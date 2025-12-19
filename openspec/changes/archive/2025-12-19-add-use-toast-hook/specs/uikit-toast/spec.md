## ADDED Requirements

### Requirement: useToast Hook
The UI Kit SHALL provide a `useToast` hook that wraps Sonner's toast functionality and returns typed methods for displaying toast notifications.

#### Scenario: Basic toast display
- **WHEN** a component calls `const { toast } = useToast()` and invokes `toast("Message")`
- **THEN** a default toast notification is displayed with the provided message

#### Scenario: Success toast variant
- **WHEN** a component calls `const { success } = useToast()` and invokes `success("Operation completed")`
- **THEN** a success-styled toast notification is displayed with a success icon

#### Scenario: Error toast variant
- **WHEN** a component calls `const { error } = useToast()` and invokes `error("Something went wrong")`
- **THEN** an error-styled toast notification is displayed with an error icon

#### Scenario: Warning toast variant
- **WHEN** a component calls `const { warning } = useToast()` and invokes `warning("Please review")`
- **THEN** a warning-styled toast notification is displayed with a warning icon

#### Scenario: Info toast variant
- **WHEN** a component calls `const { info } = useToast()` and invokes `info("FYI")`
- **THEN** an info-styled toast notification is displayed with an info icon

#### Scenario: Promise toast handling
- **WHEN** a component calls `const { promise } = useToast()` and invokes `promise(asyncFn, { loading, success, error })`
- **THEN** a loading toast is displayed during the promise execution
- **AND** on resolution, the success message is shown
- **AND** on rejection, the error message is shown

#### Scenario: Toast dismissal
- **WHEN** a component calls `const { dismiss } = useToast()` and invokes `dismiss(toastId)`
- **THEN** the toast with the specified ID is removed from the screen

#### Scenario: Toast with action button
- **WHEN** a component invokes a toast method with an `action` option containing `{ label, onClick }`
- **THEN** the toast displays an action button that triggers the callback when clicked

### Requirement: useToast Hook Options
The `useToast` hook SHALL accept optional default configuration that applies to all toasts created by that hook instance.

#### Scenario: Custom default duration
- **WHEN** a component calls `useToast({ defaultDuration: 5000 })`
- **AND** invokes any toast method without explicit duration
- **THEN** the toast auto-dismisses after 5000ms

### Requirement: Hook-Only Toast API
The UI Kit SHALL NOT export the direct `toast` function from Sonner; all toast functionality MUST be accessed via the `useToast` hook.

#### Scenario: No direct toast export
- **WHEN** a consumer attempts to import `{ toast }` from `@hai3/uikit`
- **THEN** the import fails because `toast` is not exported
- **AND** the consumer must use `useToast` hook instead
