---
hide:
    - navigation
---

!!! info "NOTE"

    All classes are prefixed with `Phalcon`



## Dispatcher\AbstractDispatcher ![Abstract](../assets/images/abstract-green.svg) 

[Source on GitHub](https://github.com/phalcon/cphalcon/blob/5.0.x/phalcon/Dispatcher/AbstractDispatcher.zep)


-   __Namespace__

    - `Phalcon\Dispatcher`

-   __Uses__
    
    - `Exception`
    - `Phalcon\Di\AbstractInjectionAware`
    - `Phalcon\Di\DiInterface`
    - `Phalcon\Dispatcher\Exception`
    - `Phalcon\Events\EventsAwareInterface`
    - `Phalcon\Events\ManagerInterface`
    - `Phalcon\Filter\FilterInterface`
    - `Phalcon\Mvc\Model\Binder`
    - `Phalcon\Mvc\Model\BinderInterface`
    - `Phalcon\Support\Collection`

-   __Extends__
    
    `AbstractInjectionAware`

-   __Implements__
    
    - `DispatcherInterface`
    - `EventsAwareInterface`

This is the base class for Phalcon\Mvc\Dispatcher and Phalcon\Cli\Dispatcher.
This class can't be instantiated directly, you can use it to create your own
dispatchers.


### Properties
```php
/**
 * @var object|null
 */
protected $activeHandler;

/**
 * @var array
 */
protected $activeMethodMap;

/**
 * @var string
 */
protected $actionName = ;

/**
 * @var string
 */
protected $actionSuffix = Action;

/**
 * @var array
 */
protected $camelCaseMap;

/**
 * @var string
 */
protected $defaultAction = ;

/**
 * @var string
 */
protected $defaultNamespace = ;

/**
 * @var string
 */
protected $defaultHandler = ;

/**
 * @var array
 */
protected $handlerHashes;

/**
 * @var string
 */
protected $handlerName = ;

/**
 * @var string
 */
protected $handlerSuffix = ;

/**
 * @var ManagerInterface|null
 */
protected $eventsManager;

/**
 * @var bool
 */
protected $finished = false;

/**
 * @var bool
 */
protected $forwarded = false;

/**
 * @var bool
 */
protected $isControllerInitialize = false;

/**
 * @var mixed|null
 */
protected $lastHandler;

/**
 * @var BinderInterface|null
 */
protected $modelBinder;

/**
 * @var bool
 */
protected $modelBinding = false;

/**
 * @var string
 */
protected $moduleName = ;

/**
 * @var string
 */
protected $namespaceName = ;

/**
 * @var array
 */
protected $params;

/**
 * @var string|null
 */
protected $previousActionName = ;

/**
 * @var string|null
 */
protected $previousHandlerName = ;

/**
 * @var string|null
 */
protected $previousNamespaceName = ;

/**
 * @var string|null
 */
protected $returnedValue;

```

### Methods

```php
public function callActionMethod( mixed $handler, string $actionMethod, array $params = [] );
```



```php
public function dispatch(): mixed | bool;
```
Process the results of the router by calling into the appropriate
controller action(s) including any routing data or injected parameters.


```php
public function forward( array $forward ): void;
```
Forwards the execution flow to another controller/action.

```php
$this->dispatcher->forward(
    [
        "controller" => "posts",
        "action"     => "index",
    ]
);
```

@throws PhalconException


```php
public function getActionName(): string;
```
Gets the latest dispatched action name


```php
public function getActionSuffix(): string;
```
Gets the default action suffix


```php
public function getActiveMethod(): string;
```
Returns the current method to be/executed in the dispatcher


```php
public function getBoundModels(): array;
```
Returns bound models from binder instance

```php
class UserController extends Controller
{
    public function showAction(User $user)
    {
        // return array with $user
        $boundModels = $this->dispatcher->getBoundModels();
    }
}
```


```php
public function getDefaultNamespace(): string;
```
Returns the default namespace


```php
public function getEventsManager(): ManagerInterface | null;
```
Returns the internal event manager


```php
public function getHandlerClass(): string;
```
Possible class name that will be located to dispatch the request


```php
public function getHandlerSuffix(): string;
```
Gets the default handler suffix


```php
public function getModelBinder(): BinderInterface | null;
```
Gets model binder


```php
public function getModuleName(): string | null;
```
Gets the module where the controller class is


```php
public function getNamespaceName(): string;
```
Gets a namespace to be prepended to the current handler name


```php
public function getParam( mixed $param, mixed $filters = null, mixed $defaultValue = null ): mixed;
```
Gets a param by its name or numeric index


```php
public function getParameter( mixed $param, mixed $filters = null, mixed $defaultValue = null ): mixed;
```
Gets a param by its name or numeric index


```php
public function getParameters(): array;
```
Gets action params


```php
public function getParams(): array;
```
Gets action params

@todo remove this in future versions


```php
public function getReturnedValue(): mixed;
```
Returns value returned by the latest dispatched action


```php
public function hasParam( mixed $param ): bool;
```
Check if a param exists
@todo deprecate this in the future


```php
public function hasParameter( mixed $param ): bool;
```
Check if a param exists


```php
public function isFinished(): bool;
```
Checks if the dispatch loop is finished or has more pendent
controllers/tasks to dispatch


```php
public function setActionName( string $actionName ): void;
```
Sets the action name to be dispatched


```php
public function setActionSuffix( string $actionSuffix ): void;
```
Sets the default action suffix


```php
public function setDefaultAction( string $actionName ): void;
```
Sets the default action name


```php
public function setDefaultNamespace( string $defaultNamespace ): void;
```
Sets the default namespace


```php
public function setEventsManager( ManagerInterface $eventsManager ): void;
```
Sets the events manager


```php
public function setHandlerSuffix( string $handlerSuffix ): void;
```
Sets the default suffix for the handler


```php
public function setModelBinder( BinderInterface $modelBinder, mixed $cache = null ): DispatcherInterface;
```
Enable model binding during dispatch

```php
$di->set(
    'dispatcher',
    function() {
        $dispatcher = new Dispatcher();

        $dispatcher->setModelBinder(
            new Binder(),
            'cache'
        );

        return $dispatcher;
    }
);
```


```php
public function setModuleName( string $moduleName = null ): void;
```
Sets the module where the controller is (only informative)


```php
public function setNamespaceName( string $namespaceName ): void;
```
Sets the namespace where the controller class is


```php
public function setParam( mixed $param, mixed $value ): void;
```
Set a param by its name or numeric index
@todo deprecate this in the future


```php
public function setParameter( mixed $param, mixed $value ): void;
```
Set a param by its name or numeric index


```php
public function setParameters( array $params ): void;
```
Sets action params to be dispatched


```php
public function setParams( array $params ): void;
```
Sets action params to be dispatched
@todo deprecate this in the future


```php
public function setReturnedValue( mixed $value ): void;
```
Sets the latest returned value by an action manually


```php
public function wasForwarded(): bool;
```
Check if the current executed action was forwarded by another one


```php
protected function resolveEmptyProperties(): void;
```
Set empty properties to their defaults (where defaults are available)


```php
protected function toCamelCase( string $input ): string;
```





## Dispatcher\DispatcherInterface ![Interface](../assets/images/interface-blue.svg) 

[Source on GitHub](https://github.com/phalcon/cphalcon/blob/5.0.x/phalcon/Dispatcher/DispatcherInterface.zep)


-   __Namespace__

    - `Phalcon\Dispatcher`

-   __Uses__
    

-   __Extends__
    

-   __Implements__
    

Interface for Phalcon\Dispatcher\AbstractDispatcher


### Methods

```php
public function dispatch(): mixed | bool;
```
Dispatches a handle action taking into account the routing parameters


```php
public function forward( array $forward ): void;
```
Forwards the execution flow to another controller/action


```php
public function getActionName(): string;
```
Gets last dispatched action name


```php
public function getActionSuffix(): string;
```
Gets the default action suffix


```php
public function getHandlerSuffix(): string;
```
Gets the default handler suffix


```php
public function getParam( mixed $param, mixed $filters = null ): mixed;
```
Gets a param by its name or numeric index


```php
public function getParameter( mixed $param, mixed $filters = null ): mixed;
```
Gets a param by its name or numeric index


```php
public function getParameters(): array;
```
Gets action params


```php
public function getParams(): array;
```
Gets action params


```php
public function getReturnedValue(): mixed;
```
Returns value returned by the latest dispatched action


```php
public function hasParam( mixed $param ): bool;
```
Check if a param exists


```php
public function isFinished(): bool;
```
Checks if the dispatch loop is finished or has more pendent
controllers/tasks to dispatch


```php
public function setActionName( string $actionName ): void;
```
Sets the action name to be dispatched


```php
public function setActionSuffix( string $actionSuffix ): void;
```
Sets the default action suffix


```php
public function setDefaultAction( string $actionName ): void;
```
Sets the default action name


```php
public function setDefaultNamespace( string $defaultNamespace ): void;
```
Sets the default namespace


```php
public function setHandlerSuffix( string $handlerSuffix ): void;
```
Sets the default suffix for the handler


```php
public function setModuleName( string $moduleName = null ): void;
```
Sets the module name which the application belongs to


```php
public function setNamespaceName( string $namespaceName ): void;
```
Sets the namespace which the controller belongs to


```php
public function setParam( mixed $param, mixed $value ): void;
```
Set a param by its name or numeric index


```php
public function setParams( array $params ): void;
```
Sets action params to be dispatched




## Dispatcher\Exception 

[Source on GitHub](https://github.com/phalcon/cphalcon/blob/5.0.x/phalcon/Dispatcher/Exception.zep)


-   __Namespace__

    - `Phalcon\Dispatcher`

-   __Uses__
    

-   __Extends__
    
    `\Exception`

-   __Implements__
    

Exceptions thrown in Phalcon\Dispatcher/* will use this class


### Constants
```php
const EXCEPTION_ACTION_NOT_FOUND = 5;
const EXCEPTION_CYCLIC_ROUTING = 1;
const EXCEPTION_HANDLER_NOT_FOUND = 2;
const EXCEPTION_INVALID_HANDLER = 3;
const EXCEPTION_INVALID_PARAMS = 4;
const EXCEPTION_NO_DI = 0;
```
