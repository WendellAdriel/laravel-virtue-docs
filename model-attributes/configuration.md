# Configuration

To enable the attributes provided by this package, you just need to use the `WendellAdriel\Virtue\Models\Concerns\Virtue` trait to your Eloquent Models and you're ready to go.

To avoid issues with the properties from the models, the attributes will override the values set on the properties, so when defining for example the fillable fields with the `Fillable` attribute, if you have also defined the `$fillable` property in your model, the `Fillable` attribute list of properties will override the one from the `$fillable` property.

So when using any of the provided attributes, don't mix the attribute with its respective property to avoid conflicts or unexpected behaviours.

```php
use Illuminate\Database\Eloquent\Model;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

final class Product extends Model
{
    use Virtue;
}
```
