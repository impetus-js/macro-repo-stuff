# Core Repo
- [Core Repo](#core-repo)
  - [Macro Repos](#macro-repos)
  - [Packages](#packages)
    - [Documentation / Website](#documentation--website)
    - [Core / Kernel](#core--kernel)
    - [Configurations](#configurations)
    - [Deployment packages](#deployment-packages)
    - [Package management libraries](#package-management-libraries)
    - [IDE plugins (eg Visual Studio Code)](#ide-plugins-eg-visual-studio-code)
    - [Development tools](#development-tools)
      - [Code Generators](#code-generators)
      - [Packages](#packages-1)
      - [Articles](#articles)
    - [Default Libraries](#default-libraries)

I'm using this document to explain all the functionality that this framework provides but as packages. The intent is to break down all the functionality by packages as I find this an easier method because I am a visual thinker. From thre I plan to describe the percieved required functionality so it is easier to explain this repo's purpose & features, how it works and why I feel this is the future of enterprise development. 

> [`NOTE`]: This repo assumes TypeScript as that is my preferred language. 

All features are broken down into macro-repos. The examples below do not include the full folder structure for each repo just the packages within. The headings are the names of each macro-repo. To see their folders in more detail open the [_example-macro-repo](./_example-macro-repo.zip) archive.

## Macro Repos
All macro-repos have the same top-level structure:
```
macro-repo-name
  _docs
  apps
  packages
    _main
    _public # A package that is public that exports
            # the packages in here. Managed by the framework
    ...
  configs
  scripts
  README.md
  pnpm-workspace.yaml
  package.json
```

## Packages
The macro-repo framework packages.

### Documentation / Website
This could be an [11ty](https://www.11ty.dev/) statically built website. I would love for this to be automatic but that wouldn't work here.
```
_docs
  11ty
    configs
    public
    css
    layouts
    data
  content
```

### Core / Kernel
Core functionality for the framework. You can think of this as the `kernal` or `main()` for the framework.

```
kernel
  client-configs
  infra
  runners
  testing
  front-end
  back-end
  # macro-repo
```

### Configurations
This repo's packages are all about configurations for each tool that the framework uses and derived repos that are created for your projects. It also includes packages for organizations to make their own configurations.

```
_main # Export all the configurations
overrides # A way for organizations to create their own configurations
loader # The configurations loader

# Tools
editorconfig
eslint-base
eslint-client
eslint-tsx
eslint-typescript
git
graphql
IO (prisma, file, db, urls, logging)
javascript
jest/ava
mfes -> SPA apps
prettier
react
rollup
server
thunder-client
typescript
webpack
yaml-json
```

### Deployment packages
Packages to manage repo deployments to various types of platforms

```
configurations
  client-configs
  infra
  runner
  testing
  web
```

### Package management libraries
Libraries to handle package management. I think this would make more sense in the `./tools` repo.

```
package-management
  bundler-logger
  bundler-prod-cleaner
  bundler-testing
```

### IDE plugins (eg Visual Studio Code)
Some packages to make development easier with the repo framework in people's favorite IDEs such as Visual Studio Code.

```
ide-plugins
  vscode-logger-highlighter
  vscode-macro-repo
  vscode-preferences
  vscode-test-opener
```

### Development tools
Tools to makde development easier. These are loaders, package generators, clis and `codemods` to modify packages automatically.

#### Code Generators

#### Packages
- [`liquidjs`](https://www.npmjs.com/package/liquidjs)
- [`mitem`](https://www.npmjs.com/package/mitem)
- [`eta`](https://www.npmjs.com/package/eta)
- [`waterpipe`](https://www.npmjs.com/package/waterpipe)
- [`Hygen`](https://www.hygen.io/)
- [EJS](https://ejs.co/)

#### Articles
- [TypeScript code generation using it’s compiler API](https://shadeglare.medium.com/typescript-code-generation-using-its-compiler-api-4c50ad9f7884)
- [handlebars-lang/handlebars.js: Minimal templating on steroids.](https://github.com/handlebars-lang/handlebars.js)


```
tools
  auto-loader
  clis
  generator-app
  generator-ci-cd
  generator-client-config
  generator-infra
  generator-lambda
  generator-lib
  generator-macro-repo
  generator-service
  # loggers
  # parcel
  # testing
```

### Default Libraries