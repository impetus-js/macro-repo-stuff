# Core Framework Repos (kernal)
- [Core Framework Repos (kernal)](#core-framework-repos-kernal)
  - [About](#about)
  - [Folder Structure](#folder-structure)
  - [Packages](#packages)
    - [Client Configs](#client-configs)
    - [Infra](#infra)
    - [Runners](#runners)
      - [Notes](#notes)
    - [~~Bundler~~](#bundler)
    - [Testing](#testing)
    - [Front End](#front-end)
    - [Back End](#back-end)
    - [Macro Repo](#macro-repo)
    - [Organization Packages](#organization-packages)

## About
The `kernal` is essentially the `main()` of the framework.

## Folder Structure
```
kernal
  _docs
  apps
  config
  packages
    client-configs
    infra
    runners
    testing
    front-end
    back-end
    bundler
    # macro-repo
```

## Packages
### Client Configs
### Infra
### Runners
The runners are executables that run the code. They have a few core functions.
1. Find & load files automatically
   - Allows code to be kept clean
   - Requires that source files are in a specific format
2. 

#### Notes
### ~~Bundler~~
### Testing
### Front End
### Back End
### Macro Repo
### Organization Packages
Packages that the Organization define to be used. They would be all the same version. The exception is if an override is required but this means it's unmanaged.

These are packages that would be automatically applied to the `package.json` by package type.
