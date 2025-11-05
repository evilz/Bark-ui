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

## BarkCheckbox

A checkbox input component with customizable sizes.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Label content for the checkbox |
| Checked | bool | false | Whether the checkbox is checked |
| CheckedChanged | EventCallback<bool> | - | Event callback when checked state changes |
| Disabled | bool | false | Whether the checkbox is disabled |
| Size | string | "md" | Checkbox size: "sm", "md", or "lg" |

### Usage

```razor
<BarkCheckbox @bind-Checked="isChecked">Accept terms and conditions</BarkCheckbox>
```

---

## BarkSwitch

A toggle switch component with customizable label positions.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text for the switch |
| Checked | bool | false | Whether the switch is on |
| CheckedChanged | EventCallback<bool> | - | Event callback when checked state changes |
| Disabled | bool | false | Whether the switch is disabled |
| Size | string | "md" | Switch size: "sm", "md", or "lg" |
| LabelPosition | string | "start" | Label position: "start" or "end" |

### Usage

```razor
<BarkSwitch @bind-Checked="isDarkMode" Label="Dark Mode" />
```

---

## BarkTextarea

A multi-line text input component with label and validation support.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Id | string? | auto-generated | HTML id attribute |
| Label | string? | null | Label text displayed above the textarea |
| Placeholder | string? | null | Placeholder text |
| Value | string? | null | Current value |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Rows | int | 4 | Number of visible text rows |
| Size | string | "md" | Textarea size: "sm", "md", or "lg" |
| Disabled | bool | false | Whether the textarea is disabled |
| HasError | bool | false | Whether to display error state |
| HelperText | string? | null | Helper or error text displayed below textarea |

### Usage

```razor
<BarkTextarea Label="Comments" Placeholder="Enter your comments..." @bind-Value="comments" />
```

---

## BarkSelect

A dropdown select component with custom styling.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Id | string? | auto-generated | HTML id attribute |
| Label | string? | null | Label text displayed above the select |
| Placeholder | string? | null | Placeholder option text |
| Value | string? | null | Currently selected value |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Size | string | "md" | Select size: "sm", "md", or "lg" |
| Disabled | bool | false | Whether the select is disabled |
| HasError | bool | false | Whether to display error state |
| HelperText | string? | null | Helper or error text displayed below select |
| ChildContent | RenderFragment? | null | Option elements |

### Usage

```razor
<BarkSelect Label="Country" @bind-Value="selectedCountry">
    <option value="us">United States</option>
    <option value="uk">United Kingdom</option>
</BarkSelect>
```

---

## BarkSlider

A range slider component with optional value display.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text displayed above the slider |
| Value | int | 0 | Current value |
| ValueChanged | EventCallback<int> | - | Event callback when value changes |
| Min | int | 0 | Minimum value |
| Max | int | 100 | Maximum value |
| Step | int | 1 | Step increment |
| ShowValue | bool | false | Display current value next to slider |
| Disabled | bool | false | Whether the slider is disabled |
| Size | string | "md" | Slider size: "sm", "md", or "lg" |

### Usage

```razor
<BarkSlider Label="Volume" @bind-Value="volume" ShowValue="true" />
```

---

## BarkRadioGroup & BarkRadio

Radio button group components for single selection from multiple options.

### BarkRadioGroup Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text for the radio group |
| ChildContent | RenderFragment? | null | Radio button items |
| Value | string? | null | Currently selected value |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Size | string | "md" | Radio size: "sm", "md", or "lg" |
| Orientation | string | "vertical" | Layout: "vertical" or "horizontal" |

### BarkRadio Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Label content for the radio button |
| Value | string? | null | Value of this radio option |
| Name | string? | null | HTML name attribute |
| Disabled | bool | false | Whether the radio is disabled |
| Size | string | "md" | Radio size: "sm", "md", or "lg" |

### Usage

```razor
<CascadingValue Value="radioGroup">
    <BarkRadioGroup Label="Select size" @bind-Value="selectedSize">
        <BarkRadio Value="small">Small</BarkRadio>
        <BarkRadio Value="medium">Medium</BarkRadio>
        <BarkRadio Value="large">Large</BarkRadio>
    </BarkRadioGroup>
</CascadingValue>
```

---

