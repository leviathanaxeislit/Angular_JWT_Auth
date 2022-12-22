# Angular Responsive Login and Register Module with JWT Auth

## How to run
First run `npm i` and then `ng serve`, then you can open localhost:4200 in your Browser

### 
Jwt:  
The @auth0/angular-jwt is added and with the login request the jwt is stored in the local storage.
The package adds then the jwt to every request to the backend automatically via an interceptoer, so the fe/the user is 
always authenticated against the backend.

Angular Guard:  
Protects the '/protected' route and checks if there is a jwt provided in the localstorage that is not expired.
If it's ok, then the user can access the route, otherwise the access is denied and the user gets redirected to Login

## Commands/Cli Commands that were used to generate this project 
With the Angular CLI we can generate Angular Scaffolds with just one specific command. 
e.g. generate a component, a module, or a service

Let the Angular CLI generate the angular starter for you  
```bash
ng new login-and-register-example
```  

add angular Material to your Angular app  
```bash
ng add @angular/material
```
  
Generate the modules Public, Private and Shared  
```bash
ng g module public  
ng g module protected  
```
Generate the components  
```bash
ng g c public/login  
ng g c public/register  
ng g c protected/dashboard 
```

Generate the "fake" Service  
```bash
ng g s public/auth 
```
  
Add an angular jwt package, for handling the jwt, the login etc.  
`npm i @auth0/angular-jwt`  
  
Add the Auth guard, to make sure only LoggedIn Users can access the Protected Module  
`ng g g Auth`  
then implement the CanActivate interface

### Sample Screenshots
Login View:
![Login View]( "Login View")

Login View with errors displayed:
![Login View with errors]( "Login View with an errors displayed")

Jwt Protected Dashboard after successfull login (only for Guard and Example purposes):
![Dashboard after login]( "Dashboard after login")

Register Form with passwords not matching error displayed:
![Register Form with Passwords not matching error displayed]("Register Form with Passwords not matching error displayed")