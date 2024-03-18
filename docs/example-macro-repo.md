# File Tree
This is just the first folder structure I cam up with and am not super happy with it but the packages themselves I do like. 

I want this mono-repo to be broken up more like 
```
// The core packages
core
  _main
  client-configs
  infra
  kernel
  runner
  testing
  web

// Example apps mostly for development
apps

media

// Business packages?
packages
  communications
  documents
  emails
  events
  gateway
  local-services
  logging
  notifications
  search
  uploads

// Open source packages. Core should be in here tho 
open-source
  bundler-logger
  bundler-prod-cleaner
  bundler-testing
  macro-repo
  saraswati-core
  vscode-logger-highlighter
  vscode-macro-repo
  vscode-preferences
  vscode-test-opener

// Tools & generators
tools
  auto-loader
  cli
  eslint-base
  eslint-client
  eslint-tsx
  eslint-typescript
  generator-app
  generator-ci-cd
  generator-client-config
  generator-infra
  generator-lambda
  generator-lib
  generator-macro-repo
  generator-service
  loggercd
  parcel
  testing
```

```
.
├── _core-business
│   ├── _main
│   │   ├── _docs
│   │   ├── adapters
│   │   │   ├── databases
│   │   │   └── front-end
│   │   ├── apps
│   │   │   ├── cli
│   │   │   ├── client-1
│   │   │   │   ├── server
│   │   │   │   └── web-app
│   │   │   ├── client-2
│   │   │   │   ├── server
│   │   │   │   └── web-app
│   │   │   └── lambdas
│   │   ├── configs
│   │   │   ├── deployment
│   │   │   │   ├── Dockerfile
│   │   │   │   ├── Dockerfile.local
│   │   │   │   ├── docker-compose.yml
│   │   │   │   └── kubernetes
│   │   │   │       ├── ansible
│   │   │   │       │   ├── local.yml
│   │   │   │       │   └── prod.yml
│   │   │   │       ├── deployment.yml
│   │   │   │       └── service.yml
│   │   │   ├── environments
│   │   │   │   ├── base.config.js
│   │   │   │   ├── dev.config.js
│   │   │   │   ├── env.host
│   │   │   │   ├── env.local
│   │   │   │   ├── prod.config.js
│   │   │   │   ├── staging.config.js
│   │   │   │   └── uat.config.js
│   │   │   ├── jest
│   │   │   │   ├── jest.config.base.js
│   │   │   │   ├── jest.config.changed.js
│   │   │   │   ├── jest.config.js
│   │   │   │   └── jest.env.js
│   │   │   ├── marble-js
│   │   │   ├── nodemon
│   │   │   │   ├── nodemon.host.json
│   │   │   │   └── nodemon.json
│   │   │   ├── prettier
│   │   │   ├── scripts
│   │   │   │   ├── backup-database.sh
│   │   │   │   ├── backup-restore.sh
│   │   │   │   ├── backup.clear.sh
│   │   │   │   └── database-reinitalize.sh
│   │   │   ├── thunder-client
│   │   │   │   └── service-urls.json
│   │   │   ├── tsconfig.docker.json
│   │   │   └── tsconfig.json
│   │   ├── lambdas
│   │   │   └── login
│   │   ├── libs
│   │   │   ├── components
│   │   │   ├── instruction-set
│   │   │   ├── routes
│   │   │   └── scripts
│   │   ├── package.json
│   │   ├── pnpm-lock.yaml
│   │   ├── pnpm-workspace.yaml
│   │   └── services
│   │       ├── investigator
│   │       ├── local-stack
│   │       ├── payments
│   │       └── reminders
│   ├── client-configs
│   │   ├── _docs
│   │   ├── clients
│   │   │   ├── client-1
│   │   │   ├── client-2
│   │   │   └── client-3
│   │   └── packages
│   │       ├── meta
│   │       │   └── index.ts
│   │       └── meta-service
│   │           └── index.ts
│   ├── infra
│   │   ├── _docs
│   │   └── packages
│   │       ├── aws
│   │       ├── config-merge
│   │       ├── secrets
│   │       └── security
│   ├── kernel
│   │   ├── _docs
│   │   └── packages
│   │       ├── authentication
│   │       ├── knex-auditing
│   │       │   └── package.json
│   │       ├── knex-backup
│   │       ├── saas
│   │       └── validation
│   ├── runner
│   │   ├── _docs
│   │   └── packages
│   │       ├── cli
│   │       ├── micro-frontend
│   │       ├── service
│   │       ├── service-local
│   │       └── web-client
│   ├── testing
│   │   ├── _docs
│   │   └── packages
│   │       ├── testing-apps
│   │       ├── testing-clients
│   │       ├── testing-database
│   │       ├── testing-har-files
│   │       ├── testing-lambdas
│   │       ├── testing-pacts
│   │       ├── testing-regression
│   │       └── testing-services
│   └── web
│       ├── _docs
│       └── packages
│           ├── base-component-library
│           ├── design-system
│           ├── theme-admin
│           ├── theme-client
│           └── theme-docs
├── communications
├── documents
├── emails
├── events
├── gateway
├── local-services
├── logging
├── notifications
├── open-source
│   ├── _docs
│   └── packages
│       ├── bundler-logger
│       ├── bundler-prod-cleaner
│       ├── bundler-testing
│       ├── macro-repo
│       ├── saraswati-core
│       ├── vscode-logger-highlighter
│       ├── vscode-macro-repo
│       ├── vscode-preferences
│       └── vscode-test-opener
├── search
├── tools
│   ├── _docs
│   └── packages
│       ├── auto-loader
│       ├── cli
│       ├── eslint-base
│       ├── eslint-client
│       ├── eslint-tsx
│       ├── eslint-typescript
│       ├── generator-app
│       ├── generator-ci-cd
│       ├── generator-client-config
│       ├── generator-infra
│       ├── generator-lambda
│       ├── generator-lib
│       ├── generator-macro-repo
│       ├── generator-service
│       ├── logger
│       ├── parcel
│       └── testing
└── uploads
```