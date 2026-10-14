# Design

## Context

`EventRegistrationDialog` is self-contained: it renders the edit form through `HalFormDisplay` with a `customLayout` and has no `HalRouteContext`. `useRegistrationDialogData` returns only the `registerForEvent` or `editRegistration` template. The backend already adds the `unregisterFromEvent` (DELETE) template to the registration resource for the member's own registration while registrations are open.

## Decisions

- **Footer button inside the dialog, calling the DELETE template directly.** `useRegistrationDialogData` also returns the `unregisterFromEvent` template. The dialog renders the button only when it is present, so visibility follows the affordance and nothing is hardcoded about who may unregister. `HalFormButton` is not reused because it needs `HalRouteContext`, which the dialog deliberately does not depend on.
- **No confirmation.** Decided in issue #2.
- **Request.** DELETE to the template target (normalised like the edit target) through `authorizedFetch`. On success call `onRegistered` (refreshes the list) and close the dialog. On failure the dialog stays open and shows an error alert.
- **Presentation.** Left-aligned `Button` with variant `warning-ghost` and the `UserMinus` icon, label "Odhlásit" (new label, since the existing `unregisterFromEvent` label is "Odhlásit se z akce"). It is disabled while the request is running.

## Risks

None beyond accidental unregistration, which is accepted: the member can register again while registrations are open.
