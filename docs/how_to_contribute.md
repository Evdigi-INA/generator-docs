To contribute to this project, please follow the following steps:

- [Star & fork the repository](https://github.com/Evdigi-INA/generator).

2. Create a new laravel project using the following command: `composer create-project --prefer-dist laravel/laravel generator-dev` or `laravel new generator-dev`.

3. Create folder `packages/evdigi/generator` in the root of the project.

4. Install the dependencies using the following command: `composer require laravel/fortify spatie/laravel-permission intervention/image yajra/laravel-datatables-oracle`.

5. Clone the repository in the folder `packages/evdigi-ina` using the following command: `git clone https://github.com/Evdigi-INA/generator.git`.

6. Add the following code to the `composer.json` file in the root of the project:

```json
"autoload": {
    "psr-4": {
        "App\\": "app/",
        "Database\\Factories\\": "database/factories/",
        "Database\\Seeders\\": "database/seeders/",
        "EvdigiIna\\Generator\\": "packages/evdigi-ina/generator/src/"
    },
    "files": [
        "packages/evdigi-ina/generator/src/Helpers/helper.php"
    ]
},
```

- Run the following command: `composer dump-autoload`.

8. Add the following code to the `config/app.php` `providers` file in the root of the project:

```php
/*
* Package Service Providers...
*/
EvdigiIna\Generator\Providers\GeneratorServiceProvider::class,
Yajra\DataTables\DataTablesServiceProvider::class,
Spatie\Permission\PermissionServiceProvider::class,
Intervention\Image\ImageServiceProvider::class,
App\Providers\FortifyServiceProvider::class,
App\Providers\ViewComposerServiceProvider::class,
```

- Publish required file for the generator: `php artisan generator:install all`.

10. Migrate the database: `php artisan migrate --seed`.
11. Run local development server : `php artisan serve` and go to `/generators/create`.
12. Make changes code as you wish in `packages/evdigi-ina/generator`.
13. Make sure the code is working properly.
14. Checkout to a new branch `git branch your_name` && `git checkout your_name` && `git add .` && `git commit -m "describe your changes`.
15. Push the code to the repository `git push origin your_name`.
16. Create a pull request.
