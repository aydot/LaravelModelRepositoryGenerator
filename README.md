# LaravelModelRepositoryGenerator
This will make an empty repository class for your laravel model.

In your Console/Kernel.php file,
add this to your $commands property like so

```
protected $commands = [
    \App\Console\Commands\Inspire::class,
    \App\Console\Commands\RepositoryMakeCommand::class,
];
```

To generate a UserRepository class, run the artisan command:

artisan make:repo User

Will create a UserRepository class with the User model as a dependency.

```
<?php

namespace App\Repositories\User;

use App\Models\User;

class UserRepository
{
    /**
     * @var User $model
     */
    protected $model;
    
    /**
     * @param User $model
     */
    public function __construct(User $model)
    {
        parent::__construct($model);
    }
}
```

