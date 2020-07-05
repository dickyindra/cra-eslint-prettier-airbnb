# Create React App with Eslint + Prettier + Airbnb Style Guide

1. Create a new React JS with Create React App project or using existing project.

```
$ npx create-react-app <project-directory>
```

2. Integrating Airbnb Style Guide config with Eslint.

```
$ npm i -D eslint-config-airbnb
```

Edit file package.json and add Airbnb in Eslint config.

```
"eslintConfig": {
	"extends": ["react-app", "airbnb"]
},
```

4. Integrating Prettier with Eslint.

```
$ npm i -D prettier eslint-config-prettier eslint-plugin-prettier
```

Edit file package.json and add Prettier in Eslint config.

```
"extends": [
	"plugin:react/recommended",
	"airbnb",
	"prettier"
],
"plugins": [
	"react",
	"prettier"
],
"rules": {
	"prettier/prettier": ["error"]
}
```

Create a .prettierrc file for Prettier configuration file.

I using prettier configuration from:
[https://gist.github.com/dickyindra/59ba86d455fc0f757ab9f76bead155ca](https://gist.github.com/dickyindra/59ba86d455fc0f757ab9f76bead155ca).

```
{
	"arrowParens": "avoid",
	"bracketSpacing": true,
	"htmlWhitespaceSensitivity": "ignore",
	"insertPragma": false,
	"jsxBracketSameLine": false,
	"jsxSingleQuote": false,
	"printWidth": 80,
	"proseWrap": "preserve",
	"quoteProps": "as-needed",
	"requirePragma": false,
	"semi": false,
	"singleQuote": true,
	"tabWidth": 2,
	"trailingComma": "es5",
	"useTabs": false
}
```

## Husky + Lint-Staged + Pre-commit Hooks

1. Edit file package.json and add fix Eslint & Prettier script.

```
"scripts": {
	"start": "react-scripts start",
	"build": "react-scripts build",
	"test": "react-scripts test",
	"eject": "react-scripts eject",
	"lint": "eslint src/**/*.js",
	"lint:fix": "eslint src/**/*.js --fix",
	"prettier": "prettier --check src/**/*.js",
	"prettier:fix": "prettier --write src/**/*.js"
},
```

2. Install & Integration Husky + Lint-Staged + Pre-commit Hooks

```
npm i -D husky lint-staged
```

Edit file package.json:

```
"husky": {
	"hooks": {
		"pre-commit": "lint-staged --allow-empty"
	}
},
"lint-staged": {
	"*.js": [
		"npm run lint:fix",
		"npm run prettier:fix",
		"git add"
	]
},
```
