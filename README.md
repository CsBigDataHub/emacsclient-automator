# emacsclient-automator
<!--
Copyright 2018, David Corking and the emacsclient-automator contributors
SPDX-License-Identifier: MIT
-->
Tiny Automator workflows to make it easier to re-use your running
Emacs.

Emacs users like to keep a single instance of their editor running,
and merely open files in it. To do this easily from outside Emacs,
Emacs comes with a tiny executable called
[emacsclient](https://www.emacswiki.org/emacs/EmacsClient). From a
command line, just run <code>emacsclient <em>file</em></code>.

From GUIs like macOS's Finder, you can drag and drop a file onto your
Emacs window, but it is nice to bypass this as we do with other apps.

Choose either the app or the service, instructions below: you might
not need both.

⚠️**Warning** `emacsclient` is hardcoded to `/Applications/Emacs.app/Contents/MacOS/bin/emacsclient`
which is typical if emacs is installed from [emacsformacosx](https://emacsformacosx.com/) . However
if installed with Homebrew please change the path in `withEmacs.workflow/Contents/document.wflow` and
`withEmacsApp.app/Contents/document.wflow` to : `/usr/local/bin/emacsclient`. If your emacsclient is
elsewhere, you *must edit* the workflow. ⚠️

## App

(steps 2 and 3 are optional - you can run an app from anywhere, but it
might be easier for you to find in your Applications folder)

1. `cd && git clone https://github.com/paironaut/emacsclient-automator.git`
2. `cd emacsclient-automator`
3. `cp -R withEmacsApp.app /Applications`

To use it:

4. [start the Emacs
   server](https://www.gnu.org/software/emacs/manual/html_node/emacs/Emacs-Server.html)
   (for example with `M-x server-start` or `emacs --daemon`)

   - Alternatively you can add `(server-start)` inside `init.el` or `.emacs` file.

5. open a Finder window and ctrl-click a file.
6. select 'Open with' then 'Other...'
7. a file sector pops up: find and select withEmacs
8. optionally, if you want to always use emacsclient to open this
   file, select the 'Always Open With' checkbox
9. select 'Open'
10. when you are finished editing type `C-x #` or `M-x server-edit`.

There are many other options in macOS for using an app like this to
open a file, such as the 'Open with: Change All ...' button in the
Finder Info window. Investigate these with Apple's documentation.

## Service

1. `cd && git clone https://github.com/paironaut/emacsclient-automator.git`
2. `cd emacsclient-automator`
3. `cp -R withEmacs.workflow ~/Library/Services`

To use it:

4. [start the Emacs
   server](https://www.gnu.org/software/emacs/manual/html_node/emacs/Emacs-Server.html)
   (for example with `M-x server-start` or `emacs --daemon`)

   - Alternatively you can add `(server-start)` inside `init.el` or `.emacs` file.

5. open a Finder window and ctrl-click a file.
6. select 'Services >' from the bottom of the popup menu
7. select 'withEmacs'.
8. when you are finished editing type `C-x #` or `M-x server-edit`.

## Credit and troubleshooting

The idea for this came from a Reddit post that I can't find at the
moment. So I don't have to relearn Automator each time I configure a
Mac, I have posted the resulting code in this public git repository.

For configuration tips, see https://stackoverflow.com/a/39907215

## Wishlist

1. a custom icon
2. make the icon appear on associated files
3. drag and drop files onto the app icon

## Coming soon

Control Emacs from your watch.

## Contributing

Use Automator.app built in to macOS to edit these workflows. We'll
consider helpful pull requests. See the wishlist above.

## Copyright and license

Copyright 2018, David Corking and the emacsclient-automator
contributors. Open source MIT License, see [LICENSE.txt](LICENSE.txt)
