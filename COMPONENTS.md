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

## BarkAccordion

An expandable accordion component for organizing content sections.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Accordion items to display |
| Variant | string | "default" | Accordion style: "default", "outline", or "ghost" |
| Multiple | bool | false | Allow multiple items to be expanded simultaneously |

### Usage

```razor
<BarkAccordion>
    <BarkAccordionItem Title="Section 1">
        Content for section 1
    </BarkAccordionItem>
    <BarkAccordionItem Title="Section 2">
        Content for section 2
    </BarkAccordionItem>
</BarkAccordion>
```

---

## BarkAccordionItem

Individual accordion section within BarkAccordion.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Content to display when expanded |
| Title | string? | null | Title text for the accordion item |
| IsExpanded | bool | false | Whether the item is expanded |
| IsExpandedChanged | EventCallback<bool> | - | Event callback when expansion state changes |

---

## BarkCollapsible

Toggle content visibility with a customizable trigger.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Content to show/hide |
| TriggerContent | RenderFragment? | null | Content for the trigger button |
| IsOpen | bool | false | Whether the content is visible |
| IsOpenChanged | EventCallback<bool> | - | Event callback when open state changes |

### Usage

```razor
<BarkCollapsible @bind-IsOpen="isOpen">
    <TriggerContent>
        <span>Click to toggle</span>
    </TriggerContent>
    <ChildContent>
        <p>Collapsible content here</p>
    </ChildContent>
</BarkCollapsible>
```

---

## BarkAvatar

Display user profile images or initials.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Src | string? | null | Image source URL |
| Alt | string? | null | Alt text for image |
| Name | string? | null | Name to generate initials from |
| Fallback | string? | null | Custom fallback text (overrides auto-generated initials) |
| Size | string | "md" | Avatar size: "sm", "md", "lg", or "xl" |
| Shape | string | "circle" | Avatar shape: "circle" or "square" |

### Usage

```razor
<BarkAvatar Name="John Doe" Size="md" Shape="circle" />
<BarkAvatar Src="https://example.com/avatar.jpg" Alt="User avatar" />
```

---

## BarkCarousel

Slideshow component for cycling through content.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Carousel items to display |
| CurrentIndex | int | 0 | Currently active slide index |
| CurrentIndexChanged | EventCallback<int> | - | Event callback when slide changes |
| ItemCount | int | 0 | Total number of items |
| Loop | bool | true | Whether to loop back to start |
| ShowControls | bool | true | Show navigation buttons |
| ShowIndicators | bool | true | Show indicator dots |

### Usage

```razor
<BarkCarousel @bind-CurrentIndex="index" ItemCount="3">
    <BarkCarouselItem>
        <div>Slide 1</div>
    </BarkCarouselItem>
    <BarkCarouselItem>
        <div>Slide 2</div>
    </BarkCarouselItem>
    <BarkCarouselItem>
        <div>Slide 3</div>
    </BarkCarouselItem>
</BarkCarousel>
```

---

## BarkIcon

Flexible icon wrapper component.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Icon content (emoji, SVG, etc.) |
| Size | string | "md" | Icon size: "xs", "sm", "md", "lg", or "xl" |
| AriaLabel | string? | null | Accessible label for screen readers |

### Usage

```razor
<BarkIcon Size="lg" AriaLabel="Home icon">🏠</BarkIcon>
```

---

## BarkTable

Data table with styling options.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Table content (thead, tbody, tfoot) |
| Variant | string | "default" | Table style: "default" or "simple" |
| Striped | bool | false | Alternate row colors |
| Hoverable | bool | true | Highlight row on hover |

### Usage

```razor
<BarkTable Striped="true" Hoverable="true">
    <thead>
        <tr>
            <th>Name</th>
            <th>Email</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>John Doe</td>
            <td>john@example.com</td>
        </tr>
    </tbody>
</BarkTable>
```

---

## BarkProgress

Visual progress indicator.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Value | int | 0 | Progress value (0-100) |
| Size | string | "md" | Progress bar size: "sm", "md", or "lg" |
| ColorScheme | string | "primary" | Color scheme: "primary", "secondary", "success", or "danger" |
| ShowLabel | bool | false | Display percentage label |
| Striped | bool | false | Striped pattern |
| Animated | bool | false | Animate stripes |

### Usage

```razor
<BarkProgress Value="75" ShowLabel="true" ColorScheme="success" />
<BarkProgress Value="50" Striped="true" Animated="true" />
```

---

## BarkSkeleton

Loading placeholder for content.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Optional custom content |
| Variant | string | "text" | Skeleton type: "text", "circle", or "rectangle" |
| Width | string | "100%" | Width of the skeleton |
| Height | string | "1rem" | Height of the skeleton |
| Animated | bool | true | Pulse animation |

### Usage

```razor
<BarkSkeleton Variant="text" Width="100%" />
<BarkSkeleton Variant="circle" />
<BarkSkeleton Variant="rectangle" Height="8rem" />
```

---

## BarkToast

Notification messages with dismissible option.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Toast message content |
| Title | string? | null | Toast title |
| Variant | string | "default" | Toast type: "default", "success", "warning", or "error" |
| Dismissible | bool | true | Show close button |
| OnClose | EventCallback | - | Event callback when toast is closed |

### Usage

```razor
<BarkToast Variant="success" Title="Success!" OnClose="HandleClose">
    Your changes have been saved.
</BarkToast>
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
