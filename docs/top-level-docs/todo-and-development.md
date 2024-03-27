# TODO & Development
- [TODO \& Development](#todo--development)
  - [Development](#development)
    - [Further IoC exploration](#further-ioc-exploration)
    - [Configurations \& Tools](#configurations--tools)
    - [Codemods](#codemods)
    - [Create a code runner](#create-a-code-runner)
    - [Package Management](#package-management)
    - [Core libraries](#core-libraries)
    - [Generators](#generators)
    - [Repo Exploration](#repo-exploration)
    - [Misc](#misc)

## Development
### Further IoC exploration
- Further test `injectable-js`
  - See how to do nested dependencies work
  - Test with my [`express-autoloader`](https://github.com/mrpotatoes/express-autoloader/) package
- Maybe see if the autoloader can handle some of the injection itself like my [`express-autoloader`](https://github.com/mrpotatoes/express-autoloader/)?

### Configurations & Tools
- Create a package with a configs & tools directory
  - `ESLint`
  - `Jest`
  - `dotenv`
  - `typescript`
  - `Express` (or some other)
  - 

### Codemods
Learn how to create/write a code mod. Codemods will let me create scripts that will modify code. For instance adding a new `import` statement and such. Also to have automatic upgrades.

- [A Step-by-Step Guide to Using jscodeshift with TypeScript](https://www.dhiwise.com/post/the-ultimate-guide-to-using-jscodeshift-with-typescript)
- [ts-migrate: A Tool for Migrating to TypeScript at Scale](https://medium.com/airbnb-engineering/ts-migrate-a-tool-for-migrating-to-typescript-at-scale-cd23bfeb5cc)
- [Automating Refactoring with Codemod](https://malcolmkee.com/blog/automating-refactoring-with-codemod/)
- [My Workflow for Codemods](https://www.skovy.dev/blog/codemod-workflow?seed=9jela9)
- [An introduction to codemods](https://nicknisi.com/posts/codemods-introduction/)

### Create a code runner
- Do for frontend
- Setup default configs that a runner & bundler would use
- Scripts to run it automatically
  - Similar to `react-scripts`

### Package Management
- Test the [`ts-import`](https://www.npmjs.com/package/ts-import) bundler 
  - Test with the [`express-autoloader`](https://github.com/mrpotatoes/express-autoloader/) package to see if it will bundle everything together
- Test some other autoloaders
  - https://www.npmjs.com/package/@jymfony/autoloader
  - https://www.npmjs.com/package/consign-ignore
  - https://www.npmjs.com/package/envk
  - https://www.npmjs.com/package/@amazeelabs/codegen-autoloader

### Core libraries
- Create a core library
  - URL dependency
- The import ignore thing to keep stuff clean n' such

### Generators
- Test out some generators
- Find a generator package I like and want to use
- Create a package generator

### Repo Exploration
- Look more into mono repo examples

### Misc
- Code mods
- API Gateway?
