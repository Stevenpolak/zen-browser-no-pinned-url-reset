# Tab button visibility

A Zen Browser mod with independent settings for hiding the Close / Unload control and the URL Reset control on pinned tabs and Essentials.

Based on [spicybackend/zen-browser-no-pinned-url-reset](https://github.com/spicybackend/zen-browser-no-pinned-url-reset). See LICENSE for the original license.

## Settings

The mod uses Zen's built-in mod settings, defined in `preferences.json`.

| Setting | Default | Effect when enabled |
| --- | --- | --- |
| Hide Close / Unload on pinned tabs and Essentials | On | Hides `.tab-close-button` and `.tab-reset-button` on pinned tabs and Essentials. |
| Hide URL Reset on pinned tabs and Essentials | Off | Hides `.tab-reset-pin-button`, which returns a pinned tab to its saved URL. |

Enable either checkbox, both, or neither. When a checkbox is off, the mod adds no hiding rule for that control; Zen and other mods determine its normal visibility. This mod does not force buttons to appear and does not disable keyboard shortcuts or menu actions.

Essentials already hide their controls by default in current Zen. These rules also cover Essentials if another theme makes the controls visible. Normal, unpinned tabs are unaffected.

On loaded pinned tabs, Zen uses `.tab-reset-button` for the close/unload action. The Close / Unload setting hides that control as well as `.tab-close-button`. URL Reset uses `.tab-reset-pin-button` and has its own setting. The original `hide-essential-close` preference key is retained to preserve saved checkbox choices.

## Installation notes

Forking this repository does not change the mod already installed from Zen's registry. That installation continues to use the original registry entry.

This version needs to be installed with both `chrome.css` and `preferences.json` loaded by Zen's mod system for its settings to appear. Loading only the CSS through `userChrome.css` does not create a mod settings panel.

For registry distribution, submit this fork as a separate mod, including its preferences, using [Zen's submission guidelines](https://docs.zen-browser.app/themes-store/themes-marketplace-submission-guidelines).

## Compatibility

Uses [Zen's documented mod preferences](https://docs.zen-browser.app/themes-store/themes-marketplace-preferences) and current tab-control selectors. The files have been checked against the documentation and browser source, but have not been tested in a running Zen installation.
