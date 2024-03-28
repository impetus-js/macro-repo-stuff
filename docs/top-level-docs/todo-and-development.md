# TODO & Development
- [TODO \& Development](#todo--development)
  - [Documentation](#documentation)
  - [Development](#development)
    - [Create a code runner](#create-a-code-runner)
      - [What](#what)
      - [Results](#results)
    - [Generators](#generators)
      - [What](#what-1)
      - [Results](#results-1)
    - [Codemods](#codemods)
      - [What](#what-2)
      - [Results](#results-2)
    - [Configurations \& Tools](#configurations--tools)
      - [What](#what-3)
      - [Results](#results-3)
    - [~~Further IoC exploration~~](#further-ioc-exploration)
      - [What](#what-4)
      - [Results](#results-4)
    - [Package Management](#package-management)
      - [What](#what-5)
      - [Results](#results-5)
    - [Core libraries](#core-libraries)
      - [What](#what-6)
      - [Results](#results-6)
    - [Repo Exploration](#repo-exploration)
      - [What](#what-7)
      - [Results](#results-7)
    - [Misc](#misc)
      - [What](#what-8)
      - [Results](#results-8)

## Documentation
- [ ] I have some repeating stuff. Let's clean that up
- [ ] Consolidate the documents

## Development
### Create a code runner
The code runner(s) are packages that autoloads files, modifies code dynamically and allows for bundling into a single file. Maybe also use `injectable-js` for IoC but this may be unnessessary since that code would require to have the params & types.

Some options:
- [`@rollup/plugin-inject`](https://github.com/rollup/plugins/tree/master/packages/inject).
     - It uses a tree walker (`AST`) so this looks like it would be the best example to autopsy.
   - Has a cache, es conversion: [`@rollup/plugin-graphql`](https://github.com/rollup/plugins/tree/master/packages/graphql)
- Follow `turbo.build`'s pattern and write a `rust` plugin or something
  - I really don't want to have to do this

#### What
- [ ] Write a `rollup.js` plugin
  - Adds all the `imports` dynamically
    - I believe that it will be a string so I would like to use aliases but really isn't nessessary
  - Uses an AST to modify the code
  - Since it'll be a single file bundle it should work fine
- [ ] Write it for a simple library/package
- [ ] Setup default configs that a runner & bundler would use
- [ ] Scripts to run the code 
  - Similar to `react-scripts`
- [ ] Follows pre-defined paths
- [ ] Compiles code differently depending on file type (by folder)
- [ ] Runs certain configs from configs that aren't within the runner package
  - Run them via configs for executable scripts
  - Package configs to auto run
    - `eslint`
    - `jest`
    - `tsconfig.json`
    - `prettier`
    - `dotenv`
    - `rollup`

#### Results
`N/A`

### Generators
A script/bin that would create code, packages, apps & macrorepos

Explore the following template engines
- [`liquidjs`](https://www.npmjs.com/package/liquidjs)
- [`mitem`](https://www.npmjs.com/package/mitem)
- [`eta`](https://www.npmjs.com/package/eta)
- [`waterpipe`](https://www.npmjs.com/package/waterpipe)
- [`Hygen`](https://www.hygen.io/)
- [EJS](https://ejs.co/)

#### What
- [ ] Investigate and test out some generator packages
- [ ] Create a package generator
- [ ] Generate a package
  - By type
  - Follows a pattern

#### Results
`N/A`

### Codemods
Learn how to create/write a code mod. Codemods will let me create scripts that will modify code. For instance adding a new `import` statement and such. Also to have automatic upgrades.

- [A Step-by-Step Guide to Using jscodeshift with TypeScript](https://www.dhiwise.com/post/the-ultimate-guide-to-using-jscodeshift-with-typescript)
- [ts-migrate: A Tool for Migrating to TypeScript at Scale](https://medium.com/airbnb-engineering/ts-migrate-a-tool-for-migrating-to-typescript-at-scale-cd23bfeb5cc)
- [Automating Refactoring with Codemod](https://malcolmkee.com/blog/automating-refactoring-with-codemod/)
- [My Workflow for Codemods](https://www.skovy.dev/blog/codemod-workflow?seed=9jela9)
- [An introduction to codemods](https://nicknisi.com/posts/codemods-introduction/)

#### What
- [ ] Be able to modify a file
  - Modify the body of a predefined function to add new code
- [ ] Add a package(s) to an app in the `./app/{app}` directory.

#### Results
`N/A`

### Configurations & Tools
Configurations that are set in one package used by the runner and other functionality like deployments and generators.

#### What
- [ ] Ability to override configs
  - ???
- [ ] Create a package with a configs & tools directory
  - `ESLint`
  - `Jest`
  - `dotenv`
  - `typescript`
  - `Express` (or some other)

#### Results
`N/A`

### ~~Further IoC exploration~~
#### What
- [x] Further investigate `injectable-js`
  - ~~See how to do nested dependencies work~~
  - ~~Test with my [`express-autoloader`](https://github.com/mrpotatoes/express-autoloader/) package~~

#### Results
- `injectable-js` satisfies the IoC requirements I had
  - Nested deps aren't important but
    - `token()`s are global so I can pull any as long as the token name is unique
  - It won't work with `express-autoloader`
    - Package can't compile to a single file because of the dynamic `require()`s/`import()`s

### Package Management
#### What
- [ ] Test the [`ts-import`](https://www.npmjs.com/package/ts-import) bundler 
  - Test with the [`express-autoloader`](https://github.com/mrpotatoes/express-autoloader/) package to see if it will bundle everything together
- [ ] Test some other autoloaders
  - https://www.npmjs.com/package/@jymfony/autoloader
  - https://www.npmjs.com/package/consign-ignore
  - https://www.npmjs.com/package/envk
  - https://www.npmjs.com/package/@amazeelabs/codegen-autoloader

#### Results
`N/A`

### Core libraries
#### What
- [ ] Create a core library
  - URL dependency
- [ ] The import ignore thing to keep stuff clean n' such

#### Results
`N/A`

### Repo Exploration
#### What
- [ ] Look more into mono repo examples

#### Results
`N/A`

### Misc
#### What
- [ ] API Gateway

#### Results
`N/A`
