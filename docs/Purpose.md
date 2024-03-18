# Purpose
## What
The idea is to use macro repos instead of a monorepo that contains everything. A macro repo in this context is similar to a monorepo with the exception that it contains ONLY packages related to an organization's subdomain. 

## Why
Why am I doing this? Firstly for fun. Secondly it's a problem that every company suffers and would make things so much faster and easier for everyone if there was an opinionated coding standard, configuration, development and testing.

## Example
For example let's say we are part of a SaaS insurtech company that provides many different customizeable services.

The domain could contain insurance and it's sub-domains would be claims, policy management, authentication etc. There could be other sub-domains that are organization specific like custom web components and internal frameworks. Therefore the sub-domains could be:

- Rules
- Claims
- Policy Management
- Authentication
- Design System & Component Library
- Frameworks
- Deployment 
- Configurations
  - Overrides & extras

Many teams prefer a monorepo to store and handle each of those items OR to have hundreds of little repos to maintain. 

I propose a new method of handling everything and focusing highly on sub-domains.

## Macro Repos
### Heavily Opinonated
Being heavily opinonated means having a consistant standard and allows for quite a few benefits for management and development.

1. Auto configurations makes setup much faster and engineers do not need to worry about how thier code is hooked up
   1. Organizations can override these configurations (in a different macro repo)
2. Code can be autoloaded
    - Simpler code makes development faster and more straight forward
3. Code can be easily manipulated via tools
   1. Tools can modify code quicker
   2. Tools to add new files is a breeze
4. Static analysis can be applied (?)
5. Everyone is coding with the same standards making team swapping easier
6. Standardized packages means that everyone should be on the same version for packages provided by the framework
7. Upgrading packages (this framework or yours) is much more simple and easier

### Functional
This macro repo framework prefers functional over the OOP paradigm. Reason being is it's a preferred paradigm but also pure functions allow for significantly easier development, error handling testing and more. Also immutable state is a huge benefit.

Though it is functional that doesn't mean that the code within any file requires it to be functional also but it is hihgly recommended.

### Autoloading

### Everything's Bundled
Every package is bundled to a single file making it simpler to add to apps. Everything can be optionally bundled into 2 different packages.

1. `npm` publish to internal or open. This is the default option.
2. A zip file that contains less code to make builds and deployments faster.
   1. Note: These would have to be on an internal service to keep these bundles.

### Core & Core Tools

### Default Packages & Code Standards

### Highly configurable.

### Other stuff
