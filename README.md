<p align="center">
<a href='https://ko-fi.com/A204JA0' target='_blank'><img height='28' style='border:0px;height:28px;' src='https://az743702.vo.msecnd.net/cdn/kofi4.png?v=f' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>&nbsp;&nbsp;<a href="https://travis-ci.org/niladam/wp2ssl"><img height="28" src="https://travis-ci.org/niladam/wp2ssl.svg?branch=master"></a>
</p>

## WP2SSL (WordPress 2 SSL): Move WordPress from HTTP to HTTPs. Automatically.
#### (c) 2017 Madalin Tache
#### http://github.com/niladam/wp2ssl

A bash script that tries to automate the moving from HTTP to HTTPS, by doing
most of the heavy lifting using [WP-CLI](http://wp-cli.org).

# What it does
***It creates a backup of your current database first.***
It then replaces all instances of `http` with `https` on the current WordPress install, and updates `.htaccess` to force to HTTPS.

# What it doesn't do (yet, or never)
It cannot update all theme/plugin files to be requested using HTTPS. If a plugin is using HTTP for the load, you will get ***mixed content*** warnings in your browser.
If you're looking for a solution to these cases i suggest you check out [Really Simple SSL](https://wordpress.org/plugins/really-simple-ssl/)

# Installing

Install with:

```bash
curl -sSL https://wp2ssl-installer.includes.io | bash
```

# Updating

If you want to update the script you can use two options. Either run the same command as the install (will auto-update if needed), or use the built-in updater

```bash
wp2ssl --up
```

or

```bash
wp2ssl --self-update
```

# Using

***For now, the plugin will only function if called from the *main WordPress* folder.***

Use with:

```bash
cd /home/someuser/public_html
wp2ssl
```

# Command Options

```bash
                  ____          _
   __      ___ __|___ \ ___ ___| |
   \ \ /\ / / '_ \ __) / __/ __| |
    \ V  V /| |_) / __/\__ \__ \ |
     \_/\_/ | .__/_____|___/___/_|
            |_|
                       v. 1.1
  https://github.com/niladam/wp2ssl

    [FLAGS]
        --up, --self-update         Self update this script to the latest version.
                                    Uses curl if available and fallsback to wget,
                                    if curl is missing.

        --h, --help                 This help screen.
```

# Does it work ?
The script has been tested on a fresh WordPress install and it worked out of the box. So i guess ***YES*** !:)

# Bugs ?
Found a bug ? Please use the [isues](https://github.com/niladam/wp2ssl/issues) section and report it. I'll be glad to tackle them.

# Contributing
If you want to contribute to this script, please fork/clone create a new branch and use the pull requests. I'll be glad to see them coming.

# TODO

- [ ] Bulk run ?
- [ ] Identify scripts/javascripts and force them to use HTTPS ?
- [ ] Suggest and/or install Really Simple SSL after use?
- [x] Suggest and/or run backup before attempting the database changes ? *Since [#a854614](https://github.com/niladam/wp2ssl/commit/a854614e6620c5b5bc5da1ebb96755ec8876c240) the plugin runs an export and archives the database dump. Just to be safe :)*
- [ ] Force WP-ADMIN SSL after run ?

# Notes
Some of the functionality in this script were originally built for [WPEB - ***W***ordPress ***E***asy ***B***ackup](https://github.com/niladam/wpeb), another script that might be of your interest.

# License

WP2SSL (WordPress 2 SSL) is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 2 of the License, or (optionally) any later version.