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
- [x] Configurable sidebar menus
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
> Warning! That will overwrite several files, so use caution while using this command and avoid using it more than once.

### Set the sidebar menu
Set the sidebar menu to fully blade code(static) or use a list from config(dynamic)

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

```php
is_active_menu(string|array $menu): boolean;
```

### Utility class

All utility functions that you maybe need, are available in ```EvdigiIna\Generator\Generators\GeneratorUtils```

```php
use EvdigiIna\Generator\Generators\GeneratorUtils;

/**
* Get template/stub file.
*
* @param string $path
* @return string
*/
GeneratorUtils::getTemplate(string $path): string

/**
* Check folder if doesnt exist, then make folder.
*
* @param string $path
* @return void
*/
GeneratorUtils::checkFolder(string $path): void

/**
* Convert string to singular pascal case.
*
* @param string $string
* @return string
*/
GeneratorUtils::singularPascalCase(string $string): string

/**
* Convert string to singular pascal case.
*
* @param string $string
* @return string
*/
GeneratorUtils::pascalCase(string $string): string

/**
* Convert string to plural pascal case.
*
* @param string $string
* @return string
*/
GeneratorUtils::pluralPascalCase(string $string): string

/**
* Convert string to plural snake case.
*
* @param string $string
* @return string
*/
GeneratorUtils::pluralSnakeCase(string $string): string

/**
* Convert string to singular snake case.
*
* @param string $string
* @return string
*/
GeneratorUtils::singularSnakeCase(string $string): string

/**
* Convert string to plural pascal case.
*
* @param string $string
* @return string
*/
GeneratorUtils::pluralCamelCase(string $string): string

/**
* Convert string to singular pascal case.
*
* @param string $string
* @return string
*/
GeneratorUtils::singularCamelCase(string $string): string

/**
* Convert string to plural, kebab case, and lowercase.
*
* @param string $string
* @return string
*/
GeneratorUtils::pluralKebabCase(string $string): string

/**
* Convert string kebab case, and lowercase.
*
* @param string $string
* @return string
*/
GeneratorUtils::kebabCase(string $string): string

/**
* Convert string to singular, kebab case, and lowercase.
*
* @param string $string
* @return string
*/
GeneratorUtils::singularKebabCase(string $string): string

/**
* Convert string to singular, remove special caracters, and lowercase.
*
* @param string $string
* @return string
*/
GeneratorUtils::cleanSingularLowerCase(string $string): string

/**
* Remove special caracters, and lowercase.
*
* @param string $string
* @return string
*/
GeneratorUtils::cleanLowerCase(string $string): string

/**
* Convert string to plural, remove special caracters, and uppercase every first letters.
*
* @param string $string
* @return string
*/
GeneratorUtils::cleanPluralUcWords(string $string): string

/**
* Convert string to singular, remove special caracters, and uppercase every first letters.
*
* @param string $string
* @return string
*/
GeneratorUtils::cleanSingularUcWords(string $string): string

/**
* Remove special caracters, and uppercase every first letters.
*
* @param string $string
* @return string
*/
GeneratorUtils::cleanUcWords(string $string): string

/**
* Convert string to plural, remove special caracters, and lowercase.
*
* @param string $string
* @return string
*/
GeneratorUtils::cleanPluralLowerCase(string $string): string

/**
* Get 1 column after id on the table.
*
* @param string $table
* @return string $column
*/
GeneratorUtils::getColumnAfterId(string $table): string

/**
* Select id and column after id on the table.
*
* @param string $table
* @return string $selectedField
*/
GeneratorUtils::selectColumnAfterIdAndIdItself(string $table): string

/**
* Converts camelCase string to have spaces between each.
*
* @param string $string
* @return string
*/
GeneratorUtils::fromCamelCase(string $string): string

/**
* Set model name from the latest of array(if exists).
*
* @param string $model
* @param string $style
* @return string
*/
GeneratorUtils::setModelName(string $model, string $style = 'pascal case'): string

/**
* Set default image and code to controller.
*
* @param null|string $default,
* @param string $field
* @param string $model
* @return array
*/
GeneratorUtils::setDefaultImage(null|string $default, string $field, string $model): array

/**
* Convert array from config to string like array.
*
* @param array $idebars
* @return string
*/
GeneratorUtils::convertArraySidebarToString(array $sidebars): string
```

### Things that we want to add in the future
- API CRUD generator
- API docs
- Can create more relation type
- Upload file except image
- CRUD with desain pattern(Service/Repository Pattern)
- Laravel table pagination
- Import/Export csv
- Input for custom table name
- Change request validation as an array
- Add a checkbox for whether to use route model binding or not
- Add a checkbox to turn off automatic pluralization
- If the time zone is set to Indonesia, then disable pluralization
- Add username to users table
- New template admin
- Option to auto migrate table or not
- Add config for showing an image in the data table or not
- ability to hide/show the field on the view page
- Configuration to limit showing fields in the index page
- Can select the field that will be showing in belongsTo the relation
- The generator can make seeder and factory
- Add default config for minimum & maximum length to column type string
- The generator can make subfolders for request class validation
- Add configuration for image type rounded or square
- Add support for diffForHumans() to input type date.
- Can custom validation(write-in input)
- The generator can use caching
- The generator can create policy
- The generator can create model observer
- Use database transaction
- The generator can create mutator & casting
- Configuration for upload file to S3
- Add soft delete option
- If the model is in a subfolder then the route will use the sub-route
- Add unit test for the generator
- The generator can create unit test
- Add notification if the user changed their email or password (package)
- Add activity log (package)
- Add backup database (package)
- The Generator uses enum class for column type enum

> The list is subject to change at any time and features may be added in any order.