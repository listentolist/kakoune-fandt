# kakoune-fandt

This plugin provides a user mode for the `f` and `t` commands
in Kakoune.

## Installation

Put the file `fandt.kak` into the autoload directory and run `require-module
fandt`.

## Usage

You can use all the `f` and `t` commands almost in the same way as usual. The
only difference is, that after that command you enter the *fandt* user
mode. In this mode you can repeat the `f` and `t` commands with the last
entered character. So you can cycle through the matches. Pressing any other
key than `f`, `F`, `t`, `T`, `<a-f>`, `<a-F>`, `<a-t>` and `<a-T>` leaves
the *fandt* mode and executes the key.

Example: By pressing `fo` you select to the next occurence of `o`. Now you
are in *fandt* mode. So pressing `f` again selects to the next occurence of
`o`. Pressing `<a-f>` brings you back to the last occurence of `o`. Pressing
`<a-T>` extends the selection until the next occurence of `o` in reverse
direction. By pressing `i` you leave the *fandt* mode and enter *insert* mode.

More realistic example: By pressing `3fa` you select to the third occurence
of `a`. But when see that it was not far enough, you press `F` to extend
the selection to the next occurence of `a`. By pressing `d` you delete
the selection.

## Configuration

- `str fandt_jump`, default `""`\
  If you want the cursor to jump instead of select to/until the next occurence
  with the lower case `f` and `t` commands, set this option to `";"`. Leave
  this option as it is, if you want the normal behaviour.

- `bool fandt_show_autoinfo`, default: `false`\
  If you want an info box to show up when entering *fandt* mode, set this to
  `true`.
