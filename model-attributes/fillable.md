# Fillable

The `Fillable` attribute allows you to set your Model's properties to be fillable in the same way that the `$fillable` property does.

```php
use Illuminate\Database\Eloquent\Model;
use WendellAdriel\Virtue\Models\Attributes\Fillable;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[Fillable([
    'name',
    'price',
    'random_number',
    'expires_at',
])]
final class Product extends Model
{
    use Virtue;
}
```
