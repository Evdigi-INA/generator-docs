To contribute to this project, please follow the following steps:

- [Star & fork the repository](https://github.com/Evdigi-INA/generator)

- Create a new laravel project using the following command: `composer create-project laravel/laravel generator-dev` or `laravel new generator-dev`

- Install the dependencies using the following command: `composer require laravel/fortify spatie/laravel-permission intervention/image "^2.0" yajra/laravel-datatables-oracle`

- Publish `fortify` resources `php artisan vendor:publish --provider="Laravel\Fortify\FortifyServiceProvider"`

- Create folder `packages/evdigi-ina` in the root of the project

- Cd into `packages/evdigi-ina`, clone the repository `git clone https://github.com/Evdigi-INA/generator.git` and install the depedency `composer i` then back again into root project

- Add the following code to the `composer.json`

```json
"autoload": {
    "psr-4": {
        "App\\": "app/",
        "Database\\Factories\\": "database/factories/",
        "Database\\Seeders\\": "database/seeders/",
        "EvdigiIna\\Generator\\": "packages/evdigi-ina/generator/src/"
    }
},
```

- Run the following command `composer dump-autoload`

- Add the following code to the `config/app.php`

```php
/*
* Package Service Providers...
*/
EvdigiIna\Generator\Providers\GeneratorServiceProvider::class,
Yajra\DataTables\DataTablesServiceProvider::class,
Spatie\Permission\PermissionServiceProvider::class,
Intervention\Image\ImageServiceProvider::class,
App\Providers\FortifyServiceProvider::class,
// App\Providers\ViewComposerServiceProvider::class,
```

- Publish required file for the generator `php artisan generator:install full`
- Add the following code to the `composer.json` (autoload files)

```json
"autoload": {
    "psr-4": {
        "App\\": "app/",
        "Database\\Factories\\": "database/factories/",
        "Database\\Seeders\\": "database/seeders/",
        "EvdigiIna\\Generator\\": "packages/evdigi-ina/generator/src/"
    },
     "files": [
         "App/Generators/helper.php"
    ]
},
```

- Uncomment `App\Providers\ViewComposerServiceProvider::class` in `config/app.php`


- Then run `composer dump-autoload` for a second time

- Migrate the database `php artisan migrate --seed`

- Run local development server `php artisan serve` and go to `/generators/create`

- Make changes code as you wish in `packages/evdigi-ina/generator`.

- Make sure the code is working properly

- Checkout to a new branch `git branch your_name` && `git checkout your_name` && `git add .` && `git commit -m "describe your changes`

- Push the code to the repository `git push origin your_name`

- Create a pull request.
