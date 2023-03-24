### Simple Version
 
- [x] CRUD Generator
    - Support more than 15 [column types of migrations](https://laravel.com/docs/9.x/migrations#available-column-types), like `string, char, date, year`, etc.
    - Datatables ([Yajra Datatables](https://github.com/yajra/laravel-datatables))
    - [One To Many (Inverse) / Belongs To](https://laravel.com/docs/10.x/eloquent-relationships#one-to-many-inverse)
    - Model casting
    - Image upload ([Intervention Image](https://image.intervention.io/v2))
    - Support [HTML 5 Input](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types)
    - Request validations supported: `required, in, image, min, max, string, email, number, date, exists, nullable, unique, comfirmed`  

### Full Version
  
- [x] CRUD Generator
- [x] CRUD User
- [x] Roles and permissions ([Spatie Permission](https://spatie.be/docs/laravel-permission/v5/introduction))
- [x] Authentication ([Laravel Fortify](https://laravel.com/docs/9.x/fortify))
    - Login
    - Register
    - Forgot Password
    - 2FA Authentication
    - Update profile information 

## Avaiable Commands

### Install The Generator
Install Generator Variants (Simple/Full Version)

For simple version
```sh
php artisan generator:install simple
```
For full verion
```sh
php artisan generator:install full
```

### Set a sidebar menu
Set a sidebar menu to fully blade code(static) or use a list from config(dynamic)

Sidebar configuration place in ```config/generator.php```

```sh
php artisan generator:sidebar dynamic
```

While using static sidebar, you can free to edit the sidebar menus on ```resources/views/layouts/sidebar.blade.php```

```sh
php artisan generator:sidebar static
```

## Utilities/Helpers

### Check sidebar active menus

```sh
is_active_menu(string|array): boolean
```

```php
is_active_menu($menu);
```

### Utility class

All utility function that maybe you needed, avaiable in ```EvdigiIna\Generator\Generators\GeneratorUtils```