# eslint-plugin-disable-autofix

Disable ESLint autofix (--fix) for specified rules and prevent them from being
formatted, without turning them off

## Usage

### Install

```shell
npm i -D eslint-plugin-disable-autofix
```

### Configure

Add prefix `disable-autofix/` to the rule in eslintrc and disable the original

```js
module.exports = {
  plugins: ['disable-autofix'],
  rules: {
    'prefer-const': 'off',
    'disable-autofix/prefer-const': 'warn',
  },
};
```

Use 3rd-party plugins

```js
module.exports = {
  plugins: ['disable-autofix', 'react'],
  rules: {
    'react/jsx-indent': 'off',
    'disable-autofix/react/jsx-indent': 'error',
  },
};
```

Use scoped plugins

```js
module.exports = {
  plugins: ['disable-autofix', '@html-eslint'],
  rules: {
    '@html-eslint/require-closing-tags': 'off',
    'disable-autofix/@html-eslint/require-closing-tags': [
      'error',
      { selfClosing: 'always' },
    ],
  },
};
```
