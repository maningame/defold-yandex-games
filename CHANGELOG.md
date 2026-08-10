# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased] - Maningame fork

### Added

- `ysdk.sdk_url` setting in `game.project` to override the URL the Yandex Games SDK is loaded from
- `ACCOUNT_SELECTION_DIALOG_OPENED` and `ACCOUNT_SELECTION_DIALOG_CLOSED` events
- `environment.referrer` with the parameters of the promo deeplink the player came from
- Retry, timeout and an on-screen error message instead of a blank page when the SDK fails to load

### Fixed

- Replaced deprecated `player.getMode()` with `player.isAuthorized()` for checking login status
- Replaced deprecated `ysdk.getLeaderboards()` with direct `ysdk.leaderboards` API calls
- Fixed typo in `JS_CanReview` (`repsonse` -> `response`)
- Removed debug `console.log` statements from production code
- `feedback.can_review` and `get_flags` called their callbacks with a wrong argument count
- `player.increment_stats` overwrote the stats instead of incrementing them (`setStats` -> `incrementStats`)
- `leaderboards.get_player_entry` returned no public name and unique id (`publicName`, `uniqueID`)
- `payments.get_catalog` returned no image, price value and currency code (`imageURI`, `priceValue`,
  `priceCurrencyCode`)
- A single unsupported event no longer breaks the subscription to the remaining ones

## [1.3.0] - 2024.12.1

### Added

- Updated initialization stage 
- Games API support
- New `game_api_pause` and `game_api_resume` events
- Event unsubscribtion functionality

## [1.2.4] - 2024.11.12

### Fixed

- Fixed typos in get leaderboard entries fields

## [1.2.3] - 2024.09.14

### Changed

- Argument `params` in `player.get_info` is now optional

## [1.2.2] - 2024.09.13

### Fixed

- Fixed broken leaderboards methods

## [1.2.1] - 2024.09.06

### Fixed

- Compilation error in HMTL5 target

## [1.2.0] - 2024.07.26

### Added

- Completions for Defold code editor
- Support for `Server time` API
- Support for player's paying status information
- Support for [GameplayAPI](https://yandex.ru/dev/games/doc/ru/sdk/sdk-game-events#gameplay)
- Updated README to include information about the new documentation
- Parameter `keys` is now optional in `ysdk.player.get_data` and `ysdk.player.get_stats`
- New parameter `callback` for `ysdk.payments.consume_purchase`

### Fixed

- String allocation for newer versions of Defold
- Error serialization in `ysdk.adv.show_fullscreen_adv` and `ysdk.adv.show_rewarded_video`

## [1.1.0] - 2024.01.4

### Added

- Support for [Remote Config](https://yandex.ru/dev/games/doc/ru/sdk/sdk-config)
