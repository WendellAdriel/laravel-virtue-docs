# Defining Options

### Flag Options

To add options that behave like flags to your command, you may use the `FlagOption` attribute.

```php
use Illuminate\Console\Command;
use WendellAdriel\Virtue\Commands\Attributes\FlagOption;
use WendellAdriel\Virtue\Commands\Concerns\Virtue;

#[FlagOption(name: 'negative', shortcut: 'm', negatable: true)]
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

These are the available properties to define your flag options:

```php
public function __construct(
        public string $name,
        public string|array|null $shortcut = null,
        public string $description = '',
        public bool $negatable = false,
    ) {
        //
    }
```

Flags that set the `negatable` as true can be used like this:

```bash
php artisan app:test --no-negative
```

### Value Options

To add options that can have values set to them to your command, you may use the `ValueOption` attribute.

```php
use Illuminate\Console\Command;
use WendellAdriel\Virtue\Commands\Attributes\ValueOption;
use WendellAdriel\Virtue\Commands\Concerns\Virtue;

#[ValueOption(name: 'scores', array: true, default: [1, 2, 3])]
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

These are the available properties to define your flag options:

```php
public function __construct(
        public string $name,
        public bool $array = false,
        public string|array|null $shortcut = null,
        public string $description = '',
        public string|bool|int|float|array|null $default = null,
        public array|Closure $suggestedValues = [],
    ) {
        //
    }
```
