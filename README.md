## laravel-azure-servicebus
Laravel ServiceProvider for Azure Service Bus

### Installation

Require package in `composer.json`
    
    "repositories": [
       {
           "type": "vcs",
           "url": "https://github.com/brainagency/laravel-azure-servicebus.git"
       }
    ],

    "require": {
        "brainagency/laravel-azure-servicebus": "^1.0",
    }

Add BusProvider to `providers` section in `app/config/app.php`

    Brainagency\LaravelAzureServicebus\BusProvider::class,

Add config to `connections` section in `app/config/queue.php`

    'azure' => [
        'driver'                => 'azure.servicebus',
        'endpoint'              => env('AZURE_SERVICEBUS_ENDPOINT'),
        'SharedAccessKeyName'   => env('AZURE_SERVICEBUS_NAME'),
        'SharedAccessKey'       => env('AZURE_SERVICEBUS_KEY'),
        'queue'                 => env('AZURE_SERVICEBUS_QUEUE')
    ]

Set default queue driver in `env.php` to

    QUEUE_DRIVER=azure

Add and Fill keys in `env.php`

    AZURE_SERVICEBUS_ENDPOINT=https:// [*container-name*] .servicebus.windows.net
    AZURE_SERVICEBUS_NAME=[*access-key-name*]
    AZURE_SERVICEBUS_KEY=[*access-key*]
    AZURE_SERVICEBUS_QUEUE=[*queue-name*]

### Usage

    See Laravel [documentation](https://laravel.com/docs/5.5/queues)
