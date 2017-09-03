
# Меню
----------

В системе имеется drag & drop меню которое подджерживает локализацию.

Количество меню ограничено и определяется в файле конфигурации 'config/cms'
```php

    'menu' => [
        'header'  => 'Top Menu',
        'sidebar' => 'Sidebar Menu',
        'footer'  => 'Footer Menu',
    ],
```


Чтобы использовать сгенерированные ею данные необходимо:

```php
namespace Orchid\CMS\Core\Models\Menu;

$menu = Menu::where('lang', App::getLocale())
    ->whereNull('parent')
    ->where('type', 'footer')
    ->with('children')
    ->get();
```

Мы возьём только основные пункты меню и дочернии ссылки.

Доступны методы:

```php
//Первый дочерний элемент
$menu = Menu::find(1)->children()->first();


//Родительский элемент
$menu = Menu::find(1)->parent()->get();
```
