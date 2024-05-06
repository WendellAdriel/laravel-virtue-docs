# Relationships

With **Virtue**, you can configure all of your Model **relationships** using **Attributes**. It works the same way when defining them with methods, so all of them accept the same parameters as the methods.

## **BelongsTo** <a href="#belongsto" id="belongsto"></a>

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\BelongsTo;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[BelongsTo(User::class)]
final class Post extends Model
{
    use Virtue;
}
```

## **BelongsToMany** <a href="#belongstomany" id="belongstomany"></a>

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\BelongsToMany;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[BelongsToMany(Role::class)]
final class User extends Model
{
    use Virtue;
}
```

## **HasMany** <a href="#hasmany" id="hasmany"></a>

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\HasMany;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[HasMany(Post::class)]
final class User extends Model
{
    use Virtue;
}
```

## **HasManyThrough** <a href="#hasmanythrough" id="hasmanythrough"></a>

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\HasMany;
use WendellAdriel\Virtue\Models\Attributes\Relations\HasManyThrough;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[HasMany(User::class)]
#[HasManyThrough(Post::class, User::class)]
final class Country extends Model
{
    use Virtue;
}
```

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\HasMany;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[HasMany(Post::class)]
final class User extends Model
{
    use Virtue;
}
```

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\BelongsTo;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[BelongsTo(User::class)]
final class Post extends Model
{
    use Virtue;
}
```

## **HasOne** <a href="#hasone" id="hasone"></a>

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\HasOne;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[HasOne(Phone::class)]
final class User extends Model
{
    use Virtue;
}
```

## **HasOneThrough** <a href="#hasonethrough" id="hasonethrough"></a>

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\HasOne;
use WendellAdriel\Virtue\Models\Attributes\Relations\HasOneThrough;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[HasOneThrough(Manufacturer::class, Computer::class)]
#[HasOne(Computer::class)]
final class Seller extends Model
{
    use Virtue;
}
```

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\HasOne;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[HasOne(Manufacturer::class)]
final class Computer extends Model
{
    use Virtue;
}
```

## **MorphMany/MorphTo** <a href="#morphmany-morphto" id="morphmany-morphto"></a>

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\MorphMany;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[MorphMany(Image::class, 'imageable')]
final class Post extends Model
{
    use Virtue;
}
```

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\MorphTo;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[MorphTo('imageable')]
final class Image extends Model
{
    use Virtue;
}
```

## **MorphOne/MorphTo** <a href="#morphone-morphto" id="morphone-morphto"></a>

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\MorphOne;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[MorphOne(Image::class, 'imageable')]
final class User extends Model
{
    use Virtue;
}
```

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\MorphTo;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[MorphTo('imageable')]
final class Image extends Model
{
    use Virtue;
}
```

## **MorphToMany/MorphedByMany** <a href="#morphtomany-morphedbymany" id="morphtomany-morphedbymany"></a>

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\MorphToMany;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[MorphToMany(Tag::class, 'taggable')]
final class Post extends Model
{
    use Virtue;
}
```

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\MorphedByMany;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[MorphedByMany(Post::class, 'taggable')]
final class Tag extends Model
{
    use Virtue;
}
```

## **Customizing the Relationship** <a href="#customizing-the-relationship" id="customizing-the-relationship"></a>

All the attributes listed above, except the `MorphTo` attribute, accept an additional parameter to customize the relationship name.

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\BelongsTo;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[BelongsTo(User::class, 'author')]
final class Post extends Model
{
    use Virtue;
}

$post->author; // Will return the User model
```

After the `name` parameter, you can pass the same parameters as you would do when defining the relationship using methods, for example, to customize the foreign key.

```php
use WendellAdriel\Virtue\Models\Attributes\Relations\BelongsTo;
use WendellAdriel\Virtue\Models\Concerns\Virtue;

#[BelongsTo(User::class, 'author', 'custom_id', 'id')]
final class Post extends Model
{
    use Virtue;
}
```
