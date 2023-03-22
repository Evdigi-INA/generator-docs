## Requirements

All you need is [Composer](https://getcomposer.org/), [PHP ^8.1](https://www.php.net/releases/8.1/en.php), and [Laravel ^9.x](http://laravel.com/).

## Installation

```sh
composer require evdigiina/generator --dev
```
> For this package, there are two variations: [Simpe Version](#simple-version) and [Full Version](#full-version)

### Simple Version

 ![image](https://user-images.githubusercontent.com/62506582/219941448-94c46fca-6a9f-422b-bdd1-29f642c3ccf6.png)


Only the generator, includes: [Yajra Datatables](https://yajrabox.com/docs/laravel-datatables/master/installation), [Intervention Image](https://image.intervention.io/v2), and [Bootstrap 5](https://getbootstrap.com/).

[View all features](/features)
  
Publish assets

```sh
php artisan generator:install simple
```

Register the provider in `config/app.php`

```php
/*
* Package Service Providers...
*/
App\Providers\ViewComposerServiceProvider::class,
```
  
Then goes to ```/simple-generators/create/```
  
<hr>

### Full Version

![image](https://user-images.githubusercontent.com/62506582/219942571-63c42764-1702-4df3-b165-4217e5558713.png)

The generator + starter app, includes: [Yajra Datatables](https://yajrabox.com/docs/laravel-datatables/master/installation), [Intervention Image](https://image.intervention.io/v2), [Laravel Fortify](https://laravel.com/docs/9.x/fortify), [Spatie Permission](https://spatie.be/docs/laravel-permission/v5/installation-laravel), and [Mazer Template](https://github.com/zuramai/mazer).

[View all features](/features#full-version).


> Installing this package after a brand-new Laravel installation is necessary if you want to use the full version of it. because several files will be overwritten.

  
Install [Laravel Fortify](https://laravel.com/docs/9.x/fortify) & [Spatie Permission](https://spatie.be/docs/laravel-permission/v5/installation-laravel)


```sh
composer require laravel/fortify spatie/laravel-permission
```

Publish assets

```sh
php artisan generator:install full
```

> Warning! Be careful with this command, it will overwrite several files, don't run it multiple times.
 
Register the provider in `config/app.php`

```php
/*
* Package Service Providers...
*/

App\Providers\FortifyServiceProvider::class,
Spatie\Permission\PermissionServiceProvider::class,
App\Providers\ViewComposerServiceProvider::class,
```

Run migration and seeder

```sh
php artisan migrate --seed
```

Then goes to ```/generators/create```

Account

- Email: admin@example.com
- Password: password

## What's inside?  

#### Simple Version

- [Yajra datatable - ^10.x](https://yajrabox.com/docs/laravel-datatables/master/installation)
- [Intervention Image - ^2.x](https://image.intervention.io/v2)
- [Bootstrap - ^5.x](https://getbootstrap.com/)
  
#### Full Version

- [Yajra datatable - ^10.x](https://yajrabox.com/docs/laravel-datatables/master/installation)
- [Intervention Image - ^2.x](https://image.intervention.io/v2)
- [Laravel Forify - ^1.x](https://laravel.com/docs/9.x/fortify)
- [Spatie permission - ^5.x](https://github.com/spatie/laravel-permission)
- [Mazer template - ^2.x](https://github.com/zuramai/mazer/)

## Pricing
Nope, it's 100% free & open source.

## License
MIT.

## Contributors
<a  href="https://github.com/Evdigi-INA/generator/graphs/contributors">
<img  src="https://contrib.rocks/image?repo=Evdigi-INA/generator&anon=1&columns=10"  />
</a>