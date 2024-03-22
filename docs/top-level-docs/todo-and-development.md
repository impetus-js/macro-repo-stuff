# TODO & Development
- [TODO \& Development](#todo--development)
  - [Development](#development)
    - [Further IoC exploration](#further-ioc-exploration)
    - [Configurations \& Tools](#configurations--tools)
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
