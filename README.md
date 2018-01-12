# xbacklight-hacks
Got pissed off with my super dull backlight on my laptop, so wrote this little utility to help.

This takes a decimal/percentage as the only parameter, and sets the backlight to that value. If the
value is greater than 100, we use xrandr to increase the gamma to simulate a brighter display, albeit
at the loss of colour and contrast.

This prevents setting a value less than `0.1`/`10%` for the brightness, as it is a pain to try and
turn the backlight back on using the commandline without a functioning backlight.

## Assumptions:

This assumes your device display name is `LVDS1`, if it isn't, you should probably alter my script.

## Dependencies:

- `xorg-xrandr`
- `xorg-xbacklight`
- `ruby` and `irb`

## Installation:

- Install the dependencies from your package manager of choice for your distro.

- Run one of the following commands in your shell...

**Using wget**
```bash
sudo sh -c "wget -S -O - \
      https://raw.githubusercontent.com/Espeonageon/xbacklight-hacks/master/backlight \
      > /usr/bin/backlight && chmod -v +x /usr/bin/backlight"
```

**Using cURL**
```bash
sudo sh -c "curl \
      https://raw.githubusercontent.com/Espeonageon/xbacklight-hacks/master/backlight \
      > /usr/bin/backlight && chmod -v +x /usr/bin/backlight"
```

## Usage:
**With percentages**
- `backlight 20%`
- `backlight 51%`
- `backlight 150%`

**With decimals**
- `backlight 0.2`
- `backlight 0.51`
- `backlight 1.5`
