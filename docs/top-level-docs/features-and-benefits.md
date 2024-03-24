# Features & Benefits
- [Features \& Benefits](#features--benefits)
  - [Opinionated](#opinionated)
  - [Featues](#featues)
  - [Benefits](#benefits)
    - [Pre-defined workflows](#pre-defined-workflows)
    - [Significantly improves development times](#significantly-improves-development-times)
    - [Code \& Packages are atomic](#code--packages-are-atomic)
    - [Opinionated \& strict standards](#opinionated--strict-standards)
    - [Containers not required](#containers-not-required)
    - [Documentation](#documentation)
    - [Keeps package directories simple and clean](#keeps-package-directories-simple-and-clean)
    - [Default libraries](#default-libraries)
    - [Enhanced testing](#enhanced-testing)
    - [Entire tech stack \& platform is easily managed \& documented](#entire-tech-stack--platform-is-easily-managed--documented)
  - [When to use](#when-to-use)
  - [When not to use](#when-not-to-use)
  - [Eventually](#eventually)
  - [Footnotes](#footnotes)

> [`NOTE`]: Need to add to the "## Features" heading

## Opinionated
- Coding styles are strict requiring engineers to use provided configurations for styles and the like
- Code generation puts files in specific directories
- Files are created for each feature i.e.
  - Code
  - Routes
  - Tests
  - Docs
  - et. al.
- Code is auto-run in development
- Packages are compiled, bundled and loaded into apps for teams

## Featues
\[`N/A`]: TBD. I think the benefits section covers most of it

## Benefits
### Pre-defined workflows
 1. **`Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer hendrerit facilisis lectus, eu molestie augue faucibus sed. Sed at sodales nulla. Suspendisse auctor dolor sed massa pretium euismod`**

### Significantly improves development times
- Because engineers ONLY focus on features and testing and not configurations and setup
- Engineers are not required to 
- Upgrades of macro-repos and their packages are less traumatic
   - Everything uses the same versions of all packages
   - High test coverage

### Code & Packages are atomic
- Frontend and backend code are completely separated
- Packages are singularly focused
   - Each file has a single function
   - Packages only contain business rules
   - This makes packages incredibly lean
      - All code is separated into standardized directories
- 2 types of packages
   - A public `Main()` package that exports all the other packages
      - `@organization/package-name`
      - Public packages have `npm` formatted namespaces. These are the packages that are exported and used by apps or developers in the case of `cli` tools or generators, for example. They pull in the private packages and are, usually, automatically handled and linked. Multiple public packages can also be created with a generator
      - Organization packages set to publick to be shared external to existing macro-repo
         - These should really be in a "global" repo so that they can be shared and keeps within the concepts of this framework.
   - All other packages default to private unless otherwise specified 
      - Private packages are used as libraries to be shared ***WITHIN*** the macro-repo. THis keeps them focused on thier usecases therefore atomic. Private libraries can also have deeper namespaces which makes it easier to keep track of them i.e.
         - `@organization/subdomain/component`
         - `@organization/subdomain/service`
      - Default can be overriden
- Package-overrides are considered unmanaged and may cause issues
   - Updates et al

### Opinionated & strict standards
- Code can be auto generated
- Engineers can focus on what matters. Business logic
- Codemods are simpler
- Code is auto loaded and ran automatically
- All code follows the same styles making transition between teams seamless
   - Except for logic which will be different for each team
- Updates to packages and repos is far less painful
   - Single repo of configs to update
   - Testing packages after updates are simple

### Containers not required
- Or any other container platform to run the macro-repo platform (or entire domain) on a local machine
- This speeds up development
  - Containers repeatedly require rebuilding
    - Rebuilding slows development time
      - Which makes the engineering feedback loop frustating and slow
      - Rebuilding requires re-installing everything in containers
      - Reruns all scripts
- Working directly on the host machine speeds up development significantly
- Since all configurations are the same it wouldn't be possible for code to be run differently on the local computer to a deployed environment.
- Would have to have options to allow this for local testing

### Documentation
- API Tester
- Storybook
- Docs website (`./_docs`)
- Technical documentation

### Keeps package directories simple and clean
- Standardized directories and file names makes things easier to find
- There won't be any open source library configurations or required directories in packages

### Default libraries
- Libraries like the injected `URL` object allow for all requests & responses to be cached into a mock for testing & logs everything by default

###  Enhanced testing
- The dependencies provided by the framework are enhanced with extra functionality e.g.
   - Captures all data from all side effectual code and saves to disk e.g.
      - API call data
      - Queried SQL or GraphQL data
      - File data
      - Authorization
   - Use internal loggers to keep business logic clean(er)
   - [**Implimentation Details**]: Fixtures take an optional secondary callback parameter to determine what data requires overriding.
      - e.g. Security information, transforming to dummy data
      - Can remove properties to make Fixtures smaller if needed
      - Updating would be a flag when running code
      - Saves to package, app or predefined directory elsewhere
         - Best idea is to not commit Fixtures. Instead use a `git hook` so publish it elsewhere
         - Fixtures locally before being published is used by the package for local developmet & testing
- Therefore unit & integrated testing becomes a straight forward affair

### Entire tech stack & platform is easily managed & documented
- Since platform is fully defined & Fixtures have been gathered:
   - Entire platform can run soup-to-nuts
   - Autorization, firewalls, gateways etc are all mocked and can be used
- [**Future**] Could have an app that can handle all this
   - Using YAML & generators every package/app/etc
- Allows to draw a diagram of the platform
   - Respects platform definition

## When to use
- The benefits above seem Neato™
- Faster development, testing, getting to prod
- Entire platform is defined & documentable

## When not to use
- Do not want development or testing performance
- If your teams prefer to manage everything themselves
- Really dislike the functional programming paradigm
- Do not like the default libraries the framework provides
- Do not like the external packages used
  - i.e. [Prisma](https://www.prisma.io/)
- Do not want development or testing performance

## Eventually
- Mocks are auto-injected into any and all tests
- Macros to make code cleaner e.g
  - Logging would be a simple comment that is converted[^logging-macro] to a logging message
    - Automatically captures the severity
    - Automatically adds subdomain, package, function name, file & line
    - Automatically captures stack trace
    - Automatically provides the error message if possible
      - Would be dope if it could infer or pull from a list of error messages defined elsewhere in the package code.
- Dependencies are automatically provided

## Footnotes
- [^logging-macro]: Something along the lines of → `// Logger: {MSG}`