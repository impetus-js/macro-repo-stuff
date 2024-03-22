# Features & Benefits
- [Features \& Benefits](#features--benefits)
  - [Opinionated](#opinionated)
  - [Featues](#featues)
  - [Benefits](#benefits)
  - [When or When not to use](#when-or-when-not-to-use)

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
- 

## Benefits
1. It will significantly improve development times
   1. Because engineers ONLY focus on features and testing and not configurations and setup
   2. Engineers are not required to 
   3. Upgrades are easy to do
   4. Mocks are auto generated for integration tests by injected dependencies. This makes integration tests incredibly fast
      1.  For instance:
      2. Fetched url data
      3. Queried SQL or GraphQL data
      4. File data
      5. Authorization
2. Code & packages are atomic
   1. Frontend and backend code are completely separated
   2. Packages are singularly focused
      1. Each file has a single function
      2. Packages only contain business rules
      3. This makes packages incredibly lean
         1. All code is separated into standardized directories
   3. 2 types of packages
      1. Private packages are used as libraries for internal development, public libraries. THis keeps them focused on thier usecases therefore atomic. Private libraries can also have deeper namespaces which makes it easier to keep track of them i.e.
         1. `@organization/subdomain/component`
         2. `@organization/subdomain/service`
      2. Public libraries have `npm` formatted namespaces. These are the packages that are exported and used by apps or developers in the case of `cli` tools or generators, for example. They pull in the private packages and are, usually, automatically handled and linked. Multiple public packages can also be created with a generator
         1. `@organization/package-name`
3. Opinionated & strict standards affords us some extra benefits
   1. Code can be auto generated
   2. Engineers can focus on what matters. Business logic
   3. Codemods are simpler
   4. Code is auto loaded and ran automatically
   5. All code follows the same styles making transition between teams seamless
      1. Except for logic which will be different for each team
   6. Updates to packages and repos is far less painful
      1. Single repo of configs to update
      2. Testing packages after updates are simple
4. Does not require local `Docker` (or any VM) containers to run code on any engineer's machine
   1. This speeds up development so engineers do not need to reload containers for container changes
   2. Working directly on the host machine speeds up development significantly
   3. Since all configurations are the same it wouldn't be possible for code to be run differently on the local computer to a deployed environment.
5. Documentation
   1. API Tester
   2. Storybook
   3. Docs website (`./_docs`)
6. Keeps package directories simple and clean
   1. Standardized directories and file names makes things easier to find
   2. There won't be any open source library configurations or required directories in packages
7. Default libraries
   1. Libraries like the injected `URL` object allow for all 

## When or When not to use
- If your teams prefer to manage everything themselves
- Really dislike the functional programming paradigm
- Do not like the default libraries the framework provides
- Do not like the external packages used
  - i.e. [Prisma](https://www.prisma.io/)
- Do not want development or testing performance
