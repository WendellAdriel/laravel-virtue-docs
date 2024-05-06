# Hidden

The `Hidden` attribute allows you to set your Model's properties to be hidden in the same way that the `$hidden` property does.

```php
use Illuminate\Database\Eloquent\Model;
use WendellAdriel\Virtue\Models\Attributes\Hidden;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[Hidden([
    'secret_field',
    'sensitive_data',
])]
final class Product extends Model
{
    use Virtue;
}
```
