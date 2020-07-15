# update-fmt

This is a script that lists outdated packages on your Arch system.

Meant to be used with Conky.

## Differences from `checkupdates`:

- Separates pkgrel bumps (rebuilds) from actual upstream updates.
- Displays commit messages for pkgrel bumps
- Hides haskell package rebuilds, since these can get pretty spammy.
- Fancy formatting
  - Common version prefixes joined together
  - "-1" pkgrel suffix removed

## Dependencies

- `pyalpm`
- `python-lxml`

Both can be installed from official repositories.

## Example conky config fragment
```
$hr
${color1}Updates:
${color2}${execpi 3600 ~/Documents/Python/update-fmt/update-fmt}$color
$hr
```