# storelify

Storelify is a front-end package that help you to storage all data into one localStorage object in order to keep things tidy.

Storelify stores properties in the `_namespace` object in order to keep things tidy. When you set/get/remove/clearAll a property you only have to specify the property name (and value if you are using the `set` function), and the service will automatically add it to the `_namespace` local storage object. It will create the object if it is not yet created.

Before: <br />
<img src="./assets/before.png" />

After: <br />
<img src="./assets/after.png" />

## Usage

```sh
npm i -S storelify
```

Now, you should be able to use Storelify in your components.

Example:

```ts
import { Storelify } from "storelify";

// Don't forget to pass an env variable name where all properties will be saved, on initialization.
const storelify = new Storelify("__fmb_dev");

storelify.set("__enable_mock", true);
console.log("Is mock enabled?", storelify.get("__enable_mock")); // true
```

Avalaiable methods:

```ts
class Storelify {
  set(key: string, value: PropertyValue): void;
  get(key: string): PropertyValue | undefined;
  remove(key: string): void;
  clearAll(): void;
  size(): number;
  keys(): string[];
  has(key: string): boolean;
}
```

> **More detalied documentation [here](DOCUMENTATION.md)**

<br />
This project includes:

- [TypeScript](https://www.typescriptlang.org/)
- [Rollup](https://rollupjs.org/)
- [Microsoft API Extractor](https://api-extractor.com/)
- [TypeDoc](https://typedoc.org/)
