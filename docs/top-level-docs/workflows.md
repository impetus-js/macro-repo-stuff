# Workflows & Setup
- [Workflows \& Setup](#workflows--setup)
  - [Organization Setup](#organization-setup)
    - [Configurations Setup](#configurations-setup)
  - [Repo \& Package Creation](#repo--package-creation)
  - [Development](#development)
  - [Deployment](#deployment)

The workflows explains how an organization sets up their macro-repos and 

## TODO
I want to add a diagram of engineering, QA & OPs workflows.

## Organization Setup
### Configurations Setup
There are extensive default configurations already created for package development to standardize as many tools as possible to keep everyone focused on feature development, testing, bug fixes, refactors et al. The configuration repo focuses on an organization's platform configurations for code styles, deployments and possibly the generators. This repo is what the framework uses when generators are used, cli and runners. 

These are primarly configuration and script setup but also overrides for each configuration type.

- Deployments
  - Ansible
  - AWS
  - Github/Gitlab/BitBucket
  - Front-end packages
  - Server packages
  - MFEs
  - Components libraries
  - Kafka
  - Envrioments
    - Dev
    - Staging (internal)
    - Staging (external)
    - Productions
  - Integration Tests
    - Mocks
- Generators -> Adding new generators of each type
  - Macro-repos
  - Packages
  - Apps
  - CLI
- Config loaders
- Overrides -> Of default configurations that the framework provides
  - Directory settings
    - Setup directories
  - Runners
  - Bundlers
  - Generators -> Modify the existing generator settings
    - Macro-repos
    - Packages
    - Apps
    - CLI
  - Code mods
  - Code Configurations
    - Code standards
      - Testing & converage
      - JS & TS coding styles, default configs
      - Styles

## Repo & Package Creation
Teams create repos, packages & apps using CLI tools to generate them and run codemods. CLI tools are also create new features within the codebase.

## Development
Development is straight forward and fast. After a macro-repo is created the packages are added and default/stub code is added. Engineers do not need to put work into handling OPs configurations nor package or code configurations. 

Configurations are loaded automatically either from default configurations that come with the framework or the overrides that the organization provides. Local (in repo) overrides are also available. 

Writing code is simple for a couple of reasons. Creating code is a generation affair (to make it easier or of course they can be added manually). When created they automatically come with tests and added to the correct directory. They are also auto linked (imported) but depending on package type. For instance a web page would generate a new route and added to a layout. These pages or components would be added to the respective app automatically and the engineer only needs to make sure it's added in the correct place. Server code would put a new route.

All code is containerized using an IoC container ([`injectable-ts`](https://github.com/raveclassic/injectable-ts/tree/main/packages/core)) and injected into the container. Core packages are also injected into autoloaded files like a logger, DB, file IO, Fetch etc those aren't required to be imported manually. I would also like to auto-import types and business logic but I'm not sure how I'd impliment such a feature and make sure that the compiler doesn't complain. That would be an incredibly useful feature to add. For instance types

Since all code is auto loaded (engineers aren't required to import them anywhere) there is no stress to do anything running applications is simple. It uses the framework's loader and runner packages. Builds are also simple because each package is by default compiled & minified to a single file and deployed/packaged as such.

## Deployment
Deployments are setup by the organization and no extra steps by the engineers are required.
