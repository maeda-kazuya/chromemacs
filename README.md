Chromemacs - Chrome navigation by Emacs keybind
=============================

[Chromemacs](https://chrome.google.com/webstore/detail/chromemacs/kfdibhbheajeacnkkakomaliggbgndcf) is a browser extension that provides keyboard-based navigation and control of the web in the spirit of
the Emacs editor.

**Installation instructions:**

Clone this repository and load unpacked via chrome://extensions

To install from source, see [here](CONTRIBUTING.md#installing-from-source).

Chromemacs's Options page can be reached via a link on the help dialog (type `<c-h>`) or via the button next to Chromemacs
on the extension pages of Chrome (`chrome://extensions`) or Firefox (`about:addons`).

## Keyboard Bindings

Modifier keys are specified as `<c-x>`, `<m-x>`, and `<a-x>` for ctrl+x, meta+x, and alt+x
respectively. For shift+x and ctrl-shift-x, just type `X` and `<c-X>`. See the next section for how
to customize these bindings.

Once you have Chromemacs installed, you can see this list of key bindings at any time by typing `?`.

Navigating the current page:

    <c-h>       show the help dialog for a list of all available keys
    <c-b>       scroll left
    <c-n>       scroll down
    <c-p>       scroll up
    <c-f>       scroll right
    <c-m-,>     scroll to top of the page
    <c-m-.>     scroll to bottom of the page
    <c-v>       scroll down half a page
    <m-v>       scroll up half a page
    <c-x><c-f>  open a link in the current tab
    <c-x><a-F>  open a link in a new tab
    <m-r>       reload
    <a-s>       view source
    <c-g><c-u>  copy the current url to the clipboard
    <c-g><c-l>  copy a link url to the clipboard
    <c-x>o      cycle forward to the next frame

Navigating to new pages:

    <c-x><c-d>  Open URL, bookmark, or history entry
    <c-x><c-D>  Open URL, bookmark, history entry in a new tab
    <c-x><c-b>  Open bookmark
    <c-x><c-B>  Open bookmark in a new tab

Using find:

    <c-s>       enter find mode
              -- type your search query and hit enter to search, or Esc to cancel
    n       cycle forward to the next find match
    N       cycle backward to the previous find match

For advanced usage, see [regular expressions](https://github.com/philc/vimium/wiki/Find-Mode) on the
wiki.

Navigating your history:

    <c-m-b>       go back in history
    <c-m-f>       go forward in history

Manipulating tabs:

    <c-b>          go one tab left
    <c-f>          go one tab right
    <c-x><up>      go to the first tab
    <c-x><down>    go to the last tab
    <c-g><c-t>     create tab
    <c-x>4         duplicate current tab
    <c-x>0         close current tab
    <c-g><c-r>     restore closed tab (i.e. unwind the 'x' command)
    <c-x>b         search through your open tabs
    <c-x>5         move current tab to new window
    <a-p>          pin/unpin current tab

Using marks:

    ma, mA  set local mark "a" (global mark "A")
    `a, `A  jump to local mark "a" (global mark "A")
    ``      jump back to the position before the previous jump
              -- that is, before the previous gg, G, n, N, / or `a

Additional advanced browsing commands:

    <c-g><left>, <c-g><right>
              Follow the link labeled 'next' or '>' ('previous' or '<')
              - helpful for browsing paginated sites
    <a-f>   open multiple links in a new tab
    <c-g><c-f>  focus the first (or n-th) text input box on the page
    <c-g><      go up one level in the URL hierarchy
    <c-g>/      go up to root of the URL hierarchy
    <c-x><      scroll all the way left
    <c-x>>      scroll all the way right

Chromemacs supports command repetition so, for example, hitting `5t` will open 5 tabs in rapid succession. `<Esc>` (or
`<c-[>`) will clear any partial commands in the queue and will also exit insert and find modes.

There are additional commands which aren't included in this README; refer to the help dialog (type `?`) for a
full list.

## Custom Key Mappings

You may remap or unmap any of the default key bindings in the "Custom key mappings" on the options
page.

Enter one of the following key mapping statements per line:

- `map key command`: Maps a key to a Chromemacs command. Overrides Chrome's default behavior (if any).
- `unmap key`: Unmaps a key and restores Chrome's default behavior (if any).
- `unmapAll`: Unmaps all bindings. This is useful if you want to completely wipe Chromemacs's defaults and start
  from scratch with your own setup.

Examples:

- `map <c-d> scrollPageDown` maps ctrl+d to scrolling the page down. Chrome's default behavior of
  showing a bookmark dialog is suppressed.
- `map r reload hard` maps the r key to reloading the page, and also includes the "hard"
  option to hard-reload the page.
- `unmap <c-d>` removes any mapping for ctrl+d and restores Chrome's default behavior.
- `unmap r` removes any mapping for the r key.

Available Chromemacs commands can be found via the "Show available commands" link
near the key mapping box on the options page. The command name appears to the
right of the description in parenthesis.

You can add comments to key mappings by starting a line with `"` or `#`.

The following special keys are available for mapping:

- `<c-*>`, `<a-*>`, `<s-*>`, `<m-*>` for ctrl, alt, shift, and meta (command on Mac) respectively
  with any key. Replace `*` with the key of choice.
- `<left>`, `<right>`, `<up>`, `<down>` for the arrow keys.
- `<f1>` through `<f12>` for the function keys.
- `<space>` for the space key.
- `<tab>`, `<enter>`, `<delete>`, `<backspace>`, `<insert>`, `<home>` and `<end>` for the
  corresponding non-printable keys.

Shifts are automatically detected so, for example, `<c-&>` corresponds to ctrl+shift+7 on an English
keyboard.

## More documentation

* [FAQ](https://github.com/philc/vimium/wiki/FAQ)
* [Command listing](https://vimium.github.io/commands/)
* [Vimium's GitHub wiki](https://github.com/philc/vimium/wiki): documentation the more advanced
  features.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## Release Notes

See [CHANGELOG](CHANGELOG.md) for the major changes in each release.

## License

Copyright (c) Phil Crosby, Ilya Sukhar. See [MIT-LICENSE.txt](MIT-LICENSE.txt) for details.
