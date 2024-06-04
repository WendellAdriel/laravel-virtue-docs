---
description: Extend the Laravel Framework with a collection of attributes
---

# ✨ Virtue

<figure><img src=".gitbook/assets/cover.png" alt=""><figcaption></figcaption></figure>

**Virtue** is a package that extends the Laravel Framework by providing a collection of attributes that you can use to configure and extend the built-in classes of the framework.

The focus of the package is to bring the power of the PHP 8 attributes to improve the DX on how to configure and extend your Laravel applications.

## Example

Currently, this package provides attributes for **Models** and **Commands**.

### Models

You can use the attributes to configure your models easily and intuitively (check out all the attributes in the docs):

```php
use Illuminate\Database\Eloquent\Model;
use WendellAdriel\Virtue\Models\Attributes\Database;
use WendellAdriel\Virtue\Models\Attributes\PrimaryKey;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[Database(connection: 'pgsql', table: 'custom_products', timestamps: false)]
#[PrimaryKey(name: 'uuid', type: 'string', incrementing: false)]
#[BelongsTo(Store::class)]
final class Product extends Model
{
    use Virtue;
}
```

### Commands

You can configure the inputs needed for your commands using attributes (check out all the attributes in the docs):

```php
use Illuminate\Console\Command;
use WendellAdriel\Virtue\Commands\Attributes\FlagOption;
use WendellAdriel\Virtue\Commands\Attributes\OptionalArgument;
use WendellAdriel\Virtue\Commands\Attributes\RequiredArgument;
use WendellAdriel\Virtue\Commands\Concerns\Virtue;

#[RequiredArgument(name: 'name')]
#[OptionalArgument(name: 'age', default: 18)]
#[FlagOption(name: 'scores-only', shortcut: 's')]
final class TestCommand extends Command
{
    use Virtue;

    protected $name = 'app:test';

    protected $description = 'Command description';

    public function handle()
    {
        // Command code here
    }
}
```

## Credits

* [Wendell Adriel](https://github.com/WendellAdriel)
* [All Contributors](https://github.com/WendellAdriel/laravel-virtue/graphs/contributors)

## Contributing

Check the [**Contributing Guide**](https://github.com/WendellAdriel/laravel-virtue/blob/main/CONTRIBUTING.md).
