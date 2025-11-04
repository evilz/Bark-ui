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

### Button
Versatile button component with multiple variants, sizes, and color schemes.

**Variants:** solid, outline, ghost
**Sizes:** sm, md, lg
**Colors:** primary, secondary, success, danger

### Card
Container component with different elevation styles.

**Variants:** elevated, outlined, flat
**Padding:** sm, md, lg, none

### Input
Fully-featured input component with labels, validation, and helper text.

**Sizes:** sm, md, lg
**Features:** Labels, helper text, error states, disabled state

### Badge
Display status or category information.

**Variants:** solid, outline, subtle
**Colors:** primary, secondary, success, danger, warning, info
**Sizes:** sm, md, lg

### Alert
Display important messages to users.

**Variants:** info, success, warning, error
**Features:** Title and content areas

### Spinner
Loading indicator component.

**Sizes:** sm, md, lg
**Colors:** primary, secondary, success

### Container
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
