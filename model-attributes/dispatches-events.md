# Dispatches Events

The `DispatchesOn` attribute allows you to set your Model's events to be dispatched in the same way that the `$dispatchesEvents` property does.

```php
use App\Events\ProductCreated;
use App\Events\ProductDeleted;
use App\Events\ProductUpdated;
use Illuminate\Database\Eloquent\Model;
use WendellAdriel\Virtue\Models\Attributes\DispatchesOn;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[DispatchesOn(event: 'created', class: ProductCreated::class)]
#[DispatchesOn(event: 'updated', class: ProductUpdated::class)]
#[DispatchesOn(event: 'deleted', class: ProductDeleted::class)]
final class Product extends Model
{
    use Virtue;
}
```
