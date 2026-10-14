## ADDED Requirements

### Requirement: Unregister From The Edit Registration Form

The form for editing an event registration SHALL let the member unregister from the event. The "Odhlásit" button SHALL be shown only when the registration offers the unregister action, and it SHALL unregister the member without asking for confirmation.

#### Scenario: Edit form offers Odhlásit for the member's own registration

- **GIVEN** a member is registered for an active event with an open registration window
- **WHEN** the member opens the edit form of their registration
- **THEN** the form footer shows an "Odhlásit" button, separated from "Zrušit" and "Upravit"

#### Scenario: Odhlásit in the edit form unregisters the member

- **GIVEN** the member has the edit form of their own registration open
- **WHEN** the member clicks "Odhlásit"
- **THEN** the member is unregistered from the event without a confirmation step
- **AND** the edit form closes
- **AND** the registrations list no longer shows the member's registration

#### Scenario: Edit form hides Odhlásit when the registration cannot be unregistered by the current user

- **GIVEN** a user with EVENTS:REGISTRATIONS edits the registration of another member
- **WHEN** the edit form opens
- **THEN** no "Odhlásit" button is shown
