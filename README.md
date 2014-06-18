# Key Lime - JavaScript IME 

<p align="center">
  <img src="screenshot.png?raw=true" alt="" />
</p>

Key Lime is an input method editor written using pure JavaScript.  The library
is designed for Smart TV applications where the manufacturers' virtual
keyboards can be awkward use. For example, Samsung's JavaScript IME needs to
have an instance individually attached to every input element you want to use
it for, and LG Smart TV's native virtual keyboard is great but there's no way
to detect when the user closes it.  So, in the spirit of writing less code, Key
Lime allows you to just add the script and "fuggedaboudit".

## Features

If you're using a WebKit or Blink-based browser, check out the [demo][1].

 - Full keyboard navigation via arrow keys, never steals focus from the input
 - Complete transparency, all key events are intercepted before they reach the input element
 - Supports holding for diacritics, similar to touch screen keyboards
 - Fully stylable with CSS, base style inspired by the Windows 8 virtual keyboard
 - Tab button for moving between form fields
 - Convenient keys for quickly entering "http://", "www." and ".com"

[1]: http://rawgithub.com/andyearnshaw/keyLime/master/demo.html

## Getting started

Download the JavaScript source and add it to your application's HTML:

    <script src="keylime.min.js"></script>

Alternatively, install with Bower:

    bower install keylime

That's it.  The IME will auto-appear on focus of a writable text input. 
You can change this to work manually by setting

    keyLime.config.noauto = true;

Then just call `keyLime.show()` or `keyLime.hide()` whenever you need it.

## Font

The keyboard is set up to use the OS's default sans-serif font, but I'd highly
recommend using something like [Fira Sans][fira].  Some smart TV platforms
might be missing some of the glyphs used. LG 2013 smart TVs don't have U+232B
Erase To The Left (⌫), for example, and most of the glyphs ignore font size on
the Samsung 2013 smart TV platform.

Note that different fonts might require some tweaking of the Key Lime CSS to
get the look right.

[fira]: https://www.mozilla.org/en-US/styleguide/products/firefox-os/typeface/

## API

Key Lime will fire `keylimeshow` and `keylimehide` events on the active element.

Alongside the `keyLime.show()` and `keyLime.hide()` methods are a couple of
configuration options:

    // Don't show/hide the keyboard automatically on focus/blur
    keyLime.config.noauto = false;

    // The length of time to hold a key before diacritics are shown 
    keyLime.config.keyHoldTimeout = 500;

The values in that example are the defaults for those settings.

## Roadmap

 - Make it easy to add other languages
 - Allow certain keys to be disabled for different input types
 - Add other types of input methods, like numeric only, and perhaps date/time
 - Add dictionary and suggestions support

## License

Copyright (c) 2014 Andy Earnshaw

This software is licensed under the MIT license. See the LICENSE.txt file accompanying this software for terms of use.
