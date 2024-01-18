# Day1: Setup Prettier and ESLint

## Install Dependencies
```bash
yarn add --dev eslint
yarn add --dev eslint-config-next
yarn add --dev @next/eslint-plugin-next
yarn add --dev @typescript-eslint/eslint-plugin
yarn add --dev prettier
yarn add --dev eslint-config-prettier
```

## Prettier
- Create a `.prettierrc.json` file
```json
{
	"printWidth": 100,
	"tabWidth": 2,
	"semi": false,
	"singleQuote": true,
	"bracketSameLine": false,
	"trailingComma": "es5",
	"bracketSpacing": true,
	"arrowParens": "avoid",
	"parser": "typescript"
}
```

## ESLint
- Install [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) plugin in VSCode extension to make eslint errors visible in VSCode

- Create `.eslintrc.json`
```json
{
  "plugins": [
    "@typescript-eslint"
  ],
  "extends": [
    "next/core-web-vitals",
    "plugin:@typescript-eslint/recommended",
    "prettier"
  ],
  "rules": {
    "@typescript-eslint/no-unused-vars": "error",
    "@typescript-eslint/no-explicit-any": "error"
  }
}
```

- Add ESLint script
```json
{
  "scripts": {
    // ...
    "lint": "next lint",
    // ...
  },
}
```

## VSCode
- Add setting below to `.vscode/settings.json`
  - Auto-fix eslint errors on save
  - Use `Prettier` as default file formatter
  - Format files on save
```json
{
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode"
}
```