# Vue Vite Template

A project created with Vue 3 + TypeScript + Vite + ESLint + Prettier and `<setup script>` syntax

## Instructions

- Start with `npm i` to install all dependencies and rules
- To serve `npm run dev`
- Check the `Train of Thought` section to understand why and have all addons needed
- Change `HelloWorld.vue` code to see your IDE reacting to the linter rules

## Train of Thought

1. Create an application with VITE

```
npm create vite@latest
```

2. Use VSCode extensions:

- ESLint
- Prettier - Code formatter
- Volar

3. Follow VITE suggestions and use `<script setup>`, to be able to do so: disable in the current Workspace any other Vue tool like `Vetur` and even the built-in `TypeScript and JavaScript Language Features`.

4. Install `eslint`

```
npm install --save-dev eslint eslint-plugin-vue @vue/eslint-config-typescript vue-eslint-parser
```

Add configuration information in `package.json`

```
  "eslintConfig": {
    "root": true,
    "env": {
      "node": true,
      "vue/setup-compiler-macros": true
    },
    "parser": "vue-eslint-parser",
    "extends": [
      "eslint:recommended",
      "plugin:vue/vue3-recommended",
      "@vue/typescript/recommended"
    ],
    "parserOptions": {
      "ecmaVersion": 2022
    },
    "rules": {}
  }
```

5. Install `prettier`

```
npm i --save-dev prettier eslint-config-prettier eslint-plugin-prettier
```

And add the configurations extensions
```
    "extends": [
      ...<other rules>...
      "plugin:prettier/recommended"
    ],
```

6. Detailed Explanation:
- To avoid variables not used error inside `<script setup>` and to be able to use `defineProps` and other functions that are injected inside the setup, we use vue parser `"parser": "vue-eslint-parser",` version 9 or above.
- For Prettier work ok with typescript and vue3+setup, we add `"@vue/eslint-config-typescript"`

- Documentation:
https://eslint.vuejs.org/rules/script-setup-uses-vars.html


https://eslint.vuejs.org/user-guide/#compiler-macros-such-as-defineprops-and-defineemits-generate-no-undef-warnings

