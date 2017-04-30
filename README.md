# scss

[![Latest Version on NPM](https://img.shields.io/npm/v/scss-boilerplate.svg?style=flat-square)](https://npmjs.com/package/scss-boilerplate)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![GitHub issues](https://img.shields.io/github/issues/filipveschool/scss.svg)](https://github.com/filipveschool/scss/issues)
[![GitHub forks](https://img.shields.io/github/forks/filipveschool/scss.svg)](https://github.com/filipveschool/scss/network)
[![GitHub stars](https://img.shields.io/github/stars/filipveschool/scss.svg)](https://github.com/filipveschool/scss/stargazers)
[![npm](https://img.shields.io/npm/dt/scss-boilerplate.svg?style=flat-square)](https://npmjs.com/package/scss-boilerplate)




SCSS boilerplate with common functions, mixins, helpers and patterns to kickstart CSS authoring.

The package sets some sensible defaults for HTML elements eg.:

```scss
// base/*.scss

* {
    box-sizing: border-box;
    position: relative;

    &:after,
    &:before {
        box-sizing: border-box;
    }
}
```

Generic helper classes are included for common layout issues:

```scss
// helpers/margin.scss

.h-margin {
    ...
}

.h-margin-none {
    ...
}

.h-margin-small {
    ...
}

...

```

Default settings are stored in Sass maps...

```scss
// settings/typography.scss

$font-weight: (
    default: (
            ...
            ),
    secondary: (
        normal: 400,
        bold: 700,
    ),
    fixed: (
       ...
    ),
) !default;


// settings/colors.scss

$blue: (
    lightest: #e6f5ff,
    lighter: #8bcdff,
    ...
) !default;
```

... and can be used with mixins or functions afterwards:

```scss
// my-app.scss

@import 'scss-boilerplate/settings';
@import 'my-custom-settings';
@import 'scss-boilerplate/styles';

h1 {
    @include font-secondary-bold;
    color: blue(darkest);
}

```

*Full documentation in progress*

## Postcardware

Spatie is a webdesign agency based in Antwerp, Belgium. You'll find an overview of all our open source projects [on our website](https://spatie.be/opensource).

You're free to use this package (it's [MIT-licensed](LICENSE.md)), but if it makes it to your production environment we'd appreciate if you send us a postcard from your hometown, mentioning which of our package(s) you are using.

Our address is: Spatie, Samberstraat 69D, 2060 Antwerp, Belgium.

The best postcards will get published on the open source page on our website.

## Install

You can install the package via yarn:

```bash
yarn add scss-boilerplate
```

## Usage

### Import

Import the base & styles file in your SCSS files.

```scss
@import 'scss-boilerplate/settings';
@import 'scss-boilerplate/styles';
```

### Overwriting defaults

All default settings are stored in `src/settings`. Copy 1 or more of these Sass maps to your own project and import them before you import the main file.

Eg. to set your own gutters in `px` instead of `rem`, you would construct or import your own `$gutters` variable.
Be sure to remove the `!default` flag for this variable.

```scss
// your-app.scss
@import 'scss-boilerplate/settings';

// overwrite default settings
$gutter: (
    xs: 5px,
    s: 10px,
    default: 20px,
    ...
);

@import 'scss-boilerplate/styles';
```

### Autoprefixing

CSS properties are not vendor-prefixed. Running autoprefixer in your own build process is recommended.

## Documentation

This package implements the ideas from our [css-styleguide](https://github.com/spatie/css-styleguide).

*Work in progress*

### Code Style
- Install cscomb globally via `npm i csscomb -g` 
- Put a `.csscomb.json` in root dir of your project
- Run `csscomb src`

## Change log

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Credits

- [Filip Vanden Eynde](https://github.com/filipveschool)
- [All Contributors](../../contributors)

## About Filip

I am a student from Belgium who loves to develop with laravel, SCSS/SASS preprocessor and other languages.
I speak Dutch, French and English. You can soon find an overview of all my open source projects [on my website which I will create at the end of June 2017](https://vandeneyndefilip.be/opensource).

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.