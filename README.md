# Lumen Form Request
Laravel Form Request for Lumen framework

## Installing

Require this package, with [Composer](https://getcomposer.org/), in the root directory of your project.

```
composer require sanchescom/lumen-form-request
```

After updating composer add the following lines to register provider in `bootstrap/app.php`

```
$app->register(Sanchescom\Foundation\Providers\FormRequestServiceProvider::class);
```

## Usage

```php
<?php

namespace App\Http\Requests;

use Sanchescom\Foundation\Http\FormRequest;

class StoreRequest extends FormRequest
{
	public function authorize()
	{
		return true;
	}

	public function rules()
	{
            return [
                'name' => 'required|max:255',
                'last_name' => 'required|max:255',
                'email' => 'required|unique:users|email|max:100',
                'password' => 'required|max:45',
            ];
	}
}
```

[Laravel Form Request documentation](https://laravel.com/docs/5.8/validation#available-validation-rules)

