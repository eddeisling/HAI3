# Change: Add useToast Hook for Streamlined Toast Management

## Why
The current Sonner integration exports the raw `toast` function directly from the library, requiring consumers to import and use it imperatively. This creates tight coupling to Sonner's API, lacks centralized configuration, and makes it harder to enforce consistent toast patterns across the application.

## What Changes
- Add a `useToast` hook that wraps Sonner's toast functionality
- Provide typed helper methods for common toast variants (success, error, warning, info)
- Support configurable defaults at the hook level
- **BREAKING**: Remove the direct `toast` export in favor of the hook pattern

## Impact
- Affected specs: uikit-toast (new capability)
- Affected code:
  - `packages/uikit/src/hooks/useToast.ts` (new file)
  - `packages/uikit/src/base/sonner.tsx` (remove `toast` export)
  - `packages/uikit/src/index.ts` (replace `toast` with `useToast` export)
  - All consumers must migrate to the hook pattern
