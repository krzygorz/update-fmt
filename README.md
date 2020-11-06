# update-fmt

This is a script that lists outdated packages on your Arch system.

The output is formatted for use with Conky, but with minimal modifications you should be able to get it to work with terminal or other display methods.

## Differences from `checkupdates`:

- Separates pkgrel bumps (rebuilds) from actual upstream updates.
- Displays commit messages for pkgrel bumps.
- Hides haskell package rebuilds, since these can get pretty spammy.
- Fancy formatting:
  - Common version prefixes joined together.
  - "-1" and ".arch1" pkgrel suffix removed.

## Dependencies

- `pyalpm`
- `python-requests`

They can be installed from the official Arch repositories.

## Config

-Generate a read-only github access token at https://github.com/settings/tokens and paste it to `~/.config/updatefmt-ghtoken`.


### Example conky config fragment

```
Updates:
${execpi 3600 ~/.local/bin/update-fmt}$color
```

Do not set the refresh interval too low as it will unnecessairly load the Arch mirrors.

## Screenshot

![](updatefmt.png)
