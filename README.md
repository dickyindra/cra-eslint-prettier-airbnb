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
