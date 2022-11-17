# privatepackagepublishtogit


—> **Steps:  publish a private package to git packages**

1. Generate a token in github

       My profile → settings → developer settings → Personnel access token → generate token → select repo, write, read package

      once token is created copy the token“[GENERATED_TOKEN](https://npm.pkg.github.com/:_authToken=GENERATED_TOKEN)”

1. Create a repo in git **"url":"[https://github.com/farooqmir/privatepackagepublishtogit](https://github.com/farooqmir/privatepackagepublishtogit)"**
2. update the system global .npmrc file with the below bolded, underlined line

```
[//registry.npmjs.org/:_authToken=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](https://registry.npmjs.org/:_authToken=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)[//npm](https://npm.pkg.github.com/:_authToken=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)

[**pkg.github.com/:_authToken=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**](https://npm.pkg.github.com/:_authToken=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)
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
