# A lite dart-sass implementation for modularscale-sass

## Installation

To install, use the following command:

```
npm i ms-sass
```

In vanilla projects, import the full file path as follows:

```scss
@use "path/to/node_modules/ms-sass/src/modularscale.scss";
```

For frameworks like `Next.js` that use the webpack `sass-loader`, simply import the package name:

```scss
@use "ms-sass";
```

However, a better approach would be to `@forward` this package with configurations in a globally used sass file, such as the global variables file.

```scss
@forward "ms-sass" with (
  $default-base: 1em,
  $default-ratio: 1.25
);
```

Alternatively, you can `@use` this package with configurations in the sass-loader's [`additionalData`](https://webpack.js.org/loaders/sass-loader/#additionaldata).

```scss
@use "ms-sass" as * with (
  $default-base: 1em,
  $default-ratio: 1.25
);
```

## Usage

Only the `ms` function has been implemented, and it differs slightly.

```
ms($n, [$base], [$ratio])
```

You can overwrite the `$base` with `ms(3, $base: 18px)` or `ms(3, 18px)`.

You can overwrite the `$ratio` with `ms(3, $ratio: 1.5)`.

Or overwrite both of them with `ms(3, 18px, 1.5)`.

## Credits

- [modularscale-sass](https://github.com/modularscale/modularscale-sass)
