# Project Dot Files

Editor Config, Husky Git Hooks, Lint Staged, Prettier, ESLint, TSLint,
Stylelint, MarkdownLint and more!

**Note:** NOT FINALIZED

## Installation

```bash
git clone https://github.com/jamesblackjr/project-dot-files.git new-project-folder

cd new-project-folder && rm -rf .git && git init
```

## EditorConfig Configuration

.editorconfig:

```yaml
root = true

[*]
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
end_of_line = lf
# editorconfig-tools is unable to ignore longs strings or urls
max_line_length = null
```

## Husky Git Hooks Configuration

.huskyrc.json:

```json
{
  "hooks": {
    "pre-commit": "lint-staged"
  }
}
```

## Lint Staged Configuration

.lintstagedrc.json:

```json
{
  "*.{js,jsx}": [
    "pretter --write",
    "eslint --fix",
    "git add"
  ],
  "*.{ts,tsx}": [
    "pretter --write",
    "tslint --fix",
    "git add"
  ],
  "*.{css,less,scss}": [
    "pretter --write",
    "stylelint --fix",
    "git add"
  ],
  "*.{html,hbs,json,graphql,toml,xml,yml,yaml}": [
    "prettier --write",
    "git add"
  ]
}
```

## Prettier Configuration

.prettierrc.json:

```json
{
  "trailingComma": "es5",
  "tabWidth": 2,
  "printWidth": 100,
  "semi": false,
  "singleQuote": true
}
```

## ESLint Configuration

.eslintrc.json:

```json
{
  "extends": ["airbnb", "prettier"],
  "plugins": ["prettier", "json"],
  "rules": {
    "prettier/prettier": ["error"]
  }
}
```

## TSLint Configuration

tslint.json:

```json
{
  "extends": "tslint:recommended",
  "rulesDirectory": [],
  "rules": {
    "max-line-length": {
      "options": [120]
    },
    "new-parens": true,
    "no-arg": true,
    "no-bitwise": true,
    "no-conditional-assignment": true,
    "no-consecutive-blank-lines": false,
    "no-console": {
      "severity": "warning",
      "options": ["debug", "info", "log", "time", "timeEnd", "trace"]
    }
  },
  "jsRules": {
    "max-line-length": {
      "options": [120]
    }
  }
}
```

## Stylelint Configuration

.stylelintrc.json:

```json
{
  "extends": "stylelint-config-recommended"
}
```

## MarkdownLint Configuration

.markdownlint.json:

```json
{
  "default": true,
  "MD003": { "style": "atx" },
  "MD007": { "indent": 2 },
  "no-hard-tabs": false,
  "whitespace": false
}
```
