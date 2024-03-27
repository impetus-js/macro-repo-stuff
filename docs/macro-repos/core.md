# Core Framework Repos (kernal)

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
Client Configs
### Infra

### Runners
The runners are executables that run the code. They have a few core functions.
1. Find & load files automatically
   - Allows code to be kept clean
   - Requires that source files are in a specific format
2. 

#### Notes
The thing about the runners is that it will not work currently without some custom functionality. Options

1. Write a `rollup.js` plugin to find files and use a codemod to write a custom file that would end up being compiled
   - Simplilar to this plugin: [`@rollup/plugin-inject`](https://github.com/rollup/plugins/tree/master/packages/inject).
     - It uses a tree walker (`AST`) so this looks like it would be the best example to autopsy.
   - Has a cache, es conversion: [`@rollup/plugin-graphql`](https://github.com/rollup/plugins/tree/master/packages/graphql)
2. Follow `turbo.build`'s method and write a `rust` plugin or something. I really don't want to have to do this.

### Bundler


### Testing
### Front End
### Back End
### Macro Repo
