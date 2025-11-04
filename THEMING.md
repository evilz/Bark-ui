# Bark UI Theming Guide

Bark UI uses a comprehensive theming system inspired by park-ui with **Radix UI Colors** that allows you to customize the appearance of all components by changing CSS custom properties (CSS variables).

## Radix UI Colors

All default theme colors are based on [Radix UI's color system](https://www.radix-ui.com/colors), which provides:
- **Scientific design**: Colors designed for optimal readability and accessibility
- **12-step scales**: Each color has 12 shades for different use cases
- **Consistent contrast**: Guaranteed WCAG AA contrast ratios
- **Beautiful palettes**: Professional, harmonious color combinations

## Table of Contents

- [Quick Start](#quick-start)
- [Semantic Tokens](#semantic-tokens)
- [Radix UI Color Scales](#radix-ui-color-scales)
- [Using Predefined Themes](#using-predefined-themes)
- [Creating Custom Themes](#creating-custom-themes)
- [Color Tokens](#color-tokens)
- [Radius Tokens](#radius-tokens)
- [Shadow Tokens](#shadow-tokens)

## Quick Start

### Apply a Predefined Theme

Add a `data-theme` attribute to your HTML element:

```html
<html lang="en" data-theme="blue">
```

Available themes (all use Radix UI color scales):
- `neutral` (default) - Radix UI Slate scale
- `blue` - Radix UI Blue/Sky scales
- `green` - Radix UI Green scale
- `purple` - Radix UI Violet scale
- `crimson` - Radix UI Crimson scale
- `gray` - Radix UI Gray scale

### Create a Custom Theme

Override CSS custom properties in your stylesheet:

```css
:root {
    --colors-color-palette-default: 37 99 235;  /* Blue */
    --colors-color-palette-fg: 255 255 255;     /* White */
}
```

## Semantic Tokens

Bark UI's theme revolves around semantic color tokens that define the meaning and purpose of colors in your application. This approach makes it easy to maintain consistency and change themes globally.

### Background Tokens

Background colors are used for backdrop elements like containers, cards, and sections.

| Token Name       | CSS Variable                | Description                        |
|------------------|-----------------------------|------------------------------------|
| `bg.canvas`      | `--bg-canvas`              | App background                     |
| `bg.default`     | `--bg-default`             | Default background for components  |
| `bg.subtle`      | `--bg-subtle`              | Subtle background                  |
| `bg.muted`       | `--bg-muted`               | Muted background                   |
| `bg.emphasized`  | `--bg-emphasized`          | Emphasized background              |
| `bg.disabled`    | `--bg-disabled`            | Disabled state background          |

### Foreground Tokens

Foreground colors are used for text, icons, and other elements that stand out against backgrounds.

| Token Name       | CSS Variable                | Description                        |
|------------------|-----------------------------|------------------------------------|
| `fg.default`     | `--fg-default`             | Default text color                 |
| `fg.muted`       | `--fg-muted`               | Muted text color                   |
| `fg.subtle`      | `--fg-subtle`              | Subtle text color (placeholders)   |
| `fg.disabled`    | `--fg-disabled`            | Disabled text color                |

### Border Tokens

Border tokens establish hierarchy and separate components.

| Token Name       | CSS Variable                | Description                        |
|------------------|-----------------------------|------------------------------------|
| `border.default` | `--border-default`         | Default border color               |
| `border.subtle`  | `--border-subtle`          | Subtle border color                |
| `border.muted`   | `--border-muted`           | Muted border color                 |
| `border.disabled`| `--border-disabled`        | Disabled border color              |
| `border.outline` | `--border-outline`         | Outline border color               |

### Color Palette Tokens

Color palette tokens are your accent colors that direct user attention to specific actions and interactive elements.

| Token Name                | CSS Variable                      | Description                    |
|---------------------------|-----------------------------------|--------------------------------|
| `colorPalette.default`    | `--color-palette-default`        | Primary accent color           |
| `colorPalette.emphasized` | `--color-palette-emphasized`     | Darker accent shade            |
| `colorPalette.muted`      | `--color-palette-muted`          | Muted accent shade             |
| `colorPalette.subtle`     | `--color-palette-subtle`         | Subtle accent shade            |
| `colorPalette.fg`         | `--color-palette-fg`             | Foreground on accent           |
| `colorPalette.text`       | `--color-palette-text`           | Text in accent color           |

### Semantic Color Tokens

Special-purpose colors for common UI patterns.

| Token Name    | CSS Variable       | Description                |
|---------------|--------------------|----------------------------|
| `success`     | `--success`        | Success state color        |
| `success.fg`  | `--success-fg`     | Text on success background |
| `error`       | `--error`          | Error state color          |
| `error.fg`    | `--error-fg`       | Text on error background   |
| `warning`     | `--warning`        | Warning state color        |
| `warning.fg`  | `--warning-fg`     | Text on warning background |
| `info`        | `--info`           | Info state color           |
| `info.fg`     | `--info-fg`        | Text on info background    |

## Radix UI Color Scales

Bark UI uses **Radix UI's color system** for all default theme colors. Radix UI provides scientifically designed color scales with optimal contrast and accessibility.

### Why Radix UI Colors?

- **Accessibility First**: All colors meet WCAG AA contrast requirements
- **12-Step Scales**: Each color has 12 carefully calibrated shades
- **Consistent System**: Predictable color behavior across all scales
- **Beautiful Design**: Professional, harmonious color combinations
- **Open Source**: Free to use, well-documented

### Color Scale Mapping

The default theme uses Radix UI's **Slate** scale:

| Semantic Token | Radix Scale Step | Purpose |
|---------------|------------------|---------|
| `bg.canvas` | slate.1 | App background |
| `bg.default` | slate.2 | Component background |
| `bg.subtle` | slate.3 | Subtle background |
| `bg.muted` | slate.4 | Muted background |
| `bg.emphasized` | slate.5 | Emphasized background |
| `border.default` | slate.6 | Default borders |
| `border.muted` | slate.7 | Muted borders |
| `border.outline` | slate.8 | Outline borders |
| `fg.subtle` | slate.10 | Subtle text |
| `fg.muted` | slate.11 | Muted text |
| `fg.default` | slate.12 | Primary text |

### Semantic Colors

Semantic colors use dedicated Radix UI scales:

- **Success**: Green scale (step 9)
- **Error**: Red scale (step 9)
- **Warning**: Amber scale (step 9)
- **Info**: Blue scale (step 9)

### Creating Themes with Radix Colors

When creating custom themes, we recommend using Radix UI color scales:

```css
/* Custom theme with Radix UI Indigo scale */
[data-theme="indigo"] {
    --colors-color-palette-default: 62 99 221;    /* indigo.9 */
    --colors-color-palette-emphasized: 54 79 199; /* indigo.10 */
    --colors-color-palette-fg: 255 255 255;
}
```

Reference: [Radix UI Colors Documentation](https://www.radix-ui.com/colors)

## Using Predefined Themes

### In HTML

```html
<!DOCTYPE html>
<html lang="en" data-theme="blue">
<head>
    <!-- ... -->
</head>
<body>
    <!-- Your content -->
</body>
</html>
```

### Dynamically with JavaScript

```javascript
// Change theme
document.documentElement.setAttribute('data-theme', 'purple');

// Remove theme (revert to default)
document.documentElement.removeAttribute('data-theme');
```

### In Blazor

```razor
@code {
    private string currentTheme = "neutral";
    
    protected override void OnAfterRender(bool firstRender)
    {
        if (firstRender)
        {
            JSRuntime.InvokeVoidAsync("eval", 
                $"document.documentElement.setAttribute('data-theme', '{currentTheme}')");
        }
    }
}
```

## Creating Custom Themes

### Method 1: Override in CSS

Create a new CSS file or add to your existing stylesheet:

```css
/* Custom Theme */
[data-theme="ocean"] {
    /* Accent Colors - Ocean Blue */
    --colors-color-palette-default: 6 95 212;
    --colors-color-palette-emphasized: 8 76 158;
    --colors-color-palette-muted: 59 130 246;
    --colors-color-palette-subtle: 147 197 253;
    --colors-color-palette-fg: 255 255 255;
    --colors-color-palette-text: 29 78 216;
    
    /* Optional: Customize other tokens */
    --colors-bg-canvas: 248 250 252;
    --radii-l2: 0.5rem; /* More rounded corners */
}
```

Then apply it:

```html
<html lang="en" data-theme="ocean">
```

### Method 2: Inline in Blazor Component

```razor
<div style="--color-palette-default: rgb(var(--colors-success));">
    <BarkButton>Success Colored Button</BarkButton>
</div>
```

### Method 3: Generate from Brand Colors

```css
:root {
    /* Define your brand colors */
    --brand-primary: 168 85 247;      /* Purple */
    --brand-primary-dark: 126 34 206;
    --brand-primary-light: 216 180 254;
    
    /* Map to semantic tokens */
    --colors-color-palette-default: var(--brand-primary);
    --colors-color-palette-emphasized: var(--brand-primary-dark);
    --colors-color-palette-subtle: var(--brand-primary-light);
    --colors-color-palette-fg: 255 255 255;
}
```

## Color Tokens

All color tokens use RGB format for maximum flexibility with opacity:

```css
/* Define as RGB values (no rgb() wrapper) */
--colors-color-palette-default: 37 99 235;

/* Use with rgb() or rgba() */
background-color: rgb(var(--colors-color-palette-default));
background-color: rgba(var(--colors-color-palette-default) / 0.5);
```

### Why RGB Format?

RGB format allows you to easily apply opacity:

```css
/* With RGB format */
--my-color: 37 99 235;
background: rgba(var(--my-color) / 0.5); /* 50% opacity */

/* Without RGB format (hex or rgb string) */
--my-color: #2563eb;
background: rgba(var(--my-color) / 0.5); /* Won't work! */
```

## Radius Tokens

Control the roundness of component corners:

| Token  | CSS Variable   | Default Value | Usage                           |
|--------|----------------|---------------|---------------------------------|
| `l1`   | `--radii-l1`   | 0.25rem      | Small elements (badges)         |
| `l2`   | `--radii-l2`   | 0.375rem     | Medium elements (buttons)       |
| `l3`   | `--radii-l3`   | 0.5rem       | Large elements (cards)          |

### Customizing Border Radius

```css
:root {
    /* Make everything more rounded */
    --radii-l1: 0.5rem;
    --radii-l2: 0.75rem;
    --radii-l3: 1rem;
}

/* Or make everything sharp */
:root {
    --radii-l1: 0;
    --radii-l2: 0;
    --radii-l3: 0;
}
```

## Shadow Tokens

Control elevation and depth:

| Token  | CSS Variable    | Usage                              |
|--------|-----------------|------------------------------------|
| `xs`   | `--shadows-xs`  | Minimal elevation                  |
| `sm`   | `--shadows-sm`  | Small elevation (cards)            |
| `md`   | `--shadows-md`  | Medium elevation (modals)          |

### Customizing Shadows

```css
:root {
    /* Stronger shadows */
    --shadows-sm: 0 2px 8px 0 rgba(0, 0, 0, 0.15);
    --shadows-md: 0 8px 16px -2px rgba(0, 0, 0, 0.2);
    
    /* Or remove shadows entirely */
    --shadows-xs: none;
    --shadows-sm: none;
    --shadows-md: none;
}
```

## Examples

### Dark Mode Theme

```css
[data-theme="dark"] {
    --colors-bg-canvas: 10 10 10;
    --colors-bg-default: 23 23 23;
    --colors-bg-subtle: 38 38 38;
    --colors-bg-muted: 64 64 64;
    --colors-bg-emphasized: 82 82 82;
    
    --colors-fg-default: 250 250 250;
    --colors-fg-muted: 163 163 163;
    --colors-fg-subtle: 115 115 115;
    
    --colors-border-default: 64 64 64;
    --colors-border-subtle: 38 38 38;
    --colors-border-muted: 82 82 82;
    
    --colors-color-palette-default: 96 165 250;
    --colors-color-palette-emphasized: 147 197 253;
    --colors-color-palette-fg: 30 58 138;
}
```

### High Contrast Theme

```css
[data-theme="high-contrast"] {
    --colors-bg-canvas: 255 255 255;
    --colors-bg-default: 255 255 255;
    --colors-fg-default: 0 0 0;
    
    --colors-color-palette-default: 0 0 0;
    --colors-color-palette-fg: 255 255 255;
    
    --colors-border-default: 0 0 0;
    --radii-l1: 0;
    --radii-l2: 0;
    --radii-l3: 0;
}
```

## Best Practices

1. **Use Semantic Tokens**: Always reference semantic tokens (e.g., `--fg-default`) rather than creating new color variables
2. **Test Accessibility**: Ensure sufficient contrast ratios (WCAG AA: 4.5:1 for normal text, 3:1 for large text)
3. **Consistent Palette**: Stick to one accent color for your theme
4. **Document Custom Themes**: If creating custom themes, document the token values for your team
5. **Test All States**: Verify hover, focus, active, and disabled states with your theme
6. **Mobile Testing**: Test your theme on mobile devices to ensure readability

## Troubleshooting

### Colors Not Updating

Make sure you're using the correct format:

```css
/* ❌ Wrong */
--colors-bg-default: #ffffff;

/* ✅ Correct */
--colors-bg-default: 255 255 255;
```

### Theme Not Applying

Check that the theme CSS file is loaded:

```html
<link rel="stylesheet" href="themes.css" />
```

### Partial Theme Application

Ensure you're setting the data-theme attribute on the `<html>` element, not `<body>`:

```html
<!-- ✅ Correct -->
<html data-theme="blue">

<!-- ❌ Wrong -->
<body data-theme="blue">
```

## Resources

- [Park UI Documentation](https://park-ui.com/docs/theming)
- [CSS Custom Properties (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
- [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/WCAG21/quickref/)
