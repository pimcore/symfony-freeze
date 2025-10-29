# Pimcore Symfony Freeze

A metapackage to control Symfony version constraints for Pimcore 12.3 and 12.x development versions.

**⚠️ Important**: This package is **only for Pimcore 12.3 and 12.x dev versions**. Pimcore 13 will require Symfony 7+ and drop Symfony 6 support entirely.

## Purpose

This metapackage uses Composer's `conflict` directive to enforce Symfony version requirements:

- **6.x branch**: Freezes core Symfony components at 6.x (14 components)
- **7.x branch**: Requires core Symfony components at 7.x minimum (13 components)

## Usage by Pimcore Version

### Pimcore 12.3 / 12.x (dev versions)

**Symfony 7.x fully supported** - choose based on your needs:

```json
{
  "require": {
    "pimcore/symfony-freeze": "^7.0" // Recommended: Enforce Symfony 7.x minimum
  }
}
```

Or if you need Symfony 6.x compatibility:

```json
{
  "require": {
    "pimcore/symfony-freeze": "^6.0" // Optional: Keep Symfony 6.x
  }
}
```

### Pimcore 13+

**Do not use this package**. Remove it:

```bash
composer remove pimcore/symfony-freeze
```

## Technical Details

- **Type**: Metapackage (no code, only constraints)
- **6.x branch**: Conflicts with `symfony/*: ">=7.0"` for 14 core components
- **7.x branch**: Conflicts with `symfony/*: "<7.0"` for 13 core components (excludes deprecated `symfony/templating`)

## License

POCL - © Pimcore GmbH
