Symfony - Iban Bundle
=======================

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/673c6209-efe7-486e-8c20-8461c26c2564/mini.png)](https://insight.sensiolabs.com/projects/673c6209-efe7-486e-8c20-8461c26c2564)
[![Dependency Status](https://www.versioneye.com/user/projects/57703c9a6718940036449020/badge.svg?style=flat-square)](https://www.versioneye.com/user/projects/57703c9a6718940036449020)
[![Latest Stable Version](https://poser.pugx.org/shapecode/iban-bundle/v/stable)](https://packagist.org/packages/shapecode/iban-bundle) 
[![Total Downloads](https://poser.pugx.org/shapecode/iban-bundle/downloads)](https://packagist.org/packages/shapecode/iban-bundle) 
[![License](https://poser.pugx.org/shapecode/iban-bundle/license)](https://packagist.org/packages/shapecode/iban-bundle)

Install instructions
--------------------------------

First you need to add `shapecode/iban-bundle` to `composer.json`:

``` json
{
   "require": {
        "shapecode/iban-bundle": "~1.0"
    }
}
```

Please note that `dev-develop` points to the latest development version. Of course you can also use an explicit version number, e.g., `1.0.*`.

You also have to add `ShapecodeIbanBundle` to your `AppKernel.php`:

``` php
<?php

// app/AppKernel.php
//...

class AppKernel extends Kernel
{
    //...
    public function registerBundles()
    {
        $bundles = array(
            ...
            new Shapecode\Bundle\IbanBundle\ShapecodeIbanBundle(),
        );
        //...

        return $bundles;
    }
    //...
}
```

Use instructions
--------------------------------

``` php
<?php

// get iban from country code, bank identification and account number
$iban = $this->getContainer('shapecode_iban.generator')->generateIban('DE', '50010517', '0648489890');

// get bic from iban
$bic = $this->getContainer('shapecode_iban.generator')->generateBic($iban);

// validate iban
$isIban = $this->getContainer('shapecode_iban.generator')->validateIban($iban);
```
