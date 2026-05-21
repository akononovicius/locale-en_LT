# locale-en_LT

I was annoyed that `en_US` locale had Sunday as its first day of the week,
so I have decided to make a custom locale. Along the way I have decided to
add some other elements from Lithuanian locale (which ought to be my home
locale).

## Compose file issue

In your logs, you might see an error along the lines of

```
xkbcommon: ERROR: couldn't find a Compose file for locale ...
```

This error should be just an inconvenience and not cause any significant
problems. Still, if you want to fix it, you will have to edit `compose.dir`
file, which tells which compose file to use for which locale. To do that
run:

```bash
sudoedit /usr/share/X11/locale/compose.dir
```

and then add the following line at the bottom of the file:

```
en_US.UTF-8/Compose		en_LT.UTF-8
```

This way `en_LT` will just reuse `en_US` compose file.

## Alternative solution

Instead of creating custom local, you could modify contents of your `/etc/locale.conf` file. See the example below, which should give a reasonable approximation possibly suitable for Lithuanian users prefering some US English defaults.

```
LANG="en_US.UTF-8"

LC_TIME="en_DK.UTF-8"
LC_MONETARY="en_IE.UTF-8"
LC_NUMERIC="en_US.UTF-8"

LC_PAPER="lt_LT.UTF-8"
LC_TELEPHONE="lt_LT.UTF-8"
LC_MEASUREMENT="lt_LT.UTF-8"
LC_ADDRESS="lt_LT.UTF-8"
```

## License

Consider this locale to be licensed under the same license as `glibc`
itself. At the time of creating this locale, it was licensed under
LGPL-2.1-or-later.

