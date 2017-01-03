## Overview

Create an Angular 2 website written in Typescript that lets users create a new Mimo account or lets user login with their existing Mimo account.

- You won't be judged on the visual design at all, the only metric is your code.
- Part of this coding challenge is to read the documentation for the APIs provided to you.
- Use Git to track your changes and upload your Git repo either on [GitHub](https://github.com) or [Bitbucket](https://bitbucket.com) to share it with us.

All of the authentication is done via [Auth0](https://auth0.com/)

- Auth0 Domain: `mimo-test.auth0.com`
- Auth0 Client ID: `PAn11swGbMAVXVDbSCpnITx5Utsxz1co`
- Auth0 Connection Name: `Username-Password-Authentication`

The website should have three pages: One for login (/login), one for signup (/signup) and one to display information about the logged in user (/account).

## Login (/login)

	- The page should contain two fields: One for the email address and one for the password.
	- If the email doesn't exist upon login, display an error message stating that the account doesn't exist
	- Link to the signup page, so users that don't have an account yet can signup first

Relevant Auth0 API: https://auth0.com/docs/api/authentication#resource-owner-password

## Signup (/signup)

	- The page should contain two fields: One for the email address and one for the password.
	- If the email exist upon signup, display an error message stating that the account already exists

Relevant Auth0 API: https://auth0.com/docs/api/authentication#signup
Use `openid profile email` for the `scope` parameter

## Account (/account)

	- The page should display the email address of the user. Get this info from the JWT that you receive
	- If you're brave enough, also display the Gravatar picture associated with the email address
	- If the user user navigates to the account page directly and they aren't logged in, redirect them to the login page. Implement this in a way so it can be easily extended to other pages.
	- If the JWT expires, do the same as the above point.
