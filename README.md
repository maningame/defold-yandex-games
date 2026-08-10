[![YaGames Logo](cover.png)](https://github.com/yandex-games-plugins/defold)

# Yandex.Games SDK for Defold

[Yandex Games](https://yandex.com/games/) is a catalog of browser-based online games that can be played on
smartphones or desktop devices and require no installation. Most games are also available offline (code for
these games is added to the device cache during the first gaming session).

### Installation

You can procees to [Installation](https://plugins.lisgames.ru/defold/general/install) section of the documentation
to get more info about how to install the plugin.

### Documentation

Check out the [Documentation](https://plugins.lisgames.ru/) to get more info about how to work with plugins.

### Community

Feel free to join our [Telegram Chat](https://t.me/yandexgamesplugins) to keep in touch with us, get the
latest development news and take part in surveys!

## Fork changes

This is a Maningame fork of the official plugin, which has seen no commits since December 2024. On top of
the upstream `v1.3.0` it carries the fixes below and the two commits from
[Vallix/yandex-games-defold](https://github.com/Vallix/yandex-games-defold). See `CHANGELOG.md` for the
full list.

### `sdk_url` setting

Upstream loads `/sdk.js` in production and the absolute `https://sdk.games.s3.yandex.net/sdk.js` on
localhost only. That works for games uploaded to Yandex as an archive, but not for iframe games served from
their own domain — those need the absolute URL in production too, which used to require patching the built
`index.html`.

Set the URL in `game.project` instead:

```ini
[ysdk]
sdk_url = https://sdk.games.s3.yandex.net/sdk.js
```

Leave the setting empty (or omit the section) to keep the upstream behaviour.
