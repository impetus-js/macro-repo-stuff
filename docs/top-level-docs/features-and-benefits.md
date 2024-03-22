# Features & Benefits
- [Features \& Benefits](#features--benefits)
  - [Opinionated](#opinionated)
  - [Benefits](#benefits)
  - [When or When not to use](#when-or-when-not-to-use)

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
      5. Authorizations
2. Opinionated & strict standards affords us some extra benefits
   1. Code can be auto generated
   2. Engineers can focus on what matters. Business logic
   3. Codemods are simpler
   4. Code is auto loaded and ran automatically
   5. All code follows the same styles making transition between teams seamless
      1. Except for logic which will be different for each team
   6. Updates to packages and repos is far less painful
      1. Single repo of configs to update
      2. Testing packages after updates are simple
3. Does not require local `Docker` (or any VM) containers to run code on any engineer's machine
   1. This speeds up development so engineers do not need to reload containers for container changes
   2. Working directly on the host machine speeds up development significantly
   3. Since all configurations are the same it wouldn't be possible for code to be run differently on the local computer to a deployed environment.
4. Documentation
   1. API Tester
   2. Storybook
   3. Docs website (`./_docs`)

## When or When not to use
- If your teams prefer to manage everything themselves
- Really dislike the functional programming paradigm
- Do not like the default libraries the framework provides
- Do not like the external packages used
  - i.e. [Prisma](https://www.prisma.io/)
- Do not want development or testing performance
