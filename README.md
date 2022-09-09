# model-observer

[![Latest Stable Version](https://img.shields.io/packagist/v/friendsofhyperf/model-observer)](https://packagist.org/packages/friendsofhyperf/model-observer)
[![Total Downloads](https://img.shields.io/packagist/dt/friendsofhyperf/model-observer)](https://packagist.org/packages/friendsofhyperf/model-observer)
[![License](https://img.shields.io/packagist/l/friendsofhyperf/model-observer)](https://github.com/friendsofhyperf/model-observer)

## Installation

```bash
composer require friendsofhyperf/model-observer
```

## Usage

- Generator command

```bash
php bin/hyperf.php gen:observer TestObserver --model="App\\Model\\User"
```

- Single binding

```php
namespace App\Observer;

use App\Model\User;
use FriendsOfHyperf\ModelObserver\Annotation\Observer;

#[Observer(model: User::class)]
class FooObserver
{
    public function creating(User $model)
    {
        // do sth...
    }

    public function created(User $model)
    {
        // do sth...
    }

    // another events
}
```

- Multiple binding

```php
namespace App\Observer;

use App\Model\Post;
use App\Model\User;
use FriendsOfHyperf\ModelObserver\Annotation\Observer;

#[Observer(model: [User::class, Post::class])]
class FooObserver
{
    public function creating($model)
    {
        // do sth...
    }

    public function created($model)
    {
        // do sth...
    }

    // another events
}
```

## Methods

- `booting`
- `booted`
- `retrieved`
- `creating`
- `created`
- `updating`
- `updated`
- `saving`
- `saved`
- `restoring`
- `restored`
- `deleting`
- `deleted`
- `forceDeleted`
