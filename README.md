# NgxTranslateCut Pipe

[![npm version](https://badge.fury.io/js/ngx-translate-cut.svg)](https://badge.fury.io/js/ngx-translate-cut)
[![Package License](https://img.shields.io/npm/l/ngx-translate-cut.svg)](https://www.npmjs.com/ngx-translate-cut)
[![Build & Publish](https://github.com/bartholomej/ngx-translate-cut/workflows/Build%20&%20Publish/badge.svg?branch=master)](https://github.com/bartholomej/ngx-translate-cut/actions)
[![NPM Downloads](https://img.shields.io/npm/dm/ngx-translate-cut.svg)](https://www.npmjs.com/ngx-translate-cut)
[![codecov](https://codecov.io/gh/bartholomej/ngx-translate-cut/branch/master/graph/badge.svg?token=FV0ZM2Y3L3)](https://codecov.io/gh/bartholomej/ngx-translate-cut)

> Angular pipe for cutting translations ✂️ 🌍 (plugin for [@ngx-translate](https://github.com/ngx-translate/core))

> ✓ _Angular 12, Ivy and Angular Universal (SSR) compatible_

Here's the [demo](http://bartholomej.github.io/ngx-translate-cut/) or [stackblitz live preview](https://stackblitz.com/edit/ngx-translate-cut)

## Install

_Make sure you have installed [@ngx-translate](https://github.com/ngx-translate/core) library_

1. Use yarn (or npm) to install the package

```terminal
yarn add ngx-translate-cut
```

2. Add NgxTranslateCutModule into your module `imports`

```typescript
  import { NgxTranslateCutModule } from 'ngx-translate-cut';

  @NgModule({
   // ...
   imports: [
     // ...
     NgxTranslateCutModule
   ]
  })
```

## Usage

### Definition

Strings are separated with `|` _(pipe sign)_
_[...but you can choose your own symbol](#options)_

File `assets/i18n/en.json`

```json
{
  "demo": "This is only one 'translate string' with | strong text | and | links"
}
```

### Example code

In your template use `translateCut:<number>` pipe right after `translate` pipe from [@ngx-translate](https://github.com/ngx-translate/core) library.

```html
{{ 'demo' | translate | translateCut:0 }}

<strong> {{ 'demo' | translate | translateCut:1 }} </strong>

{{ 'demo' | translate | translateCut:2 }}

<a href="#"> {{ 'demo' | translate | translateCut:3 }} </a>
```

### Result

> This is only one 'translate string' with <strong>strong</strong> text and [links](https://github.com/bartholomej/ngx-translate-cut/)

## Options

If you are not satisfied with the basic settings of the separator (which is `|`), you can choose your own separator

```typescript
  import { NgxTranslateCutModule } from 'ngx-translate-cut';

  @NgModule({
   // ...
   imports: [
     // ...
     NgxTranslateCutModule.forRoot({
      // Your separator in translation strings will be `*`
      separator: '*'
    }),
   ]
  })
```

## Dependencies

[@ngx-translate/core](https://github.com/ngx-translate/core)

## 🧪 Experiments

### Angular 12 + IVY (Goodbye ngcc)

If you're brave enough, you can play with the experimental version, which is only compiled with IVY and fully supports Angular12+ (you can't use this with older Angular version anymore)

```bash
yarn add ngx-translate-cut@ng12
# npm install ngx-translate-cut@ng12 --save
```

Branch: [ng12](https://github.com/bartholomej/ngx-translate-cut/tree/ng12)

## Development (notes for me)

### Publish Stable

```shell
yarn release:patch
# yarn release:minor
# yarn release:major
```

### Publish next channel

1. Bump version `-beta.0` in `package.json`
2. `yarn publish:next`

## License

Copyright &copy; 2021 [Lukas Bartak](http://bartweb.cz)

Proudly powered by nature 🗻, wind 💨, tea 🍵 and beer 🍺 ;)

All contents are licensed under the [MIT license].

[mit license]: LICENSE

## Donation

If this project have helped you save time please consider [making a donation](https://github.com/sponsors/bartholomej) for some 🍺 or 🍵 ;)

## Thanks to

Original idea comes from: [@yuristsepaniuk](https://github.com/yuristsepaniuk) in [this thread](https://github.com/ngx-translate/core/issues/223).
