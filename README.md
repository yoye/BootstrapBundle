## Installation

1. Add this bundle to your project:

```
[BootstrapBundle]
    git=http://github.com/yoye/BootstrapBundle.git
    target=/bundles/Yoye/Bundle/BootstrapBundle

```

2. Add namespace

``` php
<?php
// app/autoload.php

$loader->registerNamespaces(array(
    // ...
    'Yoye'        => __DIR__.'/../vendor/bundles',
));
```

3. Register this bundle

``` php
// application/ApplicationKernel.php
public function registerBundles()
{
    return array(
        // ...
        new Yoye\Bundle\BootstrapBundle\YoyeBootstrapBundle(),
        // ...
    );
}
```

## Usage

1. Alert

You can use alert as macro in your template.

``` html
{% import "YoyeBootstrapBundle::alert.html.twig" as alert %}

{{ alert.show('basic') }}
                
```

In your controller set your flash message.

``` php
<?php 

$this->get('session')->setFlash('warning', 'Type your warning message !');
$this->get('session')->setFlash('info', 'Type your info message !');
$this->get('session')->setFlash('success', 'Type your success message !');
$this->get('session')->setFlash('error', 'Type your error message !');

```

2. Form

Config your form template:

``` yaml
# Twig Configuration
twig:
    debug:            %kernel.debug%
    strict_variables: %kernel.debug%
    form:
        resources: 
            - 'YoyeBootstrapBundle:Form:fields.html.twig'

```
    
3. Breadcrumb
    
You can use breadcrumb as macro in your template.

``` html
{% import "YoyeBootstrapBundle::breadcrumb.html.twig" as breadcrumb %}

{{ breadcrumb.draw({
    'homepage' : path("homepage"), 
    'You are here !' : none}) }}
                
```
    