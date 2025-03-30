# Tag Factory
- - -

## Overview
[Phalcon\Html\TagFactory][html-tagfactory] is a component that generates HTML tags. This component creates a new class locator with predefined HTML tag classes attached to it. Each tag class is lazy-loaded for maximum performance. To instantiate the factory and retrieve a tag helper, you need to call `newInstance()` by passing a `Phalcon\Html\Escaper` object to it.

If you are using the [Phalcon\Di\FactoryDefault][di-factorydefault] container for your application, the [Phalcon\Html\TagFactory][html-tagfactory] is already registered for you with the name `tag`.

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\TagFactory;

$escaper = new Escaper();
$factory = new TagFactory($escaper);
$helper  = $factory->newInstance('a');
```

```php
<?php

use Phalcon\Di\FactoryDefault;

$container = new FactoryDefault();

$helper = $container->tag->newInstance('a');
```

The registered names for respective helpers are:

| Name                 | Class                                     |
|----------------------|-------------------------------------------|
| `a`                  | `Phalcon\Html\Helper\Anchor`              |
| `base`               | `Phalcon\Html\Helper\Base`                |
| `breadcrumbs`        | `Phalcon\Html\Helper\Breadcrumbs`         |
| `body`               | `Phalcon\Html\Helper\Body`                |
| `button`             | `Phalcon\Html\Helper\Button`              |
| `close`              | `Phalcon\Html\Helper\Close`               |
| `doctype`            | `Phalcon\Html\Helper\Doctype`             |
| `element`            | `Phalcon\Html\Helper\Element`             |
| `form`               | `Phalcon\Html\Helper\Form`                |
| `img`                | `Phalcon\Html\Helper\Img`                 |
| `inputCheckbox`      | `Phalcon\Html\Helper\Input\Checkbox`      |
| `inputColor`         | `Phalcon\Html\Helper\Input\Color`         |
| `inputDate`          | `Phalcon\Html\Helper\Input\Date`          |
| `inputDateTime`      | `Phalcon\Html\Helper\Input\DateTime`      |
| `inputDateTimeLocal` | `Phalcon\Html\Helper\Input\DateTimeLocal` |
| `inputEmail`         | `Phalcon\Html\Helper\Input\Email`         |
| `inputFile`          | `Phalcon\Html\Helper\Input\File`          |
| `inputHidden`        | `Phalcon\Html\Helper\Input\Hidden`        |
| `inputImage`         | `Phalcon\Html\Helper\Input\Image`         |
| `inputInput`         | `Phalcon\Html\Helper\Input\Input`         |
| `inputMonth`         | `Phalcon\Html\Helper\Input\Month`         |
| `inputNumeric`       | `Phalcon\Html\Helper\Input\Numeric`       |
| `inputPassword`      | `Phalcon\Html\Helper\Input\Password`      |
| `inputRadio`         | `Phalcon\Html\Helper\Input\Radio`         |
| `inputRange`         | `Phalcon\Html\Helper\Input\Range`         |
| `inputSearch`        | `Phalcon\Html\Helper\Input\Search`        |
| `inputSelect`        | `Phalcon\Html\Helper\Input\Select`        |
| `inputSubmit`        | `Phalcon\Html\Helper\Input\Submit`        |
| `inputTel`           | `Phalcon\Html\Helper\Input\Tel`           |
| `inputText`          | `Phalcon\Html\Helper\Input\Text`          |
| `inputTextarea`      | `Phalcon\Html\Helper\Input\Textarea`      |
| `inputTime`          | `Phalcon\Html\Helper\Input\Time`          |
| `inputUrl`           | `Phalcon\Html\Helper\Input\Url`           |
| `inputWeek`          | `Phalcon\Html\Helper\Input\Week`          |
| `label`              | `Phalcon\Html\Helper\Label`               |
| `link`               | `Phalcon\Html\Helper\Link`                |
| `meta`               | `Phalcon\Html\Helper\Meta`                |
| `ol`                 | `Phalcon\Html\Helper\Ol`                  |
| `script`             | `Phalcon\Html\Helper\Script`              |
| `style`              | `Phalcon\Html\Helper\Style`               |
| `title`              | `Phalcon\Html\Helper\Title`               |
| `ul`                 | `Phalcon\Html\Helper\Ul`                  |

### Method call
If you do not wish to call `newInstance()`, you can always use the method call that corresponds to the name of the helper. Some helpers accept a `bool` `$raw` parameter, which defines whether the input will be escaped or not. This is useful when creating anchor links with images.

```php
public function a(
    string $href, 
    string $text, 
    array $attributes = [], 
    bool $raw = false
): string

public function base(
    string $href, 
    array $attributes = []
): string

public function body(
    array $attributes = []
): string

public function breadcrumbs(
    string $indent = '    ',
    string $delimiter = "\n"
): Breadcrumbs

public function button(
    string $text, 
    array $attributes = [], 
    bool $raw = false
): string

public function close(
    string $tag, 
    bool $raw = false
): string

public function doctype(
    int $flag, 
    string $delimiter
): Doctype

public function element(
    string $tag, 
    string $text, 
    array $attributes = [], 
    bool $raw = false
): string

