# Okta Spring Security Resource Server Example

This sample application authenticates requests against your Spring application, using access tokens.

## Prerequisites

Before running this sample, you will need the following:

* An Okta Developer Account, you can sign up for one at https://developer.okta.com/signup/.
* An Okta Application, configured for Singe-Page App (SPA) mode. This is done from the Okta Developer Console and you can find instructions [here][OIDC SPA Setup Instructions]. 
A typical resource-server requires a frontend and a backend application, so you will need to start each process:

## Running This Example

**backend:**
```bash
cd backend
mvnw -Dokta.oauth2.issuer=https://{yourOktaDomain}/oauth2/default
```
> **NOTE:** The above command starts the resource server on port 8000. You can browse to `http://localhost:8000` to ensure it has started. If you get the message "401 Unauthorized", it indicates that the resource server is up. You will need to pass an access token to access the resource, which will be done by the front-end below.

**frontend:**

- **Client Id** - The client ID of the SPA application that you created earlier. This can be found on the "General" tab of an application, or the list of applications. The resource server will validate that tokens have been minted for this application.
- **Base URL** - This is the URL of the developer org that you created. For example, `https://dev-1234.oktapreview.com`.

Now start the front-end.


Browse to: `http://localhost:8080/` to login!


[Authorization Code Flow + PKCE]: https://developer.okta.com/docs/guides/implement-auth-code-pkce/overview/
[Okta Angular Sample Apps]: https://github.com/okta/samples-js-angular
[Okta Vue Sample Apps]: https://github.com/okta/samples-js-vue
[Okta React Sample Apps]: https://github.com/okta/samples-js-react
[OIDC SPA Setup Instructions]: https://developer.okta.com/authentication-guide/implementing-authentication/implicit#1-setting-up-your-application
