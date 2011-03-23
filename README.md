Provides a text helper to Symfony2 projects.

Installation
============

**Add TextBundle to your application kernel:**

    // app/AppKernel.php
    public function registerBundles()
    {
        return array(
            // ...
            new EWZ\Bundle\TextBundle\EWZTextBundle(),
            // ...
        );
    }

**Add the EWZ namespace to your autoloader:**

    // app/autoload.php
    $loader->registerNamespaces(array(
        ...
        'EWZ' => __DIR__.'/../src',
    ));
