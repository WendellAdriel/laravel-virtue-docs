# Configuration

To enable the attributes provided by this package, you need to use the `WendellAdriel\Virtue\Commands\Concerns\Virtue` trait to your Commands.

You also need to update the command to not use a `$signature` property, but only define the `$name` for it. This is to avoid issues with arguments and options defined in the `$signature`.

Instead of this:

<pre class="language-php"><code class="lang-php"><strong>use Illuminate\Console\Command;
</strong>
final class TestCommand extends Command
{
    protected $signature = 'app:test {name}';

    protected $description = 'Command description';

    public function handle()
    {
        // Command code here
    }
}
</code></pre>

Update to this:

```php
use Illuminate\Console\Command;
use WendellAdriel\Virtue\Commands\Concerns\Virtue;

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