## BarkNumberInput

A number input with increment and decrement buttons.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Id | string? | auto-generated | HTML id attribute |
| Label | string? | null | Label text displayed above the input |
| Value | int | 0 | Current value |
| ValueChanged | EventCallback<int> | - | Event callback when value changes |
| Min | int | int.MinValue | Minimum value |
| Max | int | int.MaxValue | Maximum value |
| Step | int | 1 | Step increment |
| Size | string | "md" | Input size: "sm", "md", or "lg" |
| Disabled | bool | false | Whether the input is disabled |
| HasError | bool | false | Whether to display error state |
| HelperText | string? | null | Helper or error text displayed below input |

### Usage

```razor
<BarkNumberInput Label="Quantity" @bind-Value="quantity" Min="1" Max="100" />
```

---

## BarkPinInput

A PIN or OTP input component with multiple digit fields.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text displayed above the pin input |
| Value | string | "" | Current pin value |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Length | int | 4 | Number of pin digits |
| Mask | bool | false | Whether to mask the input as password |
| Disabled | bool | false | Whether the input is disabled |
| Size | string | "md" | Input size: "sm", "md", or "lg" |

### Usage

```razor
<BarkPinInput Label="Enter PIN" @bind-Value="pin" Length="4" />
```

---

## BarkFileUpload

A file upload component with drag-and-drop support.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Id | string? | auto-generated | HTML id attribute |
| Label | string? | null | Label text displayed above the upload area |
| PlaceholderText | string? | null | Custom placeholder text |
| HelperText | string? | null | Helper text displayed below upload area |
| Multiple | bool | false | Allow multiple file uploads |
| Accept | string? | null | Accepted file types |
| Disabled | bool | false | Whether the upload is disabled |
| FilesChanged | EventCallback<string[]> | - | Event callback when files are selected |

### Usage

```razor
<BarkFileUpload Label="Upload documents" Multiple="true" Accept=".pdf,.doc,.docx" />
```

---

## BarkRatingGroup

A star rating component for user feedback.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text displayed above the rating |
| Value | int | 0 | Current rating value |
| ValueChanged | EventCallback<int> | - | Event callback when value changes |
| Max | int | 5 | Maximum rating value |
| Icon | string | "⭐" | Icon to use for rating (emoji or character) |
| Disabled | bool | false | Whether the rating is disabled |
| Size | string | "md" | Rating size: "sm", "md", or "lg" |

### Usage

```razor
<BarkRatingGroup Label="Rate this product" @bind-Value="rating" />
```

---

## BarkSegmentGroup & BarkSegment

Segmented control for switching between views or options.

### BarkSegmentGroup Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text for the segment group |
| ChildContent | RenderFragment? | null | Segment items |
| Value | string? | null | Currently selected value |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Size | string | "md" | Segment size: "sm", "md", or "lg" |

### BarkSegment Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Content for the segment |
| Value | string? | null | Value of this segment option |

### Usage

```razor
<CascadingValue Value="segmentGroup">
    <BarkSegmentGroup Label="View mode" @bind-Value="viewMode">
        <BarkSegment Value="list">List</BarkSegment>
        <BarkSegment Value="grid">Grid</BarkSegment>
    </BarkSegmentGroup>
</CascadingValue>
```

---

## BarkToggleGroup & BarkToggle

Toggle button group for selecting from multiple options.

### BarkToggleGroup Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text for the toggle group |
| ChildContent | RenderFragment? | null | Toggle items |
| Value | string? | null | Currently selected value |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Size | string | "md" | Toggle size: "sm", "md", or "lg" |
| Variant | string | "default" | Toggle style variant |

### BarkToggle Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Content for the toggle |
| Value | string? | null | Value of this toggle option |

### Usage

```razor
<CascadingValue Value="toggleGroup">
    <BarkToggleGroup Label="Text alignment" @bind-Value="alignment">
        <BarkToggle Value="left">Left</BarkToggle>
        <BarkToggle Value="center">Center</BarkToggle>
        <BarkToggle Value="right">Right</BarkToggle>
    </BarkToggleGroup>
</CascadingValue>
```

---

## BarkTagsInput