public function form(
    array $attributes = []
): string

public function img(
    string $src, 
    array $attributes = []
): string

public function inputCheckbox(
    string $name, 
    string $value = null, 
    array $attributes = []
): Checkbox

public function inputColor(
    string $name, 
    string $value = null, 
    array $attributes = []
): Color

public function inputDate(
    string $name, 
    string $value = null, 
    array $attributes = []
): Date

public function inputDateTime(
    string $name, 
    string $value = null, 
    array $attributes = []
): DateTime

public function inputDateTimeLocal(
    string $name, 
    string $value = null, 
    array $attributes = []
): DateTimeLocal

public function inputEmail(
    string $name, 
    string $value = null, 
    array $attributes = []
): Email

public function inputFile(
    string $name, 
    string $value = null, 
    array $attributes = []
): File

public function inputHidden(
    string $name, 
    string $value = null, 
    array $attributes = []
): Hidden

public function inputImage(
    string $name, 
    string $value = null, 
    array $attributes = []
): Image

public function inputInput(
    string $name, 
    string $value = null, 
    array $attributes = []
): Input

public function inputMonth(
    string $name, 
    string $value = null, 
    array $attributes = []
): Month

public function inputNumeric(
    string $name, 
    string $value = null, 
    array $attributes = []
): Numeric

public function inputPassword(
    string $name, 
    string $value = null, 
    array $attributes = []
): Password

public function inputRadio(
    string $name, 
    string $value = null, 
    array $attributes = []
): Radio

public function inputRange(
    string $name, 
    string $value = null, 
    array $attributes = []
): Range

public function inputSearch(
    string $name, 
    string $value = null, 
    array $attributes = []
): Search

public function inputSelect(
    string $name, 
    string $value = null, 
    array $attributes = []
): Select

public function inputSubmit(
    string $name, 
    string $value = null, 
    array $attributes = []
): Submit

public function inputTel(
    string $name, 
    string $value = null, 
    array $attributes = []
): Tel

public function inputText(
    string $name, 
    string $value = null, 
    array $attributes = []
): Text

public function inputTextarea(
    string $name, 
    string $value = null, 
    array $attributes = []
): Textarea

public function inputTime(
    string $name, 
    string $value = null, 
    array $attributes = []
): Time

public function inputUrl(
    string $name, 
    string $value = null, 
    array $attributes = []
): Url

public function inputWeek(
    string $name, 
    string $value = null, 
    array $attributes = []
): Week

public function label(
    string $label, 
    array $attributes = [], 
    bool $raw = false
): string

public function link(
    string $indent = '    ', 
    string $delimiter = PHP_EOL
): Link

public function meta(
    string $indent = '    ', 
    string $delimiter = PHP_EOL
): Meta

public function ol(
    string $text, 
    array $attributes = [], 
    bool $raw = false
): Ol

public function script(
    string $indent = '    ', 
    string $delimiter = PHP_EOL
): Script

public function style(
    string $indent = '    ', 
    string $delimiter = PHP_EOL
): Style

public function title(
    string $indent = '    ', 
    string $delimiter = PHP_EOL
): Title

public function ul(
    string $text, 
    array $attributes = [], 
    bool $raw = false
): Ul

```

```php
<?php

use Phalcon\Di\FactoryDefault;

$container = new FactoryDefault();

$result = $container->tag->a('https://phalcon.io', 'Phalcon Website');

$image  = $container
    ->tag
    ->img('https://phalcon.io/img/phalcon.png')
;

$result = $container
    ->tag
    ->a(
        'https://phalcon.io', 
        $image,
        true
    )
;
```

### Helpers
All helpers that are used by the [Phalcon\Html\TagFactory][html-tagfactory] are located under the `Phalcon\Html\Helper` namespace. You can create each of these classes individually if you wish to, or you can use the tag factory as shown above.

!!! info "NOTE"

    The code and output below have been formatted for readability

### `a`
[Phalcon\Html\Helper\Anchor][html-helper-anchor] creates a `<a>` (anchor) tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $href`           | The href                          |
| `string $text`           | The text to display               |
| `array $attributes = []` | Additional attributes (key/value) |
| `bool $raw = false`      | Whether to escape or not the text |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Anchor;

