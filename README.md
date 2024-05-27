# Prettier <!-- omit in toc -->

## Overview

[Prettier](https://prettier.io/) is an opinionated code formatter.

- [Homepage](https://prettier.io/)
- [Online playground](https://prettier.io/playground/)

## Install

1. Install latest Prettier.

```shell
npm install --save-dev --save-exact prettier
```

1. Add `.prettierignore`. Prettier will follow rules in `.gitignore`

```js
# Ignore artifacts:
build
coverage
```

## Usage

- To check all files:

```shell
npx prettier . --check
```

- To format all files:

```shell
npx prettier . --write
```

## Configuration

Prettier will search for a configuration file in the following order:

- `prettier` key in your package.json file.
- `.prettierrc` file written in JSON or YAML.
- `.prettierrc.json`, `.prettierrc.yml`, `.prettierrc.yaml`, or `.prettierrc.json5` file.
- `.prettierrc.js`, or `prettier.config.js` file that exports an object using export default or module.exports (depends on the type value in your `package.json`).
- `.prettierrc.mjs`, or `prettier.config.mjs` file that exports an object using export default.
- `.prettierrc.cjs`, or `prettier.config.cj`s file that exports an object using module.exports.
- `.prettierrc.toml` file.

Many values will inherit from `.editorconfig`, if it exists.

## Ignoring code

- Use globs in `.prettierignore`

```ini
# Ignore artifacts:
build
coverage

# Ignore all HTML files:
**/*.html
```

- Using the CLI

```shell
prettier . "!**/*.{js,jsx,vue}" --write
```

- Use comments in JavaScript

```js
// prettier-ignore
matrix(
  1, 0, 0,
  0, 1, 0,
  0, 0, 1
)
```

- Use comments in JSX

```jsx
<div>
  {/* prettier-ignore */}
  <span     ugly  format=''   />
</div>
```

- Use comments in HTML

```html
<!-- prettier-ignore -->
<div         class="x"       >hello world</div            >
```

- Use comments in CSS

```css
/* prettier-ignore */
.my    ugly rule
{

}
```

- Use comments in Markdown

```md
<!-- prettier-ignore -->
Do   not    format   this
```

- Use comments in YAML

```yml
# prettier-ignore
key  : value
hello: world
```

## VSCode

- `esbenp.prettier-vscode`

```json
{
  "prettier.prettierPath": "./node_modules/prettier",
  "prettier.enable": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
}
```
