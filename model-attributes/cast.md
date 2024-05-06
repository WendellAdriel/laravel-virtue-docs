# Cast

The `Cast` attribute allows you to cast your Model's properties to a specific type in the same way that the `$casts` property does.

```php
use Illuminate\Database\Eloquent\Model;
use WendellAdriel\Virtue\Models\Attributes\Cast;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[Cast(field: 'price', type: 'float')]
#[Cast(field: 'expires_at', type: 'immutable_datetime')]
final class Product extends Model
{
    use Virtue;
}
```
