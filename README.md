# Pimcore Symfony 6 Freeze

A metapackage to enforce Symfony 6.x compatibility constraints for Pimcore installations, ensuring alignment with Pimcore 12.2 release requirements.

## Purpose

This package provides version constraints to prevent certain Symfony components from upgrading to version 7.x, matching the compatibility requirements of **Pimcore 12.2**. While your local Pimcore installation (12.x branch) may allow Symfony 7 for some core framework components, this freeze package ensures backward compatibility with Pimcore 12.2 release.

## What This Package Does

This metapackage uses Composer's `conflict` directive to block Symfony 7.x upgrades for **14 specific components** that Pimcore 12.2 restricts to Symfony 6.x only:

### Frozen Components (Restricted to Symfony 6.x)

1. **symfony/console** - Command-line interface framework
2. **symfony/dependency-injection** - Service container and DI system
3. **symfony/framework-bundle** - Core Symfony framework bundle
4. **symfony/http-foundation** - HTTP request/response abstractions
5. **symfony/http-kernel** - HTTP request processing kernel
6. **symfony/messenger** - Asynchronous message handling
7. **symfony/runtime** - Application runtime environment
8. **symfony/security-bundle** - Security framework bundle
9. **symfony/security-core** - Security core components
10. **symfony/security-http** - HTTP security layer
11. **symfony/templating** - Templating engine (deprecated in Symfony)
12. **symfony/twig-bridge** - Twig integration bridge
13. **symfony/twig-bundle** - Twig bundle
14. **symfony/validator** - Data validation framework

### Components NOT Frozen (Can Upgrade to Symfony 7.x)

The following **31 components** are allowed to upgrade to Symfony 7.x as per Pimcore 12.2 compatibility:

- symfony/cache
- symfony/config
- symfony/debug-bundle
- symfony/doctrine-bridge
- symfony/doctrine-messenger
- symfony/dom-crawler
- symfony/error-handler
- symfony/event-dispatcher
- symfony/expression-language
- symfony/filesystem
- symfony/finder
- symfony/html-sanitizer
- symfony/lock
- symfony/mailer
- symfony/mime
- symfony/options-resolver
- symfony/password-hasher
- symfony/process
- symfony/property-access
- symfony/property-info
- symfony/rate-limiter
- symfony/routing
- symfony/serializer
- symfony/string
- symfony/translation
- symfony/uid
- symfony/var-dumper
- symfony/webpack-encore-bundle
- symfony/web-profiler-bundle
- symfony/workflow
- symfony/yaml

## Technical Details

### Package Type

- **Type**: `metapackage`
- **Strategy**: Uses Composer `conflict` directives (no actual code)

### Version Constraints

Each frozen component uses the constraint: `">=7.0"` in the conflict section, effectively blocking any Symfony 7.x version while allowing all 6.x versions.

## Comparison with Pimcore Releases

### Pimcore 12.2 (Stable Release)

- Restricts 14 core Symfony components to 6.x only
- Allows 31 peripheral components to use either 6.x or 7.x
- This package matches these exact constraints

### Pimcore 12.x (Development Branch) or 12.3 and later

- Allows all 45 Symfony components to upgrade to 7.x
- This freeze package overrides those permissions for the 14 core components

## Statistics

- **Total Symfony Components**: ~45
- **Frozen to 6.x**: 14 (31%)
- **Allowed for 7.x**: 31 (69%)
- **Alignment**: 100% with Pimcore 12.2

## Maintenance

This package should be updated when:

1. Pimcore releases a new stable version with changed Symfony requirements
2. Symfony releases a new major version
3. Core framework components receive official Symfony 7 support from Pimcore


## License

POCL - © Pimcore GmbH

## Support

For issues related to Pimcore compatibility, please refer to:

- [Pimcore Documentation](https://pimcore.com/docs/latest/)
- [Pimcore GitHub Issues](https://github.com/pimcore/pimcore/issues)
- [Pimcore Forums](https://github.com/pimcore/pimcore/discussions)
