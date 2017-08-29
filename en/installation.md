#Installation
----------

ORCHID based off [Laravel Framework](http://laravel.com), so before you put the ORCHID, you must install [`Laravel`](http://laravel.com).

You can see the installation on [`YouTube`](https://youtu.be/e9B5eVw7yss)

#### Via Composer

Going your project directory on shell and run this command: 
```php
$ composer require orchid/cms
```

####  Provider and Facades

Add to `config/app.php`:

Service provider to the 'providers' array:
```php
'providers' => [
  // Laravel Framework Service Providers...
  //...

  // Package Service Providers
  Orchid\Platform\Providers\FoundationServiceProvider::class,
  Orchid\CMS\Providers\FoundationServiceProvider::class,

  // ...

  // Application Service Providers
  // ...
];
```

Facades aliases to the 'aliases' array:
```php
'aliases' => [
  // ...
  'Dashboard' =>  Orchid\Platform\Facades\Dashboard::class,
  'Alert' =>  Orchid\Alert\Facades\Alert::class,
  'Active' => Watson\Active\Facades\Active::class,
  'Setting' =>  Orchid\Setting\Facades\Setting::class,
  'Image' => Intervention\Image\Facades\Image::class,
];
```


#### User

Inherit your model App\User

```php
namespace App;

use Orchid\Platform\Core\Models\User as UserOrchid;

class User extends UserOrchid
{

}

```

#### Finish


**Go to url:**  localhost:8000/dashboard

The graphical installation does not work if the server is started using the `artisan serve` command, if you want to use a local server, please go to the public directory and run
```php
php -S localhost:8000
```

