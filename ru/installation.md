# Установка
----------

ORCHID основана на [Laravel Framework](http://laravel.com), 
поэтому перед тем, как поставить ORCHID, вы должны установить [`Laravel`](http://laravel.com).


#### Используя Composer

Перейдите в каталог проекта и запустите эту команду:
```php
$ composer require orchid/cms
```

#### Пользователь

Наследовать свою модель `App\User`

```php
namespace App;

use Orchid\Platform\Core\Models\User as UserOrchid;

class User extends UserOrchid
{

}

```

#### Конец


 **Перейти к URL-адресу:**  localhost:8000/dashboard

Графическая установка не работает, если сервер запускается с помощью команды `artisan serve`, если вы хотите использовать локальный сервер, перейдите в общий каталог и запустите
```php
php -S localhost:8000
```