A tags input component for adding and removing tags.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text displayed above the input |
| Placeholder | string? | null | Placeholder text |
| Tags | List<string> | new() | List of current tags |
| TagsChanged | EventCallback<List<string>> | - | Event callback when tags change |
| Disabled | bool | false | Whether the input is disabled |
| HelperText | string? | null | Helper text displayed below input |
| Size | string | "md" | Input size: "sm", "md", or "lg" |

### Usage

```razor
<BarkTagsInput Label="Tags" @bind-Tags="tags" Placeholder="Type and press Enter" />
```

---

## BarkRadioCardGroup & BarkRadioCard

Card-based radio selection for rich option presentation.

### BarkRadioCardGroup Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text for the card group |
| ChildContent | RenderFragment? | null | Radio card items |
| Value | string? | null | Currently selected value |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Columns | int | 2 | Number of columns in grid layout |

### BarkRadioCard Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Content for the radio card |
| Value | string? | null | Value of this card option |

### Usage

```razor
<CascadingValue Value="radioCardGroup">
    <BarkRadioCardGroup Label="Select a plan" @bind-Value="plan" Columns="3">
        <BarkRadioCard Value="starter">
            <h3>Starter</h3>
            <p>Perfect for small projects</p>
        </BarkRadioCard>
    </BarkRadioCardGroup>
</CascadingValue>
```

---

## BarkField

A form field wrapper component with label, helper text, and error handling.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Id | string? | null | HTML id attribute |
| Label | string? | null | Label text for the field |
| ChildContent | RenderFragment? | null | Field content (input, select, etc.) |
| HelperText | string? | null | Helper text displayed below field |
| ErrorText | string? | null | Error text displayed when HasError is true |
| HasError | bool | false | Whether to display error state |

### Usage

```razor
<BarkField Label="Email" HelperText="We'll never share your email">
    <BarkInput Type="email" Placeholder="you@example.com" />
</BarkField>
```

---

## BarkFieldset

A fieldset component for grouping related form fields.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Legend | string? | null | Fieldset legend text |
| HelperText | string? | null | Helper text displayed below legend |
| ChildContent | RenderFragment? | null | Form fields content |
| Disabled | bool | false | Whether all fields in the fieldset are disabled |

### Usage

```razor
<BarkFieldset Legend="Personal Information" HelperText="Please provide your details">
    <BarkInput Label="First Name" />
    <BarkInput Label="Last Name" />
</BarkFieldset>
```

---

## BarkEditable

An inline editable text component.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Value | string? | null | Current text value |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Placeholder | string? | "Click to edit" | Placeholder text when empty |

### Usage

```razor
<BarkEditable @bind-Value="title" Placeholder="Enter title" />
```

---

## BarkColorPicker

A color picker component with hex input.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text displayed above the picker |
| Value | string | "#000000" | Current color value (hex format) |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Disabled | bool | false | Whether the picker is disabled |
| HelperText | string? | null | Helper text displayed below picker |

### Usage

```razor
<BarkColorPicker Label="Primary Color" @bind-Value="primaryColor" />
```

---

## BarkDatePicker

A date picker component using native date input.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Id | string? | auto-generated | HTML id attribute |
| Label | string? | null | Label text displayed above the picker |
| Value | DateTime? | null | Current date value |
| ValueChanged | EventCallback<DateTime?> | - | Event callback when value changes |
| Disabled | bool | false | Whether the picker is disabled |
| Size | string | "md" | Picker size: "sm", "md", or "lg" |
| HasError | bool | false | Whether to display error state |
| HelperText | string? | null | Helper or error text displayed below picker |

### Usage

```razor
<BarkDatePicker Label="Birth Date" @bind-Value="birthDate" />
```

---

## BarkCombobox

A searchable dropdown component with filtering.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Label | string? | null | Label text displayed above the combobox |
| Placeholder | string? | null | Placeholder text |
| Value | string? | null | Currently selected value |
| ValueChanged | EventCallback<string> | - | Event callback when value changes |
| Options | List<string> | new() | List of available options |
| Disabled | bool | false | Whether the combobox is disabled |
| HelperText | string? | null | Helper text displayed below combobox |

### Usage

```razor
<BarkCombobox Label="Search countries" @bind-Value="country" Options="countries" />
```

---

## BarkAbsoluteCenter

