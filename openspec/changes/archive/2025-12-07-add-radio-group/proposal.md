# Change: Add Radio Group Base UI Kit Element

## Why
Radio Group is a common form element for single-selection from multiple options. It is listed in the UI Kit category system but not yet implemented.

## What Changes
- Add `RadioGroup` and `RadioGroupItem` base components built on `@radix-ui/react-radio-group`
- Export components from `@hai3/uikit` package
- Add demo examples in Forms & Inputs category with translations
- Mark Radio Group as implemented in category system

## Impact
- Affected specs: `uikit-base`
- Affected code:
  - `packages/uikit/src/base/radio-group.tsx` (new)
  - `packages/uikit/src/index.ts`
  - `src/screensets/demo/components/FormElements.tsx`
  - `src/screensets/demo/screens/uikit/uikitCategories.ts`
  - `src/screensets/demo/screens/uikit/i18n/*.json` (36 language files)
