EWZTextBundle
=============

This bundle provides easy text helper for Symfony2.

## Installation

Installation depends on how your project is setup:

### Step 1: Installation using the `bin/vendors.php` method

If you're using the `bin/vendors.php` method to manage your vendor libraries,
add the following entry to the `deps` in the root of your project file:

```
[EWZTextBundle]
    git=http://github.com/excelwebzone/EWZTextBundle.git
    target=/bundles/EWZ/Bundle/TextBundle
```

Next, update your vendors by running:

``` bash
$ ./bin/vendors
```

Great! Now skip down to *Step 2*.

### Step 1 (alternative): Installation with submodules

If you're managing your vendor libraries with submodules, first create the
`vendor/bundles/EWZ/Bundle` directory:

``` bash
$ mkdir -pv vendor/bundles/EWZ/Bundle
```

Next, add the necessary submodule:

``` bash
$ git submodule add git://github.com/excelwebzone/EWZTextBundle.git vendor/bundles/EWZ/Bundle/TextBundle
```

### Step2: Configure the autoloader

Add the following entry to your autoloader:

``` php
<?php
// app/autoload.php

$loader->registerNamespaces(array(
    // ...

    'EWZ' => __DIR__.'/../vendor/bundles',
));
```

### Step3: Enable the bundle

Finally, enable the bundle in the kernel:

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...

        new EWZ\Bundle\TextBundle\EWZTextBundle(),
    );
}
```

Congratulations! You're ready!

## Basic Usage

This bundle only for PHP templates, for example:

``` php
<?php echo $view['ewz_text']->excerpt('hello my world', 'my'); // "...lo my wo..." ?>
```

Here are the supported function:

``` php
<?php

function truncate($text, $length = 30, $truncate_string = '...', $truncate_lastspace = false);

function highlight($text, $phrase, $highlighter = '<strong class="highlight">\\1</strong>');

function excerpt($text, $phrase, $radius = 100, $excerpt_string = '...', $excerpt_space = false);

function wrap($text, $line_width = 80);

```
