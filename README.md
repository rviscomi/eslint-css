# ESLint CSS Language Plugin

## Overview

This package contains a plugin that allows you to natively lint CSS files using ESLint.

**Important:** This plugin requires ESLint v9.6.0 or higher and you must be using the [new configuration system](https://eslint.org/docs/latest/use/configure/configuration-files).

## Installation

For Node.js and compatible runtimes:

```shell
npm install @eslint/css -D
# or
yarn add @eslint/css -D
# or
pnpm install @eslint/css -D
# or
bun install @eslint/css -D
```

For Deno:

```shell
deno add @eslint/css
```

### Configurations

| **Configuration Name** | **Description**                |
| ---------------------- | ------------------------------ |
| `recommended`          | Enables all recommended rules. |

In your `eslint.config.js` file, import `@eslint/css` and include the recommended config:

```js
// eslint.config.js
import css from "@eslint/css";

export default [
	// lint CSS files
	{
		files: ["**/*.css"],
		language: "css/css",
		...css.configs.recommended,
	},

	// your other configs here
];
```

### Rules

<!-- NOTE: The following table is autogenerated. Do not manually edit. -->

<!-- Rule Table Start -->

| **Rule Name**                                                    | **Description**                  | **Recommended** |
| :--------------------------------------------------------------- | :------------------------------- | :-------------: |
| [`no-duplicate-imports`](./docs/rules/no-duplicate-imports.md)   | Disallow duplicate @import rules |       yes       |
| [`no-empty-blocks`](./docs/rules/no-empty-blocks.md)             | Disallow empty blocks            |       yes       |
| [`no-invalid-at-rules`](./docs/rules/no-invalid-at-rules.md)     | Disallow invalid at-rules        |       yes       |
| [`no-invalid-properties`](./docs/rules/no-invalid-properties.md) | Disallow invalid properties      |       yes       |
| [`use-layers`](./docs/rules/use-layers.md)                       | Require use of layers            |       no        |

<!-- Rule Table End -->

**Note:** This plugin does not provide formatting rules. We recommend using a source code formatter such as [Prettier](https://prettier.io) for that purpose.

In order to individually configure a rule in your `eslint.config.js` file, import `@eslint/css` and configure each rule with a prefix:

```js
// eslint.config.js
import css from "@eslint/css";

export default [
	{
		files: ["**/*.css"],
		plugins: {
			css,
		},
		language: "css/css",
		rules: {
			"css/no-empty-blocks": "error",
		},
	},
];
```

You can individually config, disable, and enable rules in CSS using comments, such as:

<!-- prettier-ignore -->
```css
/* eslint css/no-empty-blocks: error */

/* eslint-disable css/no-empty-blocks -- this one is ok */
a {
}
/* eslint-enable css/no-empty-blocks */

b { /* eslint-disable-line css/no-empty-blocks */
}

/* eslint-disable-next-line css/no-empty-blocks */
em {
}
```

### Languages

| **Language Name** | **Description**        |
| ----------------- | ---------------------- |
| `css`             | Parse CSS stylesheets. |

In order to individually configure a language in your `eslint.config.js` file, import `@eslint/css` and configure a `language`:

```js
// eslint.config.js
import css from "@eslint/css";

export default [
	{
		files: ["**/*.css"],
		plugins: {
			css,
		},
		language: "css/css",
		rules: {
			"css/no-empty-blocks": "error",
		},
	},
];
```

By default, the CSS parser runs in strict mode, which reports all parsing errors. If you'd like to allow recoverable parsing errors (those that the browser automatically fixes on its own), you can set the `tolerant` option to `true`:

```js
// eslint.config.js
import css from "@eslint/css";

export default [
	{
		files: ["**/*.css"],
		plugins: {
			css,
		},
		language: "css/css",
		languageOptions: {
			tolerant: true,
		},
		rules: {
			"css/no-empty-blocks": "error",
		},
	},
];
```

Setting `tolerant` to `true` is necessary if you are using custom syntax, such as [PostCSS](https://postcss.org/) plugins, that aren't part of the standard CSS syntax.

## License

Apache 2.0

<!-- NOTE: This section is autogenerated. Do not manually edit.-->
<!--sponsorsstart-->

## Sponsors

The following companies, organizations, and individuals support ESLint's ongoing maintenance and development. [Become a Sponsor](https://eslint.org/donate)
to get your logo on our READMEs and [website](https://eslint.org/sponsors).

<h3>Platinum Sponsors</h3>
<p><a href="https://automattic.com"><img src="https://images.opencollective.com/automattic/d0ef3e1/logo.png" alt="Automattic" height="128"></a> <a href="https://www.airbnb.com/"><img src="https://images.opencollective.com/airbnb/d327d66/logo.png" alt="Airbnb" height="128"></a></p><h3>Gold Sponsors</h3>
<p><a href="https://trunk.io/"><img src="https://images.opencollective.com/trunkio/fb92d60/avatar.png" alt="trunk.io" height="96"></a></p><h3>Silver Sponsors</h3>
<p><a href="https://www.serptriumph.com/"><img src="https://images.opencollective.com/serp-triumph5/fea3074/logo.png" alt="SERP Triumph" height="64"></a> <a href="https://www.jetbrains.com/"><img src="https://images.opencollective.com/jetbrains/fe76f99/logo.png" alt="JetBrains" height="64"></a> <a href="https://liftoff.io/"><img src="https://images.opencollective.com/liftoff/5c4fa84/logo.png" alt="Liftoff" height="64"></a> <a href="https://americanexpress.io"><img src="https://avatars.githubusercontent.com/u/3853301" alt="American Express" height="64"></a></p><h3>Bronze Sponsors</h3>
<p><a href="https://cybozu.co.jp/"><img src="https://images.opencollective.com/cybozu/933e46d/logo.png" alt="Cybozu" height="32"></a> <a href="https://www.crosswordsolver.org/anagram-solver/"><img src="https://images.opencollective.com/anagram-solver/2666271/logo.png" alt="Anagram Solver" height="32"></a> <a href="https://icons8.com/"><img src="https://images.opencollective.com/icons8/7fa1641/logo.png" alt="Icons8" height="32"></a> <a href="https://discord.com"><img src="https://images.opencollective.com/discordapp/f9645d9/logo.png" alt="Discord" height="32"></a> <a href="https://www.gitbook.com"><img src="https://avatars.githubusercontent.com/u/7111340" alt="GitBook" height="32"></a> <a href="https://nx.dev"><img src="https://avatars.githubusercontent.com/u/23692104" alt="Nx" height="32"></a> <a href="https://opensource.mercedes-benz.com/"><img src="https://avatars.githubusercontent.com/u/34240465" alt="Mercedes-Benz Group" height="32"></a> <a href="https://herocoders.com"><img src="https://avatars.githubusercontent.com/u/37549774" alt="HeroCoders" height="32"></a></p>
<h3>Technology Sponsors</h3>
Technology sponsors allow us to use their products and services for free as part of a contribution to the open source ecosystem and our work.
<p><a href="https://netlify.com"><img src="https://raw.githubusercontent.com/eslint/eslint.org/main/src/assets/images/techsponsors/netlify-icon.svg" alt="Netlify" height="32"></a> <a href="https://algolia.com"><img src="https://raw.githubusercontent.com/eslint/eslint.org/main/src/assets/images/techsponsors/algolia-icon.svg" alt="Algolia" height="32"></a> <a href="https://1password.com"><img src="https://raw.githubusercontent.com/eslint/eslint.org/main/src/assets/images/techsponsors/1password-icon.svg" alt="1Password" height="32"></a></p>
<!--sponsorsend-->
