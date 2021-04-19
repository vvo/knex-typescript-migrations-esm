# TypeScript + Knex + ESM modules

This project demonstrates that requiring ESM modules inside a TypeScript Knex migration fails.

```sh
npm install
./node_modules/.bin/knex migrate:latest

Error [ERR_REQUIRE_ESM]: Must use import to load ES Module: /Users/[redacted]/knex-typescript-migrations-esm/node_modules/random-int/index.js
require() of ES modules is not supported.
require() of /Users/[redacted]/knex-typescript-migrations-esm/node_modules/random-int/index.js from /Users/[redacted]/knex-typescript-migrations-esm/migrations/20210419131555_test.ts is an ES module file as it is a .js file whose nearest parent package.json contains "type": "module" which defines all .js files in that package scope as ES modules.
Instead rename index.js to end in .cjs, change the requiring code to use import(), or remove "type": "module" from /Users/[redacted]/knex-typescript-migrations-esm/node_modules/random-int/package.json.

    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1080:13)
    at Module.load (internal/modules/cjs/loader.js:928:32)
    at Function.Module._load (internal/modules/cjs/loader.js:769:14)
    at Module.require (internal/modules/cjs/loader.js:952:19)
    at require (internal/modules/cjs/helpers.js:88:18)
    at Object.<anonymous> (/Users/[redacted]/knex-typescript-migrations-esm/migrations/20210419131555_test.ts:2:1)
    at Module._compile (internal/modules/cjs/loader.js:1063:30)
    at Module.m._compile (/Users/[redacted]/knex-typescript-migrations-esm/node_modules/ts-node/src/index.ts:1056:23)
    at Module._extensions..js (internal/modules/cjs/loader.js:1092:10)
    at Object.require.extensions.<computed> [as .ts] (/Users/[redacted]/knex-typescript-migrations-esm/node_modules/ts-node/src/index.ts:1059:12)
```