# Bark UI

Beautifully designed Blazor components inspired by park-ui with Radix UI colors

![Bark UI Demo](https://github.com/user-attachments/assets/c4927bad-256f-485f-996f-5be295d5a5ed)

## Overview

Bark UI is a comprehensive .NET Blazor component library that provides customizable, accessible components with sensible defaults. Built with .NET 9.0 and using **Radix UI's scientifically designed color system**, it gives developers complete control over how components are built and styled.

## Features

- 🎨 **Radix UI Colors** - Professional color system with optimal contrast and accessibility
- 🎭 **Fully Themable** - Complete theming system with semantic tokens
- 🚀 **Modern** - Built with .NET 9.0 and Blazor
- 📦 **Component Library** - Rich set of UI components
- 🎯 **Sensible Defaults** - Works great out of the box
- 🔧 **Flexible** - Easy to customize and extend
- ♿ **Accessible** - WCAG AA compliant colors

## Components

### Disclosure

#### Accordion
Expandable content sections that can be toggled open and closed.

**Variants:** default, outline, ghost
**Features:** Multiple item support, expandable sections

#### Collapsible
Toggle content visibility with a customizable trigger.

**Features:** Custom trigger content, smooth animations

### Display

#### Avatar
Display user profile images or initials.

**Sizes:** sm, md, lg, xl
**Shapes:** circle, square
**Features:** Image support, automatic initials generation

#### Badge
Display status or category information.

**Variants:** solid, outline, subtle
**Colors:** primary, secondary, success, danger, warning, info
**Sizes:** sm, md, lg

#### Card
Container component with different elevation styles.

**Variants:** elevated, outlined, flat
**Padding:** sm, md, lg, none

#### Carousel
Slideshow component for cycling through content.

**Features:** Navigation controls, indicator dots, looping, customizable

#### Icon
Flexible icon wrapper component.

**Sizes:** xs, sm, md, lg, xl
**Features:** Accessible with aria-labels

#### Table
Data table with sorting and styling options.

**Variants:** default, simple
**Features:** Striped rows, hoverable rows, responsive

### Feedback

#### Alert
Display important messages to users.

**Variants:** info, success, warning, error
**Features:** Title and content areas

#### Progress
Visual progress indicator.

**Sizes:** sm, md, lg
**Colors:** primary, secondary, success, danger
**Features:** Labels, striped, animated

#### Skeleton
Loading placeholder for content.

**Variants:** text, circle, rectangle
**Features:** Animated pulse effect

#### Spinner
Loading indicator component.

**Sizes:** sm, md, lg
**Colors:** primary, secondary, success

#### Toast
Notification messages with dismissible option.

**Variants:** default, success, warning, error
**Features:** Dismissible, auto-animation

### Forms

#### Button
Versatile button component with multiple variants, sizes, and color schemes.

**Variants:** solid, outline, ghost
**Sizes:** sm, md, lg
**Colors:** primary, secondary, success, danger

#### Input
Text input component with labels, validation, and helper text.

**Sizes:** sm, md, lg
**Features:** Labels, helper text, error states, disabled state

#### Checkbox
Checkbox input with support for different sizes.

**Sizes:** sm, md, lg
**Features:** Custom label, disabled state

#### Switch
Toggle switch with customizable label positions.

**Sizes:** sm, md, lg
**Features:** Label positioning, checked state

#### Textarea
Multi-line text input with label and validation.

**Sizes:** sm, md, lg
**Features:** Adjustable rows, labels, helper text, error states

#### Select
Dropdown select with custom styling.

**Sizes:** sm, md, lg
**Features:** Labels, placeholder, helper text, error states

#### Slider
Range slider with optional value display.

**Sizes:** sm, md, lg
**Features:** Min/max values, step control, value display

#### Radio Group
Radio button groups with vertical/horizontal layouts.

**Sizes:** sm, md, lg
**Features:** Single selection, orientation control

#### Number Input
Number input with increment/decrement buttons.

**Sizes:** sm, md, lg
**Features:** Min/max bounds, step control, validation

#### Pin Input
PIN/OTP input with multiple digit fields.

**Sizes:** sm, md, lg
**Features:** Custom length, masking support

#### File Upload
File upload with drag-and-drop support.

**Features:** Multiple files, file type filtering, drag-and-drop

#### Rating Group
Star rating component for user feedback.

**Sizes:** sm, md, lg
**Features:** Custom max rating, custom icons

#### Segment Group
Segmented control for view switching.

**Sizes:** sm, md, lg
**Features:** Multiple segments, active state

#### Toggle Group
Toggle button group for option selection.

**Sizes:** sm, md, lg
**Features:** Multiple toggles, variants

#### Tags Input
Tags input with add/remove functionality.

**Sizes:** sm, md, lg
**Features:** Add tags on Enter, remove tags

#### Radio Card Group
Card-based radio selection for rich options.

**Features:** Grid layout, custom columns, checkmark indicator

#### Field
Form field wrapper with label and error handling.

**Features:** Labels, helper text, error messages

#### Fieldset
Fieldset for grouping related form fields.

**Features:** Legend, helper text, disabled state

#### Editable
Inline editable text component.

**Features:** Click to edit, save/cancel actions

#### Color Picker
Color picker with hex input.

**Features:** Visual picker, text input, preview

#### Date Picker
Date input with native date picker.

**Sizes:** sm, md, lg
**Features:** Labels, helper text, error states

#### Combobox
Searchable dropdown with filtering.

**Features:** Type to filter, custom options

### Layout

#### Container
Responsive container with max-width constraints.

**Max Width:** sm, md, lg, xl, full
**Features:** Centered content option

## Getting Started

### Prerequisites

- .NET 9.0 SDK or later

### Installation

1. Clone the repository:
```bash
git clone https://github.com/evilz/Bark-ui.git
cd Bark-ui
```

2. Build the solution:
```bash
dotnet build
```

3. Run the demo application:
```bash
cd src/BarkUI.Demo
dotnet run
```

### Using in Your Project

1. Add a reference to the BarkUI.Components project:
```bash
dotnet add reference path/to/BarkUI.Components/BarkUI.Components.csproj
```

2. Add the namespace to your `_Imports.razor`:
```razor
@using BarkUI.Components
```

3. Start using components:
```razor
<BarkButton ColorScheme="primary">Click Me</BarkButton>
<BarkCard Variant="elevated">
    <h3>Card Title</h3>
    <p>Card content goes here</p>
</BarkCard>
```

## Examples

### Button Examples

```razor
<!-- Solid button -->
<BarkButton>Default Button</BarkButton>

<!-- Outline button -->
<BarkButton Variant="outline" ColorScheme="primary">Outline</BarkButton>

<!-- Ghost button -->
<BarkButton Variant="ghost" ColorScheme="secondary">Ghost</BarkButton>

<!-- Different sizes -->
<BarkButton Size="sm">Small</BarkButton>
<BarkButton Size="md">Medium</BarkButton>
<BarkButton Size="lg">Large</BarkButton>

<!-- Disabled state -->
<BarkButton Disabled="true">Disabled</BarkButton>
```

### Input Examples

```razor
<!-- Basic input -->
<BarkInput Label="Email" Placeholder="Enter your email" />

<!-- Input with error -->
<BarkInput 
    Label="Password" 
    Type="password" 
    HasError="true" 
    HelperText="Password is required" />

<!-- Disabled input -->
<BarkInput Label="Disabled" Disabled="true" />
```

### Card Examples

```razor
<!-- Elevated card -->
<BarkCard Variant="elevated">
    <h3>Elevated Card</h3>
    <p>Content with shadow effect</p>
</BarkCard>

<!-- Outlined card -->
<BarkCard Variant="outlined" Padding="lg">
    <h3>Outlined Card</h3>
    <p>Content with border</p>
</BarkCard>
```

### Alert Examples

```razor
<BarkAlert Variant="info" Title="Information">
    This is an informational message.
</BarkAlert>

<BarkAlert Variant="success" Title="Success">
    Operation completed successfully!
</BarkAlert>

<BarkAlert Variant="warning" Title="Warning">
    Please review this warning.
</BarkAlert>

<BarkAlert Variant="error" Title="Error">
    An error occurred.
</BarkAlert>
```

## Customization

All components support custom CSS classes through the `AdditionalAttributes` parameter:

```razor
<BarkButton class="my-custom-class">Custom Styled Button</BarkButton>
```

Components use scoped CSS, so you can override styles in your own stylesheets:

```css
.bark-button {
    /* Your custom styles */
}
```

## Project Structure

```
Bark-ui/
├── src/
│   ├── BarkUI.Components/      # Component library
│   │   ├── BarkButton.razor
│   │   ├── BarkCard.razor
│   │   ├── BarkInput.razor
│   │   ├── BarkBadge.razor
│   │   ├── BarkAlert.razor
│   │   ├── BarkSpinner.razor
│   │   └── BarkContainer.razor
│   └── BarkUI.Demo/            # Demo application
│       └── Components/
│           └── Pages/
│               └── Home.razor
├── BarkUI.slnx
└── README.md
```

## Technology Stack

- **.NET 9.0** - Latest version of .NET
- **Blazor** - Modern web UI framework
- **Razor Components** - Component-based architecture
- **CSS** - Scoped CSS for styling

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the MIT License.

## Inspiration

Bark UI is inspired by [park-ui](https://park-ui.com/), bringing similar design principles and component patterns to the .NET Blazor ecosystem.
