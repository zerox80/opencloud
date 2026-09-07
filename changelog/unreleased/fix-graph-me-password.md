Bugfix: Require current password verification for own password changes

The Graph API now rejects password profile updates through `PATCH /me` before
applying any changes. Users must use `POST /me/changePassword`, which verifies
their current password. Administrator password resets through
`PATCH /users/{id}` remain supported.
