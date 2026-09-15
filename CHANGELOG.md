# @nomansheikh/nestjs-stoplight-elements

## 1.3.0

### Minor Changes

- f93e0ba: Correct the dependency declarations in `package.json`.

  The package previously shipped three runtime `dependencies` it does not import. The compiled output only ever requires `express-handlebars` and Node's built-in `path`.

  - `eslint-plugin-prettier` moved to `devDependencies`. It is an ESLint plugin used by `gts lint`, not a runtime dependency. It has to stay declared at the project root because ESLint 8 resolves plugins relative to the project, not to the config that references them.
  - `install` removed. It was never used and was added by accident.
  - `@nestjs/platform-express` moved from `dependencies` to `peerDependencies`. The module reaches the HTTP layer through `app.getHttpAdapter()` and never imports the package, so installing its own copy risked pulling a second HTTP platform into consumer apps. Applications running NestJS on Express already provide it.

## 1.2.0

### Minor Changes

- 3cce911: add missing tryItCredentialsPolicy to the handlebars config

## 1.1.0

### Minor Changes

- c611576: add tryItCredentialsPolicy option

## 1.0.0

### Major Changes

- 0c3fb6c: Inital release
