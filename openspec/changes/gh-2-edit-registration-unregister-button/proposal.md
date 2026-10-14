## Why

GitHub issue #2 asks for an "Odhlásit" button in the form for editing an event registration. The edit dialog now offers only "Zrušit" and "Upravit". A member who opens it to change their registration and decides to drop out has to close it and look for the unregister action elsewhere (event detail page or events list).

## What Changes

- The edit registration dialog shows an "Odhlásit" button in its footer, separated from "Zrušit" and "Upravit".
- The button is shown only when the registration resource offers the `unregisterFromEvent` affordance. That is the member's own registration while registrations are open, so a coordinator editing someone else's registration does not see it.
- Clicking the button unregisters the member immediately, with no confirmation step. The dialog then closes and the registrations list refreshes.
- No backend change: `unregisterFromEvent` is already part of the registration resource.

## Capabilities

### New Capabilities

<!-- None. -->

### Modified Capabilities

- `event-registrations`: `Edit Own Registration` gains scenarios for the unregister button in the edit dialog.

## Impact

**Affected specs:** `openspec/specs/event-registrations/spec.md` (`Edit Own Registration`).

**Affected code (frontend only):** `EventRegistrationDialog.tsx`, `useRegistrationDialogData.ts` and their tests.

**APIs:** none. The existing `unregisterFromEvent` (DELETE) template is used.
