# Установка
----------

ORCHID основана на [Laravel Framework](http://laravel.com), 
поэтому перед тем, как поставить ORCHID, вы должны установить [`Laravel`](http://laravel.com).

Вы можете увидеть установку на [`YouTube`](https://youtu.be/e9B5eVw7yss)


#### Используя Composer

Перейдите в каталог проекта и запустите эту команду:
```php
$ composer require orchid/platform
```

####  Поставщики и фасады

Добавить в `config/app.php`:

Поставщик услуг в массив `Providers`:
```php
'providers' => [
  // Laravel Framework Service Providers...
  //...

  // Package Service Providers
  Orchid\Providers\FoundationServiceProvider::class,

  // ...

  // Application Service Providers
  // ...
];
```

Алиасы фасадов к массиву `aliases`:
```php
'aliases' => [
  // ...
  'Dashboard' =>  Orchid\Facades\Dashboard::class,
  'Alert' =>  Orchid\Alert\Facades\Alert::class,
  'Setting' =>  Orchid\Setting\Facades\Setting::class,
  'Active' => Watson\Active\Facades\Active::class,
  'Image' => Intervention\Image\Facades\Image::class,
];
```


#### Пользователь

Наследовать свою модель `App\User`

```php
namespace App;

use Orchid\Core\Models\User as UserOrchid;

class User extends UserOrchid
{

}

```

#### Конец


> **Перейти к URL-адресу:**  localhost:8000/dashboard

Графическая установка не работает, если сервер запускается с помощью команды `artisan serve`, если вы хотите использовать локальный сервер, перейдите в общий каталог и запустите
```php
php -S localhost:8000
```
