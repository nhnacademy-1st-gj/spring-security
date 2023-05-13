Database Table Extension

Add the following columns to the "resident" table:
ID (id)
Password (password)
Email (email)
Password should not be stored as plain text.
It should be stored based on the digest of a one-way hash function.
Additional Features

Add login/logout functionality.
Authentication cookies should expire in 3 days.
Sessions should be stored in Redis.
Functionality Changes

Resident List
Instead of displaying the entire list of residents, only the residents belonging to the logged-in user and their household should be displayed.
OAuth2 Authentication Addition

Implementing OAuth2 authentication without using Spring Security.

Both ID/password authentication and OAuth2 authentication should be provided simultaneously.
Users should be able to choose between ID/password authentication and OAuth2 authentication when logging in.
Only support OAuth2 provider for Github.
OAuth2 Authentication Implementation

Implement OAuth2 authentication directly using the Github API, without using the Spring Security library.
OAuth2 Authentication Handling

If the authenticated result from Github includes an email value that exists in the "resident" table, the user should be logged in with that account.
If the authentication from Github is successful but the email value does not exist in the "resident" table, the user should be logged out.
