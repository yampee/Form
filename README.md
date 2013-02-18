Yampee Form: a PHP library to validate your forms
=============================================================

What is Yampee Form ?
----------------------------

Yampee Annotations is a PHP library to validate easily your forms, using a set
of validators and filters.

An example ?

``` php
<?php
$form = $factory->createFormBuilder()
	->add('alnum_length')
		->addValidator(new Yampee_Form_Validator_Alnum())
		->addValidator(new Yampee_Form_Validator_ExactLength(4))
		->addFilter(new Yampee_Form_Filter_Xss())
	->end()
	->add('test2')
		->setRequired(false)
		->addFilter(new Yampee_Form_Filter_Xss())
	->end();

$form->bind(array(
	'alnum_length' => 'test'
));

var_dump($form->getData());
```

Documentation
-------------

The documentation is to be found in the `doc/` directory.

About
-------

Yampee Form is licensed under the MIT license (see LICENSE file).
The Yampee Form library is developed and maintained by the Titouan Galopin.
