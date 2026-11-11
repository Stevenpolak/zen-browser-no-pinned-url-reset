# Tab button visibility

A Zen Browser mod with independent settings for hiding the Close / Unload control and the URL Reset control on pinned tabs and Essentials.

Based on [spicybackend/zen-browser-no-pinned-url-reset](https://github.com/spicybackend/zen-browser-no-pinned-url-reset). See LICENSE for the original license.

## Settings

The mod uses Zen's built-in mod settings, defined in `preferences.json`.

| Setting | Default | Effect when enabled |
| --- | --- | --- |
| Hide Close / Unload on pinned tabs and Essentials | On | Hides `.tab-close-button` and `.tab-reset-button` on pinned tabs and Essentials. |
| Hide URL Reset on pinned tabs and Essentials | Off | Hides `.tab-reset-pin-button`, which returns a pinned tab to its saved URL. |

Enable either checkbox, both, or neither. When Close / Unload is unchecked, Zen determines its normal visibility. When Hide URL Reset is unchecked, this mod keeps URL Reset available on named pinned tabs in the expanded sidebar, including at the saved URL. Hiding URL Reset takes priority. Keyboard shortcuts and menu actions are unchanged.

Essentials already hide their controls by default in current Zen. These rules also cover Essentials if another theme makes the controls visible. Normal, unpinned tabs are unaffected.

On loaded pinned tabs, Zen uses `.tab-reset-button` for the close/unload action. The Close / Unload setting hides that control as well as `.tab-close-button`. URL Reset uses `.tab-reset-pin-button` and has its own setting. The original `hide-essential-close` preference key is retained to preserve saved checkbox choices.

## Reset at the saved URL

With Hide URL Reset off, the reset button stays available on named pinned tabs even when their URL matches the saved URL. It shows a reload icon in that state. Clicking it uses Zen's existing reset action, which restores the saved page state and reloads the page. This can also reset tab history, scroll position, and session storage; it is not a cache-bypassing hard refresh.

This extra visibility applies to the expanded sidebar. Essentials and the collapsed sidebar keep their native layout.

## Installation notes

Forking this repository does not change the mod already installed from Zen's registry. That installation continues to use the original registry entry.

This version needs to be installed with both `chrome.css` and `preferences.json` loaded by Zen's mod system for its settings to appear. Loading only the CSS through `userChrome.css` does not create a mod settings panel.

For registry distribution, submit this fork as a separate mod, including its preferences, using [Zen's submission guidelines](https://docs.zen-browser.app/themes-store/themes-marketplace-submission-guidelines).

## Compatibility

Uses [Zen's documented mod preferences](https://docs.zen-browser.app/themes-store/themes-marketplace-preferences) and current tab-control selectors. The files have been checked against the documentation and browser source, but have not been tested in a running Zen installation.
