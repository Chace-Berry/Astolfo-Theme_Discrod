# Astolfo Theme for Discord (Vencord)

A beautiful Astolfo-themed Discord background with custom styling, based on the BasicBackground theme by mwittrien. This theme is designed for use with Vencord and BetterDiscord.

## Features
- Custom background image and colors with adjustable opacity overlay
- Adjustable transparency settings
- **Custom pink accent color override** - Replaces Discord's default blurple with custom pink
- **Clean message appearance** - Chat bubbles disabled for minimal design
- **No version notifications** - Update notices removed for cleaner experience
- Removes watermark
- Adds extra space underneath the username/timestamp before messages

## Installation
1. Download or copy the contents of `Astolfo.css` to your Vencord themes folder:
   - `C:\Users\<your-username>\AppData\Roaming\Vencord\themes\Astolfo.css`
2. Enable the theme in Vencord or BetterDiscord.
3. **Important:** Refresh Discord (Ctrl+R) or restart Discord completely for accent color changes to take effect.

## Customization
To change the accent color, modify these variables in the CSS file:
```css
--accentcolor: 250, 182, 241 !important;        /* RGB values for your desired color */
--accentcolor_s: 250, 182, 241 !important;      /* Same RGB values */
```
And update all the `--brand-experiment` variables with your desired `rgb()` color.

To adjust background opacity, modify the overlay values:
```css
--background: linear-gradient(rgba(0, 0, 0, 0.364), rgba(0, 0, 0, 0.441)), url(image-url);
```
- Lower values (e.g., 0.2) = more visible background
- Higher values (e.g., 0.8) = darker overlay, less visible background

To re-enable chat bubbles:
```css
--messagetransparency: 0.5;  /* Change from 0 to desired transparency level */
```

## Source Code Reference
This theme imports and overrides the [BasicBackground](https://mwittrien.github.io/BetterDiscordAddons/Themes/BasicBackground/BasicBackground.css) theme:

```css
@import url(https://mwittrien.github.io/BetterDiscordAddons/Themes/BasicBackground/BasicBackground.css);
```

### Custom Modifications

#### Accent Color Override
The theme includes comprehensive overrides to replace Discord's default blurple accent color with a custom pink color (`rgb(250, 182, 241)`):

```css
/* Custom accent color variables */
--accentcolor: 250, 182, 241 !important;
--accentcolor_s: 250, 182, 241 !important;

/* Force override Discord's brand colors */
:root {
    --brand-experiment: rgb(250, 182, 241) !important;
    --brand-experiment-100: rgb(250, 182, 241) !important;
    /* ... (continues for all brand color variants) */
    --brand-experiment-900: rgb(250, 182, 241) !important;
}

/* Override specific blurple selectors */
.base__2b1f5[style*="background-color: rgb(88, 101, 242)"] {
    background-color: rgb(250, 182, 241) !important;
}
```

This ensures the pink accent color appears consistently across:
- Buttons and interactive elements
- Links and mentions
- Status indicators
- Focus states
- All Discord UI elements that use the brand color

#### Chat Spacing Modification
The following code was added to create extra space underneath the user info (username/timestamp) before messages:

```css
/* Add space underneath user info (username/timestamp) before chat bubble */
.header_c19a55 {
    margin-bottom: 8px !important;
}
```

You can adjust the `8px` value to change the spacing.

#### Chat Bubbles Disabled
Chat bubbles have been disabled for a cleaner, minimal message appearance:

```css
--messagetransparency: 0;
```

This removes the background boxes around messages. To re-enable chat bubbles, change the value to `0.5` or higher.

#### Version Check Removed
The theme update notification has been completely disabled:

```css
html:only-child > head + body div.app_a3002d > div.app__160d8::before {
    display: none !important;
    content: none !important;
    visibility: hidden !important;
}
```

#### Background Opacity
The background includes a semi-transparent overlay for better text readability:

```css
--background: linear-gradient(rgba(0, 0, 0, 0.364), rgba(0, 0, 0, 0.441)), url(https://w.wallhaven.cc/full/mp/wallhaven-mpx988.png);
```

The overlay values can be adjusted to change background visibility.

## Credits
- Astolfo Theme by ♡꧁𝒲ø𝓁𝒻𝒾ℯ꧂♡

- Based on BasicBackground by mwittrien

## License
This theme is for personal use. Please respect the original authors and do not redistribute without permission.
