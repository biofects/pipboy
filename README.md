# Pipboy Theme for Home Assistant

A Fallout-inspired Pipboy terminal theme for Home Assistant with CRT scan line effects, green-on-black color scheme, and retro terminal aesthetics.

![Pipboy Theme Preview](https://via.placeholder.com/800x450)

---

## Donations Appreciated!
If you find this theme useful, please consider donating. Your support is greatly appreciated!

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=TWRQVYJWC77E6)

---

## Requirements

This theme relies on the following:

1. **[Card-mod](https://github.com/thomasloven/lovelace-card-mod)**: **REQUIRED** - Many of the theme's visual effects and custom styling are implemented through card-mod. Without this, the theme will not display correctly.

2. **[HACS (Home Assistant Community Store)](https://hacs.xyz/)**: Recommended for easy installation of card-mod and other custom components.

3. **"Share Tech Mono" font**: For the authentic terminal look. While not strictly required, the theme looks best with this font installed.

## Overview

This theme transforms your Home Assistant interface into a Pipboy-like terminal from the Fallout game series. It features:

- Classic green-on-black color scheme with amber/gold accents
- Retro terminal-style typography using "Share Tech Mono" font
- Animated scan lines and CRT flicker effects
- Glowing elements and terminal-style UI components
- Custom styling for cards, sidebar, buttons, and form fields

## Installation

### Setup Instructions

1. Install **card-mod** via HACS or manually (see [card-mod installation](https://github.com/thomasloven/lovelace-card-mod#installation))
2. Create a `themes` folder in your Home Assistant configuration directory if it doesn't exist already
3. Download the `pipboy.yaml` file from this repository
4. Place it in your `themes` folder
5. Add the following to your `configuration.yaml`:

```yaml
frontend:
  themes: !include_dir_merge_named themes
```

6. Create a `www/images` folder in your Home Assistant configuration directory
7. Download the `pipboy.jpg` background image and place it in the `www/images` folder
8. Restart Home Assistant
9. Go to your user profile and select the "Pipboy" theme

## Usage

### Font Installation

For the best experience, install the "Share Tech Mono" font:

1. Download the font from [Google Fonts](https://fonts.google.com/specimen/Share+Tech+Mono)
2. Add the following to your `configuration.yaml` under the `frontend:` section:

```yaml
frontend:
  themes: !include_dir_merge_named themes
  extra_module_url:
    - https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap
```

### Custom Cards

This theme works best with:

- [card-mod](https://github.com/thomasloven/lovelace-card-mod) (Required)
- [button-card](https://github.com/custom-cards/button-card)
- [mini-graph-card](https://github.com/kalkih/mini-graph-card)

### Biofects Full Menu Integration

To use with ha-biofects-fullmenu:

```yaml
cards:
  - type: custom:ha-biofects-fullmenu
    particleCount: 100
    backgroundColor: '#001a00'
    gridColor: rgba(51, 255, 51, 0.1)
    lineColor: rgba(51, 255, 51, 0.5)
    orbColor: rgba(212, 160, 23, 1)
    particleColor: rgba(51, 255, 51, 0.5)
    glowColor: '#33ff33'
    textColor: '#d4a017'
    itemBorderColor: rgba(51, 255, 51, 0.5)
    hoverGlowColor: rgba(51, 255, 51, 0.8)
    defaultItemColor: '#d4a017'
```

### Custom Sidebar

Add this to your sidebar configuration:

```yaml
sidebar:
  style: |
    :host {
      --sidebar-background-color: #3a3a2d;
      --sidebar-text-color: #d4a017;
      --sidebar-icon-color: #d4a017;
      --sidebar-selected-background-color: rgba(212, 160, 23, 0.2);
      --sidebar-selected-icon-color: #e6b923;
      --sidebar-selected-text-color: #e6b923;
      background-color: var(--sidebar-background-color) !important;
      color: var(--sidebar-text-color) !important;
      box-shadow: 
        inset -4px 0 8px rgba(0, 0, 0, 0.3),
        4px 0 12px rgba(0, 0, 0, 0.4) !important;
      position: relative;
      font-family: "Share Tech Mono", monospace !important;
    }
    
    /* Additional sidebar styling in theme file */
```

## Customization

### Changing Colors

- Primary green: `#33ff33`
- Secondary green: `#66ff66`
- Background: `#001a00`
- Amber text: `#d4a017`
- Amber highlight: `#e6b923`
- Sidebar background: `#3a3a2d`

### Modifying Animations

The CRT scan line and flicker effects can be adjusted in the `card-mod-view` section of the theme file:

- `scanline` animation: Controls the vertical scan line effect
- `flicker` animation: Controls the screen flicker effect

## Features

- **CRT Effects**: Realistic scan lines and screen flicker
- **Custom Form Fields**: Styled inputs, dropdowns, and buttons
- **Calendar Integration**: Fallout-styled calendar days
- **Glowing Elements**: Subtle glow effects on interactive elements
- **Responsive Design**: Works on both desktop and mobile
- **Holistic Theme**: Consistent styling across all Home Assistant UI elements

## Troubleshooting

If you don't see the full theme effects:

1. Make sure card-mod is installed correctly
2. Check that the theme is selected in your user profile
3. Verify that the background image path is correct
4. Try hard-refreshing your browser (Ctrl+F5 or Cmd+Shift+R)
5. Confirm that the theme is included in your configuration.yaml

## Credits

- Inspired by the Pipboy interface from the Fallout game series
- Background image source: [placeholder for source]
- Font: Share Tech Mono by Google Fonts

## License

This theme is released under the MIT License.

---

*"War... War never changes, but your Home Assistant theme can!"*
