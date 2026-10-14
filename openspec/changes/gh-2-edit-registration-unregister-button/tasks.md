# Tasks

## 1. Odhlásit button in the edit registration dialog

- [ ] 1.1 Return the `unregisterFromEvent` template from `useRegistrationDialogData` test-first; verify hook tests for own registration (present) and coordinator view (absent)
- [ ] 1.2 Add the "Odhlásit" label and the footer button (`warning-ghost`, `UserMinus`, left-aligned) to `EventRegistrationDialog`, shown only with the template; DELETE via `authorizedFetch`, then `onRegistered` and close; error alert on failure; test-first; verify `EventRegistrationDialog.test.tsx` (shown, hidden, click unregisters and closes, failure keeps dialog open)
- [ ] 1.3 Run lint and the frontend tests, run `refresh-backend-server-resources`, and check the dialog in the browser at http://localhost:3000
