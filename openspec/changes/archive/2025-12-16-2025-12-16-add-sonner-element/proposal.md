# Add Sonner Toast Notification UI Kit Element

## Why

The UI Kit currently lacks a modern toast notification system for displaying ephemeral feedback messages. Sonner is a foundational component for:
- Success/error notifications after user actions
- Loading states for asynchronous operations
- Warning and informational alerts
- Promise-based notifications with loading → success/error transitions
- Non-blocking user feedback without interrupting workflow

Sonner provides a superior toast experience with:
- Beautiful animations and positioning
- Promise-based API for async operations
- Multiple toast types (default, success, info, warning, error, loading)
- Theme-aware styling that respects HAI3 color tokens
- Accessible keyboard navigation and screen reader support

## What Changes

### New Components
- `Toaster` - Container component that renders toast notifications
  - Integrates with HAI3 theme system via CSS custom properties
  - Supports custom icons for each toast type (success, info, warning, error, loading)
  - Uses `lucide-react` icons matching HAI3's icon system
  - Positioned via Sonner's built-in positioning system

### Demo Examples
Multiple toast type demonstrations in the Feedback & Status category:
- **Default toast** - Basic notification without icon
- **Success toast** - Positive feedback with CircleCheckIcon
- **Info toast** - Informational messages with InfoIcon
- **Warning toast** - Cautionary messages with TriangleAlertIcon
- **Error toast** - Error feedback with OctagonXIcon
- **Promise toast** - Loading → Success/Error transition with Loader2Icon

### Styling
- Theme integration via CSS custom properties:
  - `--normal-bg`: `var(--popover)` for toast background
  - `--normal-text`: `var(--popover-foreground)` for text color
  - `--normal-border`: `var(--border)` for borders
  - `--border-radius`: `var(--radius)` for rounded corners
- Custom icons sized with `size-4` Tailwind class
- Loading icon with `animate-spin` for visual feedback

### Dependencies
- `sonner` package (toast notification library)
- `lucide-react` icons (already in project)
- No dependency on `next-themes` - HAI3 has its own theme system

### Integration Points
- Add to Feedback & Status category in `uikitCategories.ts`
- Export from `@hai3/uikit` package
- Integrate toast function for programmatic triggering
- FeedbackElements component for demonstrations

### Accessibility
- Screen reader announcements via ARIA live regions
- Keyboard dismissal (Escape key)
- Focus management for interactive toasts
- Semantic role="status" for notifications

## Affected Specs
- `uikit-base` - New Sonner component requirements
