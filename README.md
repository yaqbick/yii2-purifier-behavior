yii2-purifier-behavior
==================
Purifier provides an ability to clean up HTML from any harmful code.

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist rokorolov/yii2-purifier-behavior "*"
```

or add

```
"rokorolov/yii2-purifier-behavior": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by  :

Attach a behavior to model and configure.

```php

use rokorolov\purifier\PurifierBehavior;

public function behaviors() 
{
    return [
        // ...
        'purifierBehavior' => [
            'class' => PurifierBehavior::className(),
            'attributes' => [
                self::EVENT_BEFORE_UPDATE => ['description'],
                self::EVENT_BEFORE_INSERT => ['description'],
            ],
            'textAttributes' => [
                self::EVENT_BEFORE_UPDATE => ['title', 'slug'],
                self::EVENT_BEFORE_INSERT => ['title', 'slug']
            ]
        ],
    ];
}
```