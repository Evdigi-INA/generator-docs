## Create your first CRUD

Go to ```/generators/create``` if yo're using [Full Version](/features#full-version) or ```/simple-generators/create``` for [Simple Version](/features)

Below is table about supported input type & validation when you are using some column type.

|Columm Type|Input Type|Validation|Length (min & max)|
|-----------|----------|----------|------------------|
|`string`|`text, textarea, email, telephone, password url, search, file, hidden`|`required|string`| ✅ |
|`integer`|`number, range, hidden`|`required|numeric`| ✅ |
|`text`|`text, textarea, email, telephone, password url, search, file, hidden`|`required|string`| ✅ |
|`booelan`|`radio, select, datalist`|`required|booelan`| ❌ |
|`char`|`text, color, week, email, telephone, password url, search, file, hidden`|`required|string`| ✅ |
|`date`|`date, month`|`required|date`| ❌ |
|`time`|`time`|`required|date`| ❌ |
|`year`|`select, datalist`|`required|numeric`| ❌ |
|`dateTime`|`datetime-local`|`required|date`| ❌ |
|`decimal`|`number, range, hidden`|`required|numeric`| ❌ |
|`double`|`number, range, hidden`|`required|numeric`| ❌ |
|`enum`|`select, readio, datalist`|`required|in`| ❌ |
|`float`|`number, range, hidden`|`required|numeric`| ❌ |
|`foreignId`|`select, datalist`|`required|exist`| ❌ |
|`tinyInteger`|`number, range, hidden`|`required|numeric`| ❌ |
|`mediumInteger`|`number, range, hidden`|`required|numeric`| ❌ |
|`bigInteger`|`number, range, hidden`|`required|numeric`| ❌ |
|`tinyText`|`text, textarea, email, telephone, password url, search, file, hidden`|`required|string`| ✅ |
|`mediumText`|`text, textarea, email, telephone, password url, search, file, hidden`|`required|string`| ✅ |
|`longText`|`text, textarea, email, telephone, password url, search, file, hidden`|`required|string`| ✅ |

> `required` validation will change to `nullable` if you uncheck required switch in the form, if any input type `password` will automatically added `confirmed` validation, `min:1|max:100` for supported length column and `email|unique` for `email` input type.


## Create Relation

![Create Relation](https://user-images.githubusercontent.com/62506582/230761648-1ef36018-2486-424b-831f-ae5f74a66705.png)

For now is only support [One To Many (Inverse) / Belongs To](https://laravel.com/docs/10.x/eloquent-relationships#one-to-many-inverse).

There is rules you must be followed if you want create a a relation:

- Field name: 
    - Must be table name but in singular + `_id`, eg: we have `users` table then its must be `user_id`.
- Column Type:
    - Change to `foreignId`.
    - For constrain or related model name, you can fill with table name or model namespcae.
    - Action on update & delete:
        - On update: `nothing, cascade, restrict`
        - On delete: `nothing, cascade, restrict, null`


> Make sure related table & model already exist, if its no then the selected field for showing in `select`/`datalist` is an `id` by default selected field is second column in related table.

## Create Upload File

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam id lacus id sem dapibus faucibus. Aenean eu magna sodales augue efficitur porttitor eget a mi. Aenean pulvinar sit amet tellus sit amet placerat. Fusce pulvinar suscipit lacus, ut fermentum nulla efficitur a.

> if you are using `storage` for store the image, make sure you run `php artisan storage:link`


## Create sidebar menu

![Create sidebar menu](https://user-images.githubusercontent.com/62506582/230722893-f11aae2c-4407-4eaf-803e-3b8491269e40.png)

> This feature only avaiable in full version.

You can easily create a dynamic sidebar menus  with just a few input. all sidebar menus configuration place in `config/generator.php`

How about i dont need dynamic sidebar menu, i just want create my menu in `blade`? yeah we provide it, [click here how to do it](/generator-docs/features/#set-the-sidebar-menu).


## Configuration

Below is the default config for the generator and sidebar menus:

```php
return [
    /**
     * If any input file(image) as default will used options below.
     */
    'image' => [
        /**
         * Path for store the image.
         *
         * avaiable options:
         * 1. public
         * 2. storage
         */
        'path' => 'storage',

        /**
         * Will used if image is nullable and default value is null.
         */
        'default' => 'https://via.placeholder.com/350?text=No+Image+Avaiable',

        /**
         * Crop the uploaded image using intervention image.
         */
        'crop' => true,

        /**
         * When set to true the uploaded image aspect ratio will still original.
         */
        'aspect_ratio' => true,

        /**
         * Crop image size.
         */
        'width' => 500,
        'height' => 500,
    ],

    'format' => [
        /**
         * Will used to first year on select, if any column type year.
         */
        'first_year' => 1900,

        /**
         * If any date column type will cast and display used this format, but for input date still will used Y-m-d format.
         *
         * another most common format:
         * - M d Y
         * - d F Y
         * - Y m d
         */
        'date' => 'd/m/Y',

        /**
         * If any input type month will cast and display used this format.
         */
        'month' => 'm/Y',

        /**
         * If any input type time will cast and display used this format.
         */
        'time' => 'H:i',

        /**
         * If any datetime column type or datetime-local on input, will cast and display used this format.
         */
        'datetime' => 'd/m/Y H:i',

        /**
         * Limit string on index view for any column type text or longtext.
         */
        'limit_text' => 100,
    ],

    /**
     * It will used for generator to manage and showing menus on sidebar views.
     *
     * Example:
     * [
     *   'header' => 'Main',
     *
     *   // All permissions in menus[] and submenus[]
     *   'permissions' => ['test view'],
     *
     *   menus' => [
     *       [
     *          'title' => 'Main Data',
     *          'icon' => '<i class="bi bi-collection-fill"></i>',
     *          'route' => null,
     *
     *          // permission always null when isset submenus
     *          'permission' => null,
     *
     *          // All permissions on submenus[] and will empty[] when submenus equals to []
     *          'permissions' => ['test view'],
     *
     *          'submenus' => [
     *                 [
     *                     'title' => 'Tests',
     *                     'route' => '/tests',
     *                     'permission' => 'test view'
     *                  ]
     *               ],
     *           ],
     *       ],
     *  ],
     *
     * This code below always changes when you use a generator and maybe you must lint or format the code.
     */
    'sidebars' => [
        [
            'header' => 'Main',
            'permissions' => [
                'test view'
            ],
            'menus' => [
                [
                    'title' => 'Main Data',
                    'icon' => '<i class="bi bi-collection-fill"></i>',
                    'route' => null,
                    'permission' => null,
                    'permissions' => [
                        'test view'
                    ],
                    'submenus' => [
                        [
                            'title' => 'Tests',
                            'route' => '/tests',
                            'permission' => 'test view'
                        ]
                    ]
                ]
            ]
        ],
        [
            'header' => 'Users',
            'permissions' => [
                'user view',
                'role & permission view'
            ],
            'menus' => [
                [
                    'title' => 'Users',
                    'icon' => '<i class="bi bi-people-fill"></i>',
                    'route' => '/users',
                    'permission' => 'user view',
                    'permissions' => [],
                    'submenus' => []
                ],
                [
                    'title' => 'Roles & permissions',
                    'icon' => '<i class="bi bi-person-check-fill"></i>',
                    'route' => '/roles',
                    'permission' => 'role & permission view',
                    'permissions' => [],
                    'submenus' => []
                ]
            ]
        ],
    ],
];

```