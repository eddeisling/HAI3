# uikit-base Spec Delta: Sonner Toast Notification Component

## ADDED Requirements

### Requirement: Sonner Toaster Component

The UI Kit SHALL provide a Toaster component that renders toast notifications with theme-aware styling and custom icons.

#### Scenario: Toaster component is available
- **WHEN** importing Toaster from `@hai3/uikit`
- **THEN** the Toaster component is available for use
- **AND** the toast function is available for programmatic toast triggering

#### Scenario: Theme integration
- **WHEN** Toaster component renders
- **THEN** it uses HAI3 theme CSS custom properties for styling
- **AND** background uses `--popover` token
- **AND** text uses `--popover-foreground` token
- **AND** borders use `--border` token
- **AND** border radius uses `--radius` token

#### Scenario: Custom icons for toast types
- **WHEN** Toaster renders different toast types
- **THEN** success toasts display CircleCheckIcon
- **AND** info toasts display InfoIcon
- **AND** warning toasts display TriangleAlertIcon
- **AND** error toasts display OctagonXIcon
- **AND** loading toasts display Loader2Icon with spin animation

### Requirement: Toast Function API

The UI Kit SHALL provide a toast function with support for multiple notification types and promise-based loading states.

#### Scenario: Default toast
- **WHEN** calling `toast(message)`
- **THEN** a default toast notification is displayed
- **AND** the toast displays without a type-specific icon

#### Scenario: Success toast
- **WHEN** calling `toast.success(message)`
- **THEN** a success toast is displayed with CircleCheckIcon
- **AND** the toast uses success styling

#### Scenario: Info toast
- **WHEN** calling `toast.info(message)`
- **THEN** an info toast is displayed with InfoIcon
- **AND** the toast uses info styling

#### Scenario: Warning toast
- **WHEN** calling `toast.warning(message)`
- **THEN** a warning toast is displayed with TriangleAlertIcon
- **AND** the toast uses warning styling

#### Scenario: Error toast
- **WHEN** calling `toast.error(message)`
- **THEN** an error toast is displayed with OctagonXIcon
- **AND** the toast uses error styling

#### Scenario: Promise-based toast
- **WHEN** calling `toast.promise(promiseFunction, config)`
- **THEN** a loading toast is displayed immediately with Loader2Icon
- **AND** when promise resolves, toast updates to success state
- **AND** when promise rejects, toast updates to error state
- **AND** the toast shows appropriate loading, success, and error messages

### Requirement: Toaster Integration

The UI Kit SHALL integrate Toaster component at the application root level for global toast notifications.

#### Scenario: Toaster placement in App.tsx
- **WHEN** the application renders
- **THEN** Toaster component is mounted at root level
- **AND** Toaster is positioned to not interfere with layout
- **AND** toasts can be triggered from any component via toast function

### Requirement: Sonner Demo Examples

The UI kit demo SHALL provide examples for the Sonner component in the Feedback & Status category demonstrating:
- Default toast notification
- Success notification
- Info notification
- Warning notification
- Error notification
- Promise-based loading → success/error flow

#### Scenario: Sonner section in FeedbackElements
- **WHEN** viewing the Feedback & Status category
- **THEN** a Sonner section is displayed with heading and examples
- **AND** the section includes `data-element-id="element-sonner"` for navigation

#### Scenario: Sonner examples use translations
- **WHEN** Sonner examples are rendered
- **THEN** all button labels use the `tk()` translation helper
- **AND** all translated text is wrapped with TextLoader component
- **AND** no translation keys are displayed (values are shown)

#### Scenario: Multiple toast type examples
- **WHEN** viewing the Sonner section
- **THEN** buttons are displayed for triggering each toast type
- **AND** buttons are labeled: Default, Success, Info, Warning, Error, Promise
- **AND** clicking each button displays the corresponding toast notification
- **AND** Promise button simulates a 2-second async operation

#### Scenario: Interactive toast triggering
- **WHEN** clicking a toast example button
- **THEN** a toast notification appears on screen
- **AND** the toast automatically dismisses after the default duration
- **AND** user can manually dismiss the toast by clicking close button
- **AND** multiple toasts can be stacked

### Requirement: Sonner in Category System

The UI Kit SHALL include Sonner as an implemented element in the Feedback & Status category.

#### Scenario: Sonner in IMPLEMENTED_ELEMENTS
- **WHEN** checking `uikitCategories.ts`
- **THEN** 'Sonner' is included in the IMPLEMENTED_ELEMENTS array
- **AND** Sonner appears in the Feedback & Status category navigation menu

#### Scenario: Sonner element ordering
- **WHEN** viewing the Feedback & Status category
- **THEN** Sonner is positioned appropriately among other feedback elements
- **AND** the navigation menu reflects the correct order

### Requirement: Sonner Translations

The UI Kit SHALL provide Sonner translations across all supported languages (36 languages).

#### Scenario: Sonner translation keys
- **WHEN** Sonner component is used in the demo
- **THEN** translation keys exist for all Sonner elements
- **AND** keys include: sonner_heading, sonner_default_label, sonner_default_message, sonner_success_label, sonner_success_message, sonner_info_label, sonner_info_message, sonner_warning_label, sonner_warning_message, sonner_error_label, sonner_error_message, sonner_promise_label, sonner_promise_loading, sonner_promise_success, sonner_promise_error

#### Scenario: Translation files completeness
- **WHEN** checking translation files in `src/screensets/demo/screens/uikit/i18n/`
- **THEN** all 36 language files include Sonner translation keys
- **AND** translations are contextually appropriate for each language
- **AND** toast messages are concise and actionable

### Requirement: Sonner Accessibility

The Toaster component SHALL provide accessible toast notifications that work with screen readers and keyboard navigation.

#### Scenario: ARIA live region
- **WHEN** a toast notification appears
- **THEN** it is announced to screen readers via ARIA live region
- **AND** the announcement is polite (not assertive) for non-critical toasts

#### Scenario: Keyboard dismissal
- **WHEN** a toast is visible and user presses Escape key
- **THEN** the toast is dismissed
- **AND** focus returns to the triggering element if applicable

#### Scenario: Focus management
- **WHEN** multiple toasts are stacked
- **THEN** keyboard users can navigate between toasts
- **AND** each toast's close button is keyboard accessible