$escaper = new Escaper();
$helper  = new Anchor($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('/myurl', 'click<>me', $options);
// <a href="/myurl" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
//     click&lt;&gt;me
// </a>
```

### `base`
[Phalcon\Html\Helper\Base][html-helper-base] creates a `<base>` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $href`           | The href                          |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Base;

$escaper = new Escaper();
$helper  = new Base($escaper);
$options = [
    'target' => '_blank',
];

echo $helper('/myurl', $options);
// <base href="/myurl" 
//    target="_blank">
```

### `breadcrumbs`
[Phalcon\Html\Helper\Breadcrumbs][html-helper-breadcrumbs] creates HTML for breadcrumbs based on the existing or passed template.

| Parameter           | Description   |
|---------------------|---------------|
| `string $indent`    | The indent    |
| `string $delimiter` | The delimiter |


A common piece of HTML that is present in many web applications is the breadcrumbs. These are links separated by a space or by the `/` character usually, that represents the tree structure of an application. The purpose is to give users another easy visual way to navigate throughout the application.

An example is an application that has an `admin` module, an `invoices` area, and a `view invoice` page. Usually, you would select the `admin` module, then from the links you will choose `invoices` (list), and then clicking on one of the invoices in the list, you can view it. To represent this tree-like structure, the breadcrumbs displayed could be:

```php
Home / Admin / Invoices / Viewing Invoice [1234]
``` 
Each of the words above (apart from the last one) are links to the respective pages. This way the user can quickly navigate back to a different area without having to click the back button or use another menu.

[Phalcon\Html\Helper\Breadcrumbs][html-helper-breadcrumbs] offers functionality to add text, URL, icon and attributes to each element. The resulting HTML when calling `render()` will have each breadcrumb formatted and enclosed in the HTML structure defined by the template. Each element will be separated from another using the default separator `<li>/</li>`.

### Methods
```php
public function __invoke(
    string $indent = '    ',
    string $delimiter = PHP_EOL
): static 
```

Sets the indent and delimiter and returns the object back

```php
public function add(
    string $text,
    string $link = '',
    string $icon = '',
    array $attributes = []
): static 
```
Adds a new crumb.

```php
// Adding a crumb with a link
$breadcrumbs->add("Home", "/");

// Adding a crumb with added attributes
$breadcrumbs->add("Home", "/", ["class" => "main"]);

// Adding a crumb without a link (normally the last one)
$breadcrumbs->add("Users");
```

```php
public function clear(): void
```

Clears the crumbs

```php
$breadcrumbs->clear()
```

```php
public function clearAttributes(): static
```

Clears the attributes of the parent element

```php
public function getAttributes(): array
```

Returns the attributes of the parent element

```php
public function getSeparator(): string
```

```php
public function getTemplate(): array
```

Returns the current template

```php
public function remove(int $index): void
```

Removes a crumb by index.

```php
$breadcrumbs->remove(2);
```

```php
public function render(): string
```

Renders and outputs breadcrumbs based on previously set template.

```php
echo $breadcrumbs->render();
```

```php
public function setAttributes(array $attributes): static
```

Sets the attributes for the parent element

```php
public function setSeparator(string $separator): static
```

Sets the separator

```php
public function setTemplate(
    string $main,
    string $line,
    string $last
): static 
```

Sets the HTML template

```php
public function toArray(): array
```

Returns the internal breadcrumbs array

### Templates

The default templates are:

*Main*

```html
<nav%attributes%>
<ol>
%items%
</ol>
</nav>
```

*Line*

```html
<li%attributes%><a href="%link%">%icon%%text%</a></li>
```

*Last Element*

```html
<li><span%attributes%>%text%</span></li>
```

A different template can be supplied to match the needs of the application. The template can be set using the `setTemplate()` method. The template is a string that can contain placeholders that will be replaced by the actual values when rendering the breadcrumbs.

The available placeholders are:

| Placeholder    | Description                          | Applies to |
|----------------|--------------------------------------|:----------:|
| `%attributes%` | The attributes of the parent element |   Parent   |
| `%items%`      | The list of items                    |   Parent   |
| `%link%`       | The link of the element              |  Element   |
| `%text%`       | The text of the element              |  Element   |
| `%icon%`       | The icon of the element              |  Element   |
| `%attributes%` | The attributes of the element        |  Element   |

### Separator
The separator is what is printed between each of the breadcrumbs. By default, the separator is `<li>/</li>`. You can change the separator by calling `setSeparator()`.

### Example

Our application needs to display breadcrumbs in the following format:

```html
Home > Admin > Invoices > Viewing Invoice [1234]
```

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\TagFactory;

$escaper = new Escaper();
$tagFactory = new TagFactory($escaper);

$separator = '
<span class="mx-5 text-gray-500 dark:text-gray-300 rtl:-scale-x-100">
    <svg xmlns="http://www.w3.org/2000/svg" 
         class="w-5 h-5" 
         viewBox="0 0 20 20" 
         fill="currentColor">
        <path fill-rule="evenodd" 
              d="M7.293 14.707a1 1 0 010-1.414L10.586 
                10 7.293 6.707a1 1 0 011.414-1.414l4 
                4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z" 
              clip-rule="evenodd" />
    </svg>
</span>
';

$homeIcon = '
<svg xmlns="http://www.w3.org/2000/svg" 
     class="w-5 h-5" viewBox="0 0 20 20" 
     fill="currentColor">
    <path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 
            0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 
            0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 
            0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 
            0 001.414-1.414l-7-7z" />
</svg>
';

$mainTemplate = '
<div%attributes%>
%items%
</div>
';
$lineTemplate = '
<a href="%link%"%attributes%>
    %icon%%text%
</a>
';
$lastTemplate = '
<a href="%link%"%attributes%>
    %icon%%text%
</a>
';

$homeAttributes = [
    'class' => 'text-gray-600 dark:text-gray-200',
];
$lineAttributes = [
    'class' => 'text-gray-600 dark:text-gray-200 hover:underline',
];
$lastAttributes = [
    'class' => 'text-blue-600 dark:text-blue-400 hover:underline',
];

$breadcrumbs
    ->setTemplate($mainTemplate, $lineTemplate, $lastTemplate)
    ->setSeparator($separator)
    ->add('', '#', $homeIcon, $homeAttributes)
    ->add('Admin', '#', '', $lineAttributes)
    ->add('Invoices', '#', '', $lineAttributes)
    ->add('Viewing Invoice [1234]', '#', '', $lastAttributes)
;

echo $breadcrumbs->render();    
```

Output HTML:
```html
<div class="flex items-center py-4 overflow-x-auto whitespace-nowrap">
    <a href="#" class="text-gray-600 dark:text-gray-200">
        <svg xmlns="http://www.w3.org/2000/svg" 
             class="w-5 h-5" 
             viewBox="0 0 20 20" 
             fill="currentColor">
            <path d="M10.707 2.293a1 1 
                0 00-1.414 0l-7 7a1 1 
                0 001.414 1.414L4 10.414V17a1 1 
                0 001 1h2a1 1 0 001-1v-2a1 1 
                0 011-1h2a1 1 0 011 1v2a1 1 
                0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 
                0 001.414-1.414l-7-7z" />
        </svg>
    </a>

    <span class="mx-5 text-gray-500 dark:text-gray-300 rtl:-scale-x-100">
        <svg xmlns="http://www.w3.org/2000/svg" 
             class="w-5 h-5" 
             viewBox="0 0 20 20" 
             fill="currentColor">
            <path fill-rule="evenodd" 
                  d="M7.293 14.707a1 1 
                    0 010-1.414L10.586 10 7.293 6.707a1 1 
                    0 011.414-1.414l4 4a1 1 
                    0 010 1.414l-4 4a1 1 
                    0 01-1.414 0z" 
                  clip-rule="evenodd" />
        </svg>
    </span>

    <a href="#" class="text-gray-600 dark:text-gray-200 hover:underline">
        Admin
    </a>

    <span class="mx-5 text-gray-500 dark:text-gray-300 rtl:-scale-x-100">
        <svg xmlns="http://www.w3.org/2000/svg" 
             class="w-5 h-5" 
             viewBox="0 0 20 20" 
             fill="currentColor">
            <path fill-rule="evenodd" 
                  d="M7.293 14.707a1 1 
                    0 010-1.414L10.586 10 7.293 6.707a1 1 
                    0 011.414-1.414l4 4a1 1 
                    0 010 1.414l-4 4a1 1 
                    0 01-1.414 0z" 
                  clip-rule="evenodd" />
        </svg>
    </span>

    <a href="#" class="text-gray-600 dark:text-gray-200 hover:underline">
        Invoices
    </a>

    <span class="mx-5 text-gray-500 dark:text-gray-300 rtl:-scale-x-100">
        <svg xmlns="http://www.w3.org/2000/svg" 
             class="w-5 h-5" 
             viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" 
                  d="M7.293 14.707a1 1 
                    0 010-1.414L10.586 10 7.293 6.707a1 1 
                    0 011.414-1.414l4 4a1 1 
                    0 010 1.414l-4 4a1 1 
                    0 01-1.414 0z" 
                  clip-rule="evenodd" />
        </svg>
    </span>

    <a href="#" class="text-blue-600 dark:text-blue-400 hover:underline">
        Viewing Invoice [1234]
    </a>
</div>
```

### `body`
[Phalcon\Html\Helper\Body][html-helper-body] creates a `<body>` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Body;

$escaper = new Escaper();
$helper  = new Body($escaper);
$options = [
    'class' => 'my-class',
    'id'    => 'my-id',
];

echo $helper($options);
// <body id="my-id" class="my-class">
```

!!! info "NOTE"

    This helper creates only the opening `<body>` tag. You will need to use the `Close` helper to generate the closing `</body>` tag.

### `button`
[Phalcon\Html\Helper\Button][html-helper-button] creates a `<button>` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $text`           | The text to display               |
| `array $attributes = []` | Additional attributes (key/value) |
| `bool $raw = false`      | Whether to escape or not the text |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Button;

$escaper = new Escaper();
$helper  = new Button($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('click<>me', $options);
// <button 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
//     click&lt;&gt;me
// </button>
```

### `close`
[Phalcon\Html\Helper\Close][html-helper-close] creates a closing tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $text`           | The text to display               |
| `bool $raw = false`      | Whether to escape or not the text |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Close;

$escaper = new Escaper();
$helper  = new Close($escaper);

echo $helper('form');
// </form>
```

### `doctype`
[Phalcon\Html\Helper\Doctype][html-helper-doctype] creates a `<doctype>` tag.

| Parameter           | Description                       |
|---------------------|-----------------------------------|
| `int $flag`         | The text to display               |
| `string $delimiter` | Whether to escape or not the text |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Doctype;

$escaper = new Escaper();
$helper  = new Doctype($escaper);

echo $helper(Doctype::XHTML11, '-:-');
// <!DOCTYPE html
//     PUBLIC "-//W3C//DTD XHTML 1.1//EN"-:-
//     "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd\">-:-
```

### `element`
[Phalcon\Html\Helper\Element][html-helper-element] creates a tag based on the passed `name`.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $tag`            | The href                          |
| `string $text`           | The text to display               |
| `array $attributes = []` | Additional attributes (key/value) |
| `bool $raw = false`      | Whether to escape or not the text |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Element;

$escaper = new Escaper();
$helper  = new Element($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('address', 'click<>me', $options);
// <address 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
//     click&lt;&gt;me
// </address>
```

### `form`
[Phalcon\Html\Helper\Form][html-helper-form] creates a `<form>` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Form;

$escaper = new Escaper();
$helper  = new Form($escaper);
$options = [
    'class'   => 'my-class',
    'name'    => 'my-name',
    'id'      => 'my-id',
    'method'  => 'post',
    'enctype' => 'multipart/form-data'
];

echo $helper($options);
// <form 
//    id="my-id" 
//    name="my-name" 
//    class="my-class"
//    method="post"
//    enctype="multipart/form-data">
```

!!! info "NOTE"

    This helper creates only the opening `<form>` tag. You will need to use the `Close` helper to generate the closing `</form>` tag.

### `img`
[Phalcon\Html\Helper\Img][html-helper-img] creates a `<img>` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $src`            | The image source                  |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Img;

$escaper = new Escaper();
$helper  = new Img($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('/my-url', $options);
// <img 
//    src="/my-url" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputCheckbox`
[Phalcon\Html\Helper\Checkbox][html-helper-checkbox] creates a `<input type="checkbox">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

**Methods**

```php
public function label(array $attributes)
```
Sets the label for the checkbox

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Checkbox;

$escaper = new Escaper();
$helper  = new Checkbox($escaper);
$options = [
    'id'        => 'my-id',
    'unchecked' => 'no',
    'checked'   => 'yes',
];

$result = $helper('my-name', 'yes', $options);

echo $result;
// <hidden name="my_name" value="no">
// <label for="my_id">
//     <input type="checkbox"
//         id="my_id"
//         name="x_name"
//         value="yes"
//         checked="checked" />
//     some text
// </label>
```

### `inputColor`
[Phalcon\Html\Helper\Color][html-helper-color] creates a `<input type="color">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Color;

$escaper = new Escaper();
$helper  = new Color($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="color"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputDate`
[Phalcon\Html\Helper\Date][html-helper-date] creates a `<input type="date">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Date;

$escaper = new Escaper();
$helper  = new Date($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="date"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputDatetime`
[Phalcon\Html\Helper\DateTime][html-helper-datetime] creates a `<input type="datetime">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\DateTime;

$escaper = new Escaper();
$helper  = new DateTime($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="datetime"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputDatetimeLocal`
[Phalcon\Html\Helper\DateTimeLocal][html-helper-datetime-local] creates a `<input type="datetime-local">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\DateTimeLocal;

$escaper = new Escaper();
$helper  = new DateTimeLocal($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="datetime-local"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputEmail`
[Phalcon\Html\Helper\Email][html-helper-email] creates a `<input type="email">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Email;

$escaper = new Escaper();
$helper  = new Email($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="email"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputFile`
[Phalcon\Html\Helper\File][html-helper-file] creates a `<input type="file">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\File;

$escaper = new Escaper();
$helper  = new File($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="file"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputHidden`
[Phalcon\Html\Helper\Hidden][html-helper-hidden] creates a `<input type="hidden">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Hidden;

$escaper = new Escaper();
$helper  = new Hidden($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="hidden"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputImage`
[Phalcon\Html\Helper\Image][html-helper-image] creates a `<input type="image">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Image;

$escaper = new Escaper();
$helper  = new Image($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="image"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputMonth`
[Phalcon\Html\Helper\Month][html-helper-month] creates a `<input type="month">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Month;

$escaper = new Escaper();
$helper  = new Month($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="month"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `input`
[Phalcon\Html\Helper\Input][html-helper-input] creates a `<input>` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

**Methods**

```php
public function setType(string $type)
```
Sets the type of the input

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Input;

$escaper = new Escaper();
$helper  = new Input($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

$result = $helper('test-name', "test-value", $options);

$result->setType('month');

echo $result;
// <input type="month"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputNumeric`
[Phalcon\Html\Helper\Numeric][html-helper-numeric] creates a `<input type="numeric">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Numeric;

$escaper = new Escaper();
$helper  = new Numeric($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="numeric"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputPassword`
[Phalcon\Html\Helper\Password][html-helper-password] creates a `<input type="password">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Password;

$escaper = new Escaper();
$helper  = new Password($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="password"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputRadio`
[Phalcon\Html\Helper\Radio][html-helper-radio] creates a `<input type="radio">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

**Methods**

```php
public function label(array $attributes)
```
Sets the label for the radio

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Radio;

$escaper = new Escaper();
$helper  = new Radio($escaper);
$options = [
    'id'        => 'my-id',
    'unchecked' => 'no',
    'checked'   => 'yes',
];

$result = $helper('my-name', 'yes', $options);

echo $result;
// <hidden name="my_name" value="no">
// <label for="my_id">
//     <input type="radio"
//         id="my_id"
//         name="x_name"
//         value="yes"
//         checked="checked" />
//     some text
// </label>
```

### `inputRange`
[Phalcon\Html\Helper\Range][html-helper-range] creates a `<input type="range">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Range;

$escaper = new Escaper();
$helper  = new Range($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="range"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputSearch`
[Phalcon\Html\Helper\Search][html-helper-search] creates a `<input type="search">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Search;

$escaper = new Escaper();
$helper  = new Search($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="search"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputSelect`
[Phalcon\Html\Helper\Select][html-helper-select] creates a `<select>` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |


**Methods**

```php
public function add(
    string $text,
    string $value = null,
    array $attributes = [],
    bool $raw = false
): Select
```
Add an element to the list

```php
public function addPlaceholder(
    string $text,
    mixed $value = null,
    array $attributes = [],
    bool $raw = false
): Select
```
Add a placeholder to the element

```php
public function optGroup(
    string $label = null,
    array $attributes = []
): Select
```
Create an option group

```php
public function selected(string $selected): Select
```
Set the selected option

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Select;

$escaper = new Escaper();
$helper  = new Select($escaper);

$options = [
    'id' => 'carsList',
];
 
$result = $helper('    ', PHP_EOL, $options);
$result
    ->add("Ferrari", "1", ["class" => "active"])
    ->add("Ford", "2")
    ->add("Dodge", "3")
    ->add("Toyota", "4")
    ->optGroup(
        'oneLabel',
        [
            'class' => 'form-input',
        ]
    )
    ->addPlaceholder(
        'Choose & Car...',
        "0",
        [],
        true,
    )
    ->selected("3")
;

echo $result;
//
//    <select id="carsList">
//        <optgroup class="form-input" label="oneLabel">
//            <option value="0">Choose & Car...</option>
//            <option value="1" class="active">Ferrari</option>
//            <option value="2">Ford</option>
//            <option value="3" selected="selected">Dodge</option>
//            <option value="4">Toyota</option>
//        </optgroup>
//    </select>"
```

### `inputSubmit`
[Phalcon\Html\Helper\Submit][html-helper-submit] creates a `<input type="submit">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Submit;

$escaper = new Escaper();
$helper  = new Submit($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="submit"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputTel`
[Phalcon\Html\Helper\Tel][html-helper-tel] creates a `<input type="tel">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Tel;

$escaper = new Escaper();
$helper  = new Tel($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="tel"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputText`
[Phalcon\Html\Helper\Text][html-helper-text] creates a `<input type="text">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Text;

$escaper = new Escaper();
$helper  = new Text($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="text"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputTextarea`
[Phalcon\Html\Helper\TextArea][html-helper-textarea] creates a `<textarea>` tags

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\TextArea;

$escaper = new Escaper();
$helper  = new TextArea($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('click<>me', $options);
// <textarea 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
//     click&lt;&gt;me
// </textarea>
```

### `inputTime`
[Phalcon\Html\Helper\Time][html-helper-time] creates a `<input type="time">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Time;

$escaper = new Escaper();
$helper  = new Time($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="time"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputUrl`
[Phalcon\Html\Helper\Url][html-helper-url] creates a `<input type="url">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Url;

$escaper = new Escaper();
$helper  = new Url($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="url"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `inputWeek`
[Phalcon\Html\Helper\Week][html-helper-week] creates a `<input type="week">` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $name`           | The name                          |
| `string $value`          | The value                         |
| `array $attributes = []` | Additional attributes (key/value) |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Input\Week;

$escaper = new Escaper();
$helper  = new Week($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper('test-name', "test-value", $options);
// <input type="week"
//    value="test-value" 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

### `label`
[Phalcon\Html\Helper\Label][html-helper-label] creates a `<label>` tag.

| Parameter                | Description                       |
|--------------------------|-----------------------------------|
| `string $label`          | The label                         |
| `array $attributes = []` | Additional attributes (key/value) |
| `bool $raw = false`      | Whether to escape or not the text |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Label;

$escaper = new Escaper();
$helper  = new Label($escaper);
$options = [
    'class' => 'my-class',
    'name'  => 'my-name',
    'id'    => 'my-id',
];

echo $helper($options);
// <label 
//    id="my-id" 
//    name="my-name" 
//    class="my-class">
```

!!! info "NOTE"

    This helper creates only the opening `<label>` tag. You will need to use the `Close` helper to generate the closing `</label>` tag.

### `link`
[Phalcon\Html\Helper\Link][html-helper-link] creates a `<link>` tag.

| Parameter           | Description   |
|---------------------|---------------|
| `string $indent`    | The indent    |
| `string $delimiter` | The delimiter |

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Link;

$escaper = new Escaper();
$helper  = new Link($escaper);

$result = $helper();
$result
    ->add('https://phalcon.io/page/1', ['rel' => 'prev'])
    ->add('https://phalcon.io/page/2', ['rel' => 'next'])
;

echo $result;
// <link rel="prev" href="https://phalcon.io/page/1" />
// <link rel="next" href="https://phalcon.io/page/2" />
```

### `meta`
[Phalcon\Html\Helper\Meta][html-helper-meta] creates a `<meta>` tag.

| Parameter           | Description   |
|---------------------|---------------|
| `string $indent`    | The indent    |
| `string $delimiter` | The delimiter |

**Methods**
```php
public function add(array $attributes = []): Meta
```
Add an element to the list

```php
public function addHttp(string $httpEquiv, string $content): Meta
```
Adds an HTTP meta tag

```php
public function addName(string name, string content) -> <Meta>
```
Adds a name meta tag

```php
public function addProperty(string name, string content) -> <Meta>
```
Adds a property meta tag

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Meta;

$escaper = new Escaper();
$helper  = new Meta($escaper);

$result = $helper();

$result
    ->add(
        [
            "charset" => 'utf-8',
        ]
    )
    ->addHttp("X-UA-Compatible", "IE=edge")
    ->addName("generator", "Phalcon")
    ->addProperty("org:url", "https://phalcon.io")
;

echo $result;
//    <meta charset="utf-8">
//    <meta http-equiv="X-UA-Compatible" content="IE=edge">
//    <meta name="generator" content="Phalcon">
//    <meta property="org:url" content="https://phalcon.io">
```

### `ol`
[Phalcon\Html\Helper\Ol][html-helper-ol] creates a `<ol>` tag.

| Parameter           | Description   |
|---------------------|---------------|
| `string $indent`    | The indent    |
| `string $delimiter` | The delimiter |

**Methods**

```php
public function add(
    string $text,
    array $attributes = [],
    bool $raw = false
): Ol
```
Add an element to the list

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Ol;

$escaper = new Escaper();
$helper  = new Ol($escaper);
$options = [
    'id' => 'carsList',
]

$result = $helper('    ', PHP_EOL, $options);

$result
    ->add("Ferrari", "1", ["class" => "active"])
    ->add("Ford", "2")
    ->add("Dodge", "3")
    ->add("Toyota", "4")
;

echo $result;
// <ol id="carsList">
//     <li class="active">Ferrari</li>
//     <li>> Ford</li>
//     <li>> Dodge</li>
//     <li>> Toyota</li>
// </ol>
```

### `script`
[Phalcon\Html\Helper\Script][html-helper-script] creates a `<script>` tag.

| Parameter           | Description   |
|---------------------|---------------|
| `string $indent`    | The indent    |
| `string $delimiter` | The delimiter |

**Methods**

```php
public function add(
    string $url,
    array $attributes = []
): Script
```
Add a URL to the list

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Script;

$escaper = new Escaper();
$helper  = new Script($escaper);

$result = $helper();

$result
    ->add('/js/custom.js')
    ->add('/js/print.js', ['ie' => 'active'])
;

echo $result;
//    <script type="application/javascript" 
//            src="/js/custom.js"></script>
//    <script type="application/javascript" 
//            src="/js/print.js" ie="active"></script>
```

### `style`
[Phalcon\Html\Helper\Script][html-helper-style] creates a `<link>` tag.

| Parameter           | Description   |
|---------------------|---------------|
| `string $indent`    | The indent    |
| `string $delimiter` | The delimiter |

**Methods**

```php
public function add(
    string $url,
    array $attributes = []
): Script
```
Add a URL to the list

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Script;

$escaper = new Escaper();
$helper  = new Script($escaper);

$result = $helper();

$result
    ->add('custom.css')
    ->add('print.css', ['media' => 'print'])
;

echo $result;
//    <link rel="stylesheet" type="text/css"
//        href="custom.css" media="screen" />
//    <link rel="stylesheet" type="text/css"
//        href="print.css" media="print" />
```

### `title`
[Phalcon\Html\Helper\Title][html-helper-title] creates a `<title>` tag.

| Parameter           | Description   |
|---------------------|---------------|
| `string $indent`    | The indent    |
| `string $delimiter` | The delimiter |

**Methods**

```php
public function append(
    string $text, 
    bool $raw = false
): Title
```
Appends text to the current document title

```php
public function get(): string
```
Returns the title

```php
public function set(
    string $text, 
    bool $raw = false
)): Title
```
Sets the title

```php
public function setSeparator(
    string $separator, 
    bool $raw = false
)): Title
```
Sets the separator

```php
public function prepend(
    string $text, 
    bool $raw = false
): Title
```
Prepends text to the current document title

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Ul;

$escaper = new Escaper();
$helper  = new Ul($escaper);
$options = [
    'id' => 'carsList',
]

$result = $helper();

$result
    ->setSeparator(' | ')
    ->set('<Dodge>')
    ->append('< Ferrari', true)
    ->prepend('Ford <')
;

echo $result->get();
// &lt; Dodge &gt;

echo $result;
// <title>Ford > | &lt; Dodge &gt; | < Ferrari</title>
```

### `ul`
[Phalcon\Html\Helper\Ul][html-helper-ol] creates a `<ul>` tag.

| Parameter           | Description   |
|---------------------|---------------|
| `string $indent`    | The indent    |
| `string $delimiter` | The delimiter |

**Methods**

```php
public function add(
    string $text,
    array $attributes = [],
    bool $raw = false
): Ol
```
Add an element to the list

```php
<?php

use Phalcon\Html\Escaper;
use Phalcon\Html\Helper\Ul;

$escaper = new Escaper();
$helper  = new Ul($escaper);
$options = [
    'id' => 'carsList',
]

$result = $helper('    ', PHP_EOL, $options);

$result
    ->add("Ferrari", "1", ["class" => "active"])
    ->add("Ford", "2")
    ->add("Dodge", "3")
    ->add("Toyota", "4")
;

echo $result;
// <ul id="carsList">
//     <li class="active">Ferrari</li>
//     <li>> Ford</li>
//     <li>> Dodge</li>
//     <li>> Toyota</li>
// </ul>
```



[di-factorydefault]: api/phalcon_di.md#difactorydefault
[html-attributes]: api/phalcon_html.md#htmlattributes
[html-attributes-attributesinterface]: api/phalcon_html.md#htmlattributesattributesinterface
[html-attributes-renderinterface]: api/phalcon_html.md#htmlattributesrenderinterface
[html-breadcrumbs]: api/phalcon_html.md#htmlbreadcrumbs
[html-exception]: api/phalcon_html.md#htmlexception
[html-helper-abstracthelper]: api/phalcon_html.md#htmlhelperabstracthelper
[html-helper-abstractlist]: api/phalcon_html.md#htmlhelperabstractlist
[html-helper-abstractseries]: api/phalcon_html.md#htmlhelperabstractseries
[html-helper-anchor]: api/phalcon_html.md#htmlhelperanchor
[html-helper-base]: api/phalcon_html.md#htmlhelperbase
[html-helper-breadcrumbs]: api/phalcon_html.md#htmlhelperbreadcrumbs
[html-helper-body]: api/phalcon_html.md#htmlhelperbody
[html-helper-button]: api/phalcon_html.md#htmlhelperbutton
[html-helper-close]: api/phalcon_html.md#htmlhelperclose
[html-helper-doctype]: api/phalcon_html.md#htmlhelperdoctype
[html-helper-element]: api/phalcon_html.md#htmlhelperelement
[html-helper-form]: api/phalcon_html.md#htmlhelperform
[html-helper-img]: api/phalcon_html.md#htmlhelperimg
[html-helper-input-abstractinput]: api/phalcon_html.md#htmlhelperinputabstractinput
[html-helper-input-checkbox]: api/phalcon_html.md#htmlhelperinputcheckbox
[html-helper-input-color]: api/phalcon_html.md#htmlhelperinputcolor
[html-helper-input-date]: api/phalcon_html.md#htmlhelperinputdate
[html-helper-input-datetime]: api/phalcon_html.md#htmlhelperinputdatetime
[html-helper-input-datetimelocal]: api/phalcon_html.md#htmlhelperinputdatetimelocal
[html-helper-input-email]: api/phalcon_html.md#htmlhelperinputemail
[html-helper-input-file]: api/phalcon_html.md#htmlhelperinputfile
[html-helper-input-hidden]: api/phalcon_html.md#htmlhelperinputhidden
[html-helper-input-image]: api/phalcon_html.md#htmlhelperinputimage
[html-helper-input-input]: api/phalcon_html.md#htmlhelperinputinput
[html-helper-input-month]: api/phalcon_html.md#htmlhelperinputmonth
[html-helper-input-numeric]: api/phalcon_html.md#htmlhelperinputnumeric
[html-helper-input-password]: api/phalcon_html.md#htmlhelperinputpassword
[html-helper-input-radio]: api/phalcon_html.md#htmlhelperinputradio
[html-helper-input-range]: api/phalcon_html.md#htmlhelperinputrange
[html-helper-input-search]: api/phalcon_html.md#htmlhelperinputsearch
[html-helper-input-select]: api/phalcon_html.md#htmlhelperinputselect
[html-helper-input-submit]: api/phalcon_html.md#htmlhelperinputsubmit
[html-helper-input-tel]: api/phalcon_html.md#htmlhelperinputtel
[html-helper-input-text]: api/phalcon_html.md#htmlhelperinputtext
[html-helper-input-textarea]: api/phalcon_html.md#htmlhelperinputtextarea
[html-helper-input-time]: api/phalcon_html.md#htmlhelperinputtime
[html-helper-input-url]: api/phalcon_html.md#htmlhelperinputurl
[html-helper-input-week]: api/phalcon_html.md#htmlhelperinputweek
[html-helper-label]: api/phalcon_html.md#htmlhelperlabel
[html-helper-link]: api/phalcon_html.md#htmlhelperlink
[html-helper-meta]: api/phalcon_html.md#htmlhelpermeta
[html-helper-ol]: api/phalcon_html.md#htmlhelperol
[html-helper-script]: api/phalcon_html.md#htmlhelperscript
[html-helper-style]: api/phalcon_html.md#htmlhelperstyle
[html-helper-title]: api/phalcon_html.md#htmlhelpertitle
[html-helper-ul]: api/phalcon_html.md#htmlhelperul
[html-tagfactory]: api/phalcon_html.md#htmltagfactory