Center content absolutely within a container.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Content to center |
| Axis | string | "both" | Center axis: "both", "horizontal", or "vertical" |

### Usage

```razor
<div style="position: relative; height: 200px;">
    <BarkAbsoluteCenter Axis="both">
        <p>Centered content</p>
    </BarkAbsoluteCenter>
</div>
```

---

## BarkGroup

Layout component for grouping and arranging elements.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Elements to group |
| Orientation | string | "horizontal" | Layout direction: "horizontal" or "vertical" |
| Gap | string | "md" | Gap between items: "sm", "md", or "lg" |
| Align | string | "start" | Alignment: "start", "center", or "end" |
| Wrap | bool | false | Whether to wrap items |

### Usage

```razor
<BarkGroup Orientation="horizontal" Gap="md">
    <BarkButton>Button 1</BarkButton>
    <BarkButton>Button 2</BarkButton>
    <BarkButton>Button 3</BarkButton>
</BarkGroup>
```

---

## BarkScrollArea

Scrollable container with custom scrollbar styling.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Scrollable content |
| MaxHeight | string | "400px" | Maximum height of scroll area |
| ScrollDirection | string | "vertical" | Scroll direction: "vertical", "horizontal", or "both" |

### Usage

```razor
<BarkScrollArea MaxHeight="200px" ScrollDirection="vertical">
    <!-- Long content here -->
</BarkScrollArea>
```

---

## BarkSplitter

Split pane component for resizable layouts.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| FirstPane | RenderFragment? | null | Content for first pane |
| SecondPane | RenderFragment? | null | Content for second pane |
| Orientation | string | "horizontal" | Split direction: "horizontal" or "vertical" |
| DefaultSize | int | 50 | Default size percentage of first pane |

### Usage

```razor
<BarkSplitter Orientation="horizontal" DefaultSize="50">
    <FirstPane>
        <div>Left content</div>
    </FirstPane>
    <SecondPane>
        <div>Right content</div>
    </SecondPane>
</BarkSplitter>
```

---

## BarkLink

Styled hyperlink component.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Link text |
| Href | string? | null | Link URL |
| Variant | string | "default" | Link style: "default" or "muted" |
| Size | string | "md" | Link size: "sm", "md", or "lg" |
| Target | string? | null | HTML target attribute |
| Underline | bool | true | Whether to underline the link |

### Usage

```razor
<BarkLink Href="https://example.com" Target="_blank">Visit Example</BarkLink>
```

---

## BarkPagination

Pagination controls for navigating pages.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| CurrentPage | int | 1 | Currently active page |
| CurrentPageChanged | EventCallback<int> | - | Event callback when page changes |
| TotalPages | int | 1 | Total number of pages |
| MaxVisiblePages | int | 5 | Maximum visible page buttons |
| Size | string | "md" | Pagination size: "sm", "md", or "lg" |

### Usage

```razor
<BarkPagination @bind-CurrentPage="currentPage" TotalPages="10" />
```

---

## BarkTabs

Tab navigation component for switching between content views.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Tab items |
| Variant | string | "default" | Tab style: "default" or "enclosed" |
| Size | string | "md" | Tab size: "sm", "md", or "lg" |
| ActiveTabId | string? | null | ID of active tab |
| ActiveTabIdChanged | EventCallback<string> | - | Event callback when tab changes |

### Usage

```razor
<CascadingValue Value="tabs">
    <BarkTabs @bind-ActiveTabId="activeTab">
        <BarkTab Id="tab1" Title="First Tab">
            <p>First tab content</p>
        </BarkTab>
        <BarkTab Id="tab2" Title="Second Tab">
            <p>Second tab content</p>
        </BarkTab>
    </BarkTabs>
</CascadingValue>
```

---

## BarkTab

Individual tab item for BarkTabs component.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Id | string? | null | Unique identifier for the tab |
| Title | string? | null | Tab label text |
| ChildContent | RenderFragment? | null | Tab content |

---

## BarkDialog

Modal dialog component.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Dialog content |
| FooterContent | RenderFragment? | null | Optional footer content |
| Title | string? | null | Dialog title |
| IsOpen | bool | false | Whether dialog is visible |
| IsOpenChanged | EventCallback<bool> | - | Event callback when state changes |
| Size | string | "md" | Dialog size: "sm", "md", "lg", or "xl" |
| Dismissible | bool | true | Show close button |
| CloseOnOverlayClick | bool | true | Close when clicking outside |

