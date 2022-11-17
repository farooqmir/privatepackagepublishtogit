# privatepackagepublishtogit


—> **Steps:  publish a private package to git packages**

1. Generate a token in github

       My profile → settings → developer settings → Personnel access token → generate token → select repo, write, read package

      once token is created copy the token“[GENERATED_TOKEN](https://npm.pkg.github.com/:_authToken=GENERATED_TOKEN)”

1. Create a repo in git **"url":"[https://github.com/farooqmir/privatepackagepublishtogit](https://github.com/farooqmir/privatepackagepublishtogit)"**
2. update the system global .npmrc file with the below bolded, underlined line

```
 

[**pkg.github.com/:_authToken=GENERATED_TOKEN**](https://npm.pkg.github.com/:_authToken=GENERATED_TOKEN)
```

1. Create .npmrc in package project and add the line

      @username:registry=https://npm.pkg.github.com/

1. create a file in package project to export 
    
    ```js
    index.js
    
    module.exports = () => {
        console.log("This is a private");
    }
    ```
    
2. Add following in the package.json

```json
"name": "@username/privatepackagepublishtogit",
"version": "1.0.0", // Version has to be changed everytime it is published
"repository": {
    "url":"https://github.com/username/privatepackagepublishtogit"
  }
```

6.

```
npm publish
```

1. Goto "url":"[https://github.com/username/privatepackagepublishtogit](https://github.com/username/privatepackagepublishtogit)" packages to see the published package





## Consume the package - example

## —> Consume a private package in a project

```js
npm install @farooqmir/privatepackagepublishtogit
```

```json
package.json

"dependencies": {
   "@farooqmir/privatepackagepublishtogit": "github:farooqmir/privatepackagepublishtogit",
}
```

```js
import greeting from "@farooqmir/privatepackagepublishtogit";
greeting();
```
