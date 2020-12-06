spacefn-evdev
=============

This is my fork of the original Spacefn-evdev by `abrasive`

This is a little tool to implement
[the SpaceFn keyboard layout](https://geekhack.org/index.php?topic=51069.0)
on Linux.

I wanted to try SpaceFn on my laptop, obviously with a built-in keyboard.

## Requirements


- libevdev
    and its headers or -dev packages on some systems
- uinput
    `/dev/uinput` must be present and you must have permission to read and write it

You also need permission to read `/dev/input/eventXX`.

On my system all the requisite permissions are granted by making myself a member of the `input` group.
You can also just run the program as root.

## Compiling

Run `make`.

## Running

Find your keyboard in `/dev/input/`.
The easiest way is to look in `/dev/input/by-id`;
for example, my laptop keyboard is
`/dev/input/by-id/usb-ITE_Tech._Inc._ITE_Device_xxxx_-event-kbd`.

Then run the program:
```
./spacefn /dev/input/by-id/usb-ITE_Tech._Inc._ITE_Device_xxxx_-event-kbd
```

## Customising

The key map is in the function `key_map()`. Refer to `input-event-codes.h` file for keycodes.
