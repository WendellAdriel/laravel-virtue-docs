# Defining Arguments

### Arguments

To add arguments to your command you can use the `Argument` attribute.

```php
use Illuminate\Console\Command;
use WendellAdriel\Virtue\Commands\Attributes\Argument;
use WendellAdriel\Virtue\Commands\Concerns\Virtue;

#[Argument(name: 'optional', required: false, description: 'Optional parameter')]
#[Argument(name: 'required')]
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

These are the available properties to define your optional arguments:

```php
public function __construct(
        public string $name,
        public bool $required = true,
        public bool $array = false,
        public string $description = '',
        public string|int|bool|array|float|null $default = null,
        public array|Closure $suggestedValues = [],
    ) {
        //
    }
```

### Optional Arguments

To add optional arguments to your command, you can also use the `OptionalArgument` attribute.

```php
use Illuminate\Console\Command;
use WendellAdriel\Virtue\Commands\Attributes\OptionalArgument;
use WendellAdriel\Virtue\Commands\Concerns\Virtue;

#[OptionalArgument(name: 'age', default: 18)]
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

These are the available properties to define your optional arguments:

```php
public function __construct(
        public string $name,
        public bool $array = false,
        public string $description = '',
        public string|int|bool|array|float|null $default = null,
        public array|Closure $suggestedValues = [],
    ) {
        //
    }
```

### Required Arguments

To add required arguments to your command, you can also use the `RequiredArgument` attribute.

```php
use Illuminate\Console\Command;
use WendellAdriel\Virtue\Commands\Attributes\RequiredArgument;
use WendellAdriel\Virtue\Commands\Concerns\Virtue;

#[RequiredArgument(name: 'name')]
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

These are the available properties to define your required arguments:

```php
public function __construct(
        public string $name,
        public bool $array = false,
        public string $description = '',
        public array|Closure $suggestedValues = [],
    ) {
        //
    }
```
