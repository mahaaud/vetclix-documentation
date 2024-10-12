# Authentication

On VetClix, it uses the combination of Laravel Authentication, Laravel Fortify, and Laravel Sanctum. For the Laravel Authentication, it is intended to use as the authentication base for the web application with Laravel Fortify to strengthen the security by adding two factors authentication mechanism to the authentication system, and the Sanctum is mainly used as the authentication of the API. VetClix split into 3 types of authentication systems as it plans to extend the client's application to mobile application, as well as the desktop application (e.g. Electron) in the future, so these 3 authentication systems can cover all of these platforms.

## Concepts

On web application, the Laravel Authentication is used to authenticate the user's credential. Once they are logging in, the Laravel Fortify will take the responsibility to check the credential, if it is correct, the system will set the authenticated session, and generate the Laravel Sanctum token, which contains the access permissions, and store it in the separated session.

After the user is authenticated, the user can communicate with the API by attaching token with the Authentication Bearer header to the API endpoints, and they should be able to access the resource from it.