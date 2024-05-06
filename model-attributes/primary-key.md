# Primary Key

The `PrimaryKey` attribute allows you to customize the primary key of your model.

```php
use Illuminate\Database\Eloquent\Model;
use WendellAdriel\Virtue\Models\Attributes\PrimaryKey;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[PrimaryKey(name: 'uuid', type: 'string', incrementing: false)]
final class Product extends Model
{
    use Virtue;
}
```
