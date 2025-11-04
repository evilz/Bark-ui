# Bark UI Components Documentation

Complete reference for all Bark UI components.

## BarkButton

A versatile button component with multiple variants and customization options.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Content to display inside the button |
| Variant | string | "solid" | Button style: "solid", "outline", or "ghost" |
| Size | string | "md" | Button size: "sm", "md", or "lg" |
| ColorScheme | string | "primary" | Color scheme: "primary", "secondary", "success", or "danger" |
| Disabled | bool | false | Whether the button is disabled |
| Type | string | "button" | HTML button type: "button", "submit", or "reset" |
| OnClick | EventCallback<MouseEventArgs> | - | Event callback when button is clicked |

### Usage

```razor
<BarkButton Variant="solid" ColorScheme="primary" Size="md" OnClick="HandleClick">
    Click Me
</BarkButton>
```

---

## BarkCard

A container component with different elevation and styling options.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Content to display inside the card |
| Variant | string | "elevated" | Card style: "elevated", "outlined", or "flat" |
| Padding | string | "md" | Padding size: "none", "sm", "md", or "lg" |

### Usage

```razor
<BarkCard Variant="elevated" Padding="md">
    <h3>Card Title</h3>
    <p>Card content goes here</p>
</BarkCard>
```

---

## BarkInput

A fully-featured input component with labels, validation, and helper text.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Id | string? | auto-generated | HTML id attribute |
| Label | string? | null | Label text displayed above the input |
| Type | string | "text" | HTML input type |
| Placeholder | string? | null | Placeholder text |
| Value | string? | null | Current value |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Size | string | "md" | Input size: "sm", "md", or "lg" |
| Disabled | bool | false | Whether the input is disabled |
| HasError | bool | false | Whether to display error state |
| HelperText | string? | null | Helper or error text displayed below input |

### Usage

```razor
<BarkInput 
    Label="Email" 
    Type="email" 
    Placeholder="Enter your email"
    @bind-Value="emailValue"
    HelperText="We'll never share your email" />
```

---

## BarkBadge

Display status, categories, or labels with various styles.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Content to display inside the badge |
| Variant | string | "solid" | Badge style: "solid", "outline", or "subtle" |
| ColorScheme | string | "primary" | Color scheme: "primary", "secondary", "success", "danger", "warning", or "info" |
| Size | string | "md" | Badge size: "sm", "md", or "lg" |

### Usage

```razor
<BarkBadge Variant="solid" ColorScheme="success" Size="md">
    Active
</BarkBadge>
```

---

## BarkAlert

Display important messages to users with different severity levels.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Alert message content |
| Title | string? | null | Optional title displayed above the content |
| Variant | string | "info" | Alert type: "info", "success", "warning", or "error" |

### Usage

```razor
<BarkAlert Variant="success" Title="Success">
    Your changes have been saved successfully!
</BarkAlert>
```

---

## BarkSpinner

A loading indicator component with customizable size and color.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Size | string | "md" | Spinner size: "sm", "md", or "lg" |
| ColorScheme | string | "primary" | Color scheme: "primary", "secondary", or "success" |

### Usage

```razor
<BarkSpinner Size="md" ColorScheme="primary" />
```

---

## BarkContainer

A responsive container component with max-width constraints.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Content to display inside the container |
| MaxWidth | string | "lg" | Maximum width: "sm", "md", "lg", "xl", or "full" |
| CenterContent | bool | false | Whether to center content vertically and horizontally |

### Usage

```razor
<BarkContainer MaxWidth="lg">
    <h1>Page Content</h1>
    <p>Your content goes here</p>
</BarkContainer>
```

---

## Customization

### Using Additional Attributes

All components support passing additional HTML attributes:

```razor
<BarkButton class="my-custom-class" id="submit-btn" data-testid="submit">
    Submit
</BarkButton>
```

### Custom CSS Classes

All components use the BEM naming convention for CSS classes. You can override styles:

```css
/* Override button styles */
.bark-button {
    border-radius: 12px;
}

/* Override specific variant */
.bark-button--solid.bark-button--primary {
    background-color: #custom-color;
}
```

### Scoped CSS

Each component has its own scoped CSS file that can be customized by creating your own stylesheet with higher specificity.

---

## Best Practices

1. **Consistent Sizing**: Use the same size prop across related components for visual harmony.

2. **Color Schemes**: Stick to semantic color schemes (success for positive actions, danger for destructive actions).

3. **Accessibility**: Always provide labels for inputs and meaningful button text.

4. **Error Handling**: Use the HasError prop and HelperText for form validation feedback.

5. **Loading States**: Use BarkSpinner with BarkButton disabled state to show loading.

Example:
```razor
<BarkButton Disabled="@isLoading">
    @if (isLoading)
    {
        <BarkSpinner Size="sm" />
        <span style="margin-left: 0.5rem;">Loading...</span>
    }
    else
    {
        <span>Submit</span>
    }
</BarkButton>
```

---

## Browser Support

Bark UI components work in all modern browsers:
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Opera (latest)

---

## Accessibility

All components follow accessibility best practices:
- Semantic HTML elements
- ARIA attributes where appropriate
- Keyboard navigation support
- Screen reader friendly
- Focus management
