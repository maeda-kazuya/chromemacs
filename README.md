Chromemacs - The Hacker's Browser
=============================


Chromemacs is a Chrome extension that provides keyboard-based navigation and control of the web in the spirit of
the Emacs editor. The source code is originally forked from Vimium, just replaced the keybind from Vim to Emacs.

__Installation instructions:__

You can install the stable version of Chromemacs from the
[Chrome Extensions Gallery](https://chrome.google.com/extensions/detail/dbepggeogbaibhgnhhndojpepiihcmeb).

Please see
[CONTRIBUTING.md](CONTRIBUTING.md#installing-from-source)
for instructions on how you can install Chromemacs from source.

The Options page can be reached via a link on the help dialog (type `?`) or via the button next to Chromemacs on
the Chrome Extensions page (`chrome://extensions`).

Keyboard Bindings
-----------------

Modifier keys are specified as `<c-x>`, `<m-x>`, and `<a-x>` for ctrl+x, meta+x, and alt+x
respectively. For shift+x and ctrl-shift-x, just type `X` and `<c-X>`. See the next section for how to customize these bindings.

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

For advanced usage, see [regular expressions](https://github.com/philc/vimium/wiki/Find-Mode) on the wiki.

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

There are some advanced commands which aren't documented here; refer to the help dialog (type `?`) for a full
list.

Custom Key Mappings
-------------------

You may remap or unmap any of the default key bindings in the "Custom key mappings" on the options page.

Enter one of the following key mapping commands per line:

- `map key command`: Maps a key to a Chromemacs command. Overrides Chrome's default behavior (if any).
- `unmap key`: Unmaps a key and restores Chrome's default behavior (if any).
- `unmapAll`: Unmaps all bindings. This is useful if you want to completely wipe Chromemacs's defaults and start
  from scratch with your own setup.

Examples:

- `map <c-d> scrollPageDown` maps ctrl+d to scrolling the page down. Chrome's default behavior of bringing up
  a bookmark dialog is suppressed.
- `map r reload` maps the r key to reloading the page.
- `unmap <c-d>` removes any mapping for ctrl+d and restores Chrome's default behavior.
- `unmap r` removes any mapping for the r key.

Available Chromemacs commands can be found via the "Show available commands" link
near the key mapping box on the options page. The command name appears to the
right of the description in parenthesis.

You can add comments to key mappings by starting a line with `"` or `#`.

The following special keys are available for mapping:

- `<c-*>`, `<a-*>`, `<m-*>` for ctrl, alt, and meta (command on Mac) respectively with any key. Replace `*`
  with the key of choice.
- `<left>`, `<right>`, `<up>`, `<down>` for the arrow keys.
- `<f1>` through `<f12>` for the function keys.
- `<space>` for the space key.
- `<tab>`, `<enter>`, `<delete>`, `<backspace>`, `<insert>`, `<home>` and `<end>` for the corresponding non-printable keys (version 1.62 onwards).

Shifts are automatically detected so, for example, `<c-&>` corresponds to ctrl+shift+7 on an English keyboard.

More documentation
------------------
Many of the more advanced or involved features are documented on
[Chromemacs's GitHub wiki](https://github.com/philc/vimium/wiki). Also
see the [FAQ](https://github.com/philc/vimium/wiki/FAQ).

Contributing
------------
Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details.

Firefox Support
---------------

There is an *experimental* port of Chromemacs on Firefox [here](https://addons.mozilla.org/en-GB/firefox/addon/Chromemacs-ff/).
This is very much experimental: most features work, although some bugs and issues remain.

PRs are welcome.

Release Notes
-------------

1.64 (2018-08-30)


- Custom search engines can now be `javascript:` URLs (eg., search the current [site](https://github.com/philc/vimium/issues/2956#issuecomment-366509915)).
- You can now using local marks to mark a hash/anchor.  This is particularly useful for marking labels on GMail.
- For filtered hints, you can now start typing the link text before the hints have been generated.
- On Twitter, expanded tweets are now scrollable.
- Fix bug whereby `<Enter>` wasn't recognised in the Vomnibar in some circumstances.
- Various minor bug fixes.

1.63 (2018-02-16)

- The `reload` command now accepts a count prefix; so `999r` reloads all tabs (in the current window).
- Better detection of click listeners for link hints.
- Display version number in page popup.
- The Vomnibar is now loaded on demand (not preloaded).  This should fix some issues with the dev console.
- The `\I` control (case sensitivity) for find mode has been removed.  Find mode uses smartcase.
- Various bug fixes.
- 1.63.1 (Firefox only):
    - Fix [#2958](https://github.com/philc/vimium/issues/2958#issuecomment-366488659), link hints broken for `target="_blank"` links.
- 1.63.2 (Firefox only):
    - Fix [#2962](https://github.com/philc/vimium/issues/2962), find mode broken on Firefox Quantum.
- 1.63.3:
    - Fix [#2997](https://github.com/philc/vimium/issues/2997), Chromemacs's DOM injection breaks Google Pay site.


License
-------
Copyright (c) Phil Crosby, Ilya Sukhar. See MIT-LICENSE.txt for details.