### Usage

```razor
<BarkDialog @bind-IsOpen="dialogOpen" Title="Confirmation">
    <p>Are you sure you want to proceed?</p>
</BarkDialog>
```

---

## BarkDrawer

Slide-out drawer/sidebar component.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Drawer content |
| FooterContent | RenderFragment? | null | Optional footer content |
| Title | string? | null | Drawer title |
| IsOpen | bool | false | Whether drawer is visible |
| IsOpenChanged | EventCallback<bool> | - | Event callback when state changes |
| Placement | string | "right" | Drawer position: "right", "left", "top", or "bottom" |
| Size | string | "md" | Drawer size: "sm", "md", or "lg" |
| Dismissible | bool | true | Show close button |
| CloseOnOverlayClick | bool | true | Close when clicking outside |

### Usage

```razor
<BarkDrawer @bind-IsOpen="drawerOpen" Title="Menu" Placement="right">
    <ul>
        <li>Menu Item 1</li>
        <li>Menu Item 2</li>
    </ul>
</BarkDrawer>
```

---

## BarkHoverCard

Card that appears when hovering over trigger element.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| TriggerContent | RenderFragment? | null | Element that triggers the hover card |
| ChildContent | RenderFragment? | null | Hover card content |
| Placement | string | "top" | Card position: "top", "bottom", "left", or "right" |
| DelayMs | int | 200 | Delay before showing card (milliseconds) |

### Usage

```razor
<BarkHoverCard Placement="top">
    <TriggerContent>
        <span>Hover me</span>
    </TriggerContent>
    <ChildContent>
        <p>Additional information</p>
    </ChildContent>
</BarkHoverCard>
```

---

## BarkMenu

Dropdown menu component.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| TriggerContent | RenderFragment? | null | Element that triggers the menu |
| ChildContent | RenderFragment? | null | Menu items |
| Placement | string | "bottom-start" | Menu position |
| IsOpen | bool | false | Whether menu is visible |
| IsOpenChanged | EventCallback<bool> | - | Event callback when state changes |

### Usage

```razor
<CascadingValue Value="menu">
    <BarkMenu @bind-IsOpen="menuOpen">
        <TriggerContent>
            <BarkButton>Menu</BarkButton>
        </TriggerContent>
        <ChildContent>
            <BarkMenuItem OnClick="HandleAction">Item 1</BarkMenuItem>
            <BarkMenuItem OnClick="HandleAction">Item 2</BarkMenuItem>
        </ChildContent>
    </BarkMenu>
</CascadingValue>
```

---

## BarkMenuItem

Individual menu item for BarkMenu component.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| ChildContent | RenderFragment? | null | Menu item content |
| OnClick | EventCallback | - | Event callback when clicked |

---

## BarkPopover

Popover component with title and dismissible option.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| TriggerContent | RenderFragment? | null | Element that triggers the popover |
| ChildContent | RenderFragment? | null | Popover content |
| Title | string? | null | Popover title |
| Placement | string | "top" | Popover position: "top", "bottom", "left", or "right" |
| IsOpen | bool | false | Whether popover is visible |
| IsOpenChanged | EventCallback<bool> | - | Event callback when state changes |
| Dismissible | bool | true | Show close button |

### Usage

```razor
<BarkPopover Title="Help" Placement="top">
    <TriggerContent>
        <BarkButton>Help</BarkButton>
    </TriggerContent>
    <ChildContent>
        <p>Helpful information here</p>
    </ChildContent>
</BarkPopover>
```

---

## BarkTooltip

Simple tooltip component.

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| TriggerContent | RenderFragment? | null | Element that triggers the tooltip |
| Content | string? | null | Tooltip text |
| Placement | string | "top" | Tooltip position: "top", "bottom", "left", or "right" |
| DelayMs | int | 200 | Delay before showing tooltip (milliseconds) |

### Usage

```razor
<BarkTooltip Content="Click to save" Placement="top">
    <TriggerContent>
        <BarkButton>Save</BarkButton>
    </TriggerContent>
</BarkTooltip>
```

---
