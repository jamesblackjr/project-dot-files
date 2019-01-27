# Project Dot Files

Editor Config, Husky Git Hooks, Lint Staged, Prettier, ESLint, TSLint,
Stylelint, MarkdownLint and more!

**Note:** NOT FINALIZED

## Installation

```bash
git clone https://github.com/jamesblackjr/project-dot-files.git new-project-folder

cd new-project-folder

rm -rf .git && git init
```

...or you can copy individual dot files into your project.

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
  "*.{js,jsx,json}": [
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
  "*.{html}": [
    "pretter --write",
    "htmllint",
    "git add"
  ],
  "*.{graphql}": [
    "pretter --write",
    "gqlint",
    "git add"
  ],
  "*.{md}": [
    "pretter --write",
    "markdownlint",
    "git add"
  ],
  "*.{hbs,toml,xml,yml,yaml}": [
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

## GQLint (GraphQL Linter) Configuration

.gqlint.json:

```json
{
  "rules": {
    "camelcase": "warn",
    "fieldname.typename": "warn",
    "relay.connection": "warn",
    "relay.id": "warn",
    "singular.mutations": "warn",
    "enum.casing": "warn",
    "description.type": "off",
    "description.field": "off"
  }
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

## HTML Lint Configuration

.htmllintrc.json:

```json
{
  "attr-bans": [
    "align",
    "background",
    "bgcolor",
    "border",
    "frameborder",
    "longdesc",
    "marginwidth",
    "marginheight",
    "scrolling",
    "style",
    "width"
  ],
  "attr-name-ignore-regex": false,
  "attr-name-style": "dash",
  "attr-new-line": "+0",
  "attr-no-dup": true,
  "attr-no-unsafe-char": true,
  "attr-order": false,
  "attr-quote-style": "double",
  "attr-req-value": true,
  "attr-validate": true,
  "class-no-dup": true,
  "class-style": "dash",
  "doctype-first": "smart",
  "doctype-html5": true,
  "fig-req-figcaption": false,
  "focusable-tabindex-style": false,
  "head-req-title": true,
  "head-valid-content-model": true,
  "href-style": "relative",
  "html-req-lang": true,
  "html-valid-content-model": true,
  "id-class-ignore-regex": false,
  "id-class-no-ad": false,
  "id-class-style": "dash",
  "id-no-dup": true,
  "img-req-alt": "allownull",
  "img-req-src": true,
  "indent-style": "spaces",
  "indent-width": 4,
  "indent-width-cont": true,
  "input-radio-req-name": true,
  "input-req-label": true,
  "label-req-for": true,
  "lang-style": "case",
  "line-end-style": "lf",
  "line-max-len": 120,
  "line-max-len-ignore-regex": false,
  "maxerr": false,
  "raw-ignore-regex": false,
  "spec-char-escape": true,
  "table-req-caption": false,
  "table-req-header": true,
  "tag-bans": ["style", "b", "i"],
  "tag-close": false,
  "tag-name-lowercase": true,
  "tag-name-match": false,
  "tag-self-close": "never",
  "text-ignore-regex": false,
  "title-max-len": 60,
  "title-no-dup": true
}
```
