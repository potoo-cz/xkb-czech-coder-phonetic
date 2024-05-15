# Why

If you do not use the Czech language often, it might make sense to you to use `us` layout all the time 
and access to Czech characters by using the modifier button, for example:

* `AltGr + s` = `š`
* `AltGr + Shift + s` = `Š`

---

# Why to fork

This project is a fork, original idea and implementation: https://github.com/michalkahle/czech-coder-xkb

The original project mimics the native Czech keyboard layout,
but for some people _(foreigners)_ using it may be close to impossible. Learning it might be useful to have in skillset, 
but for me phonetic version from Android's virtual keyboard has much more sense.

Tutorial on how to type with native layout: https://www.czechtime.cz/article/how-to-type-czech-characters-on-keyboard/

If you are brave you may open the spoiler below.

<details>
  <summary>Native Czech keyboard layout</summary>

| No modifier | Shift  | AltGr        | AltGr + Shift |
|-------------|--------|--------------|---------------|
| `` ` ``     | `~`    | `;`          | `<modifier>`  |
| `2`         | `@`    | `ě`          | `Ě`           |
| `3`         | `#`    | `š`          | `Š`           |
| `4`         | `$`    | `č`          | `Č`           |
| `5`         | `%`    | `ř`          | `Ř`           |
| `6`         | `^`    | `ž`          | `Ž`           |
| `7`         | `&`    | `ý`          | `Ý`           |
| `8`         | `*`    | `á`          | `Á`           |
| `9`         | `(`    | `í`          | `Í`           |
| `0`         | `)`    | `é`          | `É`           |
| `=`         | `+`    | `<modifier>` | `<modifier>`  |
| `e`         | `E`    | `e`          | `€`           |
| `[`         | `{`    | `ú`          | `Ú`           |
| `;`         | `:`    | `ů`          | `Ů`           |
| `'`         | `"`    | `§`          | `"`           |
| ` \ `       | ` \| ` | `<modifier>` | `'`           |

Combinations `` AltGr + Shift + ` ``, `AltGt + =`, `AltGt + Shift =` and `AltGr + \ ` are modifiers which you need to press, release, and press the next button/combination:

| Raw button | `AltrGt + =`, | `AltrGt + =`, `Shift +` | `AltrGt + Shift + =`, | `AltrGt + Shift + =`, `Shift +` |
|------------|---------------|-------------------------|-----------------------|---------------------------------|
| `n`        | `ń`           | `Ń`                     | `ň`                   | `Ň`                             |
| `d`        | —             | —                       | `ď`                   | `Ď`                             |
| `t`        | —             | —                       | `ť`                   | `Ť`                             |
</details>

---

# Phonetic layout

This layout is phonetic which means if you want to type the character `č` you need to press `AltGr + c`.

However, some letters have three variants: `e`, `é`, and `ě`. If it happens you can find a third variant moved to the button above, which means to type `ě` you need to press `AltGt + 3`.

<details>
  <summary>Phonetic layout</summary>


| No modifier | Shift  | AltGr        | AltGr + Shift |
|-------------|--------|--------------|---------------|
| `` ` ``     | `~`    | `;`          | `<modifier>`  |
| `3`         | `#`    | `ě`          | `Ě`           |
| `4`         | `$`    | `€`          | —             |
| `7`         | `&`    | `ů`          | `Ů`           |
| `=`         | `+`    | `<modifier>` | `<modifier>`  |
| `e`         | `E`    | `é`          | `É`           |
| `r`         | `R`    | `ř`          | `Ř`           |
| `t`         | `T`    | `ť`          | `Ť`           |
| `y`         | `Y`    | `ý`          | `Ý`           |
| `u`         | `U`    | `ú`          | `Ú`           |
| `i`         | `I`    | `í`          | `Í`           |
| `o`         | `O`    | `ó`          | `Ó`           |
| `a`         | `A`    | `á`          | `Á`           |
| `s`         | `S`    | `š`          | `Š`           |
| `d`         | `D`    | `ď`          | `Ď`           |
| `'`         | `"`    | `§`          | `"`           |
| ` \ `       | ` \| ` | `<modifier>` | `'`           |
| `z`         | `Z`    | `ž`          | `Ž`           |
| `c`         | `C`    | `č`          | `Č`           |
| `n`         | `N`    | `ň`          | `Ň`           |

_You still can use modifiers as in native layout, you just don't need to._
</details>

---

# Installation

You need to put files from this repository `/.config/xkb/` to your local directory `~/.config/kxb/`, 

**WARNING**: you may need to merge files manually if your configuration is not pristine. Best luck!

# X11 Configuration

https://github.com/michalkahle/czech-coder-xkb?tab=readme-ov-file#installation

# Wayland/Sway configuration

https://github.com/michalkahle/czech-coder-xkb?tab=readme-ov-file#wayland

Modify sway config file `~/.config/sway/config` and set 2 layouts switchable by `CapsLock`:

```bash
$ cat ~/.config/sway/config

...
input "type:keyboard" {
    xkb_layout "cz(coder_phonetic),us"
    xkb_options "grp:caps_toggle,grp_led:caps"
    repeat_delay 400
    repeat_rate 60
}
...
```

# Additional reading

If you want to understand `xkb` better there is no better place than [An Unreliable Guide to XKB Configuration by Doug Palmer.](https://www.charvolant.org/doug/xkb/html/xkb.html).