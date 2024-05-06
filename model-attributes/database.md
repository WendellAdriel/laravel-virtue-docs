# Database

The `Database` attribute allows you to customize the database connection, table and timestamps of your model.

```php
use Illuminate\Database\Eloquent\Model;
use WendellAdriel\Virtue\Models\Attributes\Database;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[Database(connection: 'pgsql', table: 'custom_products', timestamps: false)]
final class Product extends Model
{
    use Virtue;
}
```
