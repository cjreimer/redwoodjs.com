# Security

RedwoodJS wants you to be able build and deploy secure applications and takes the topic of security seriously.

* [RedwoodJS Security](https://github.com/redwoodjs/redwood/security) on GitHub
* [CodeQL code scanning](https://github.com/features/security)
* [Authentication](/docs/authentication)
* [Webhook signature verification](/docs/webhooks)
* [Ways to keep your serverless functions secure](/docs/serverless-functions#security-considerations)
* [Environment variables for secure keys and tokens](/docs/environment-variables)

> ⚠️ Security is Your Responsibility
> While Redwood offers the tools, practices, and information to keep your application secure, it remains your responsibility to put these in place. Proper password, token, and key protection using disciplined communication, password management systems, and environment management services like [Doppler](https://www.doppler.com) are strongly encouraged.

## Authentication

`@redwoodjs/auth` is a lightweight wrapper around popular SPA authentication libraries. We [currently support](https://redwoodjs.com/docs/authentication) the following authentication providers:

* Netlify Identity Widget
* Auth0
* Azure Active Directory
* Netlify GoTrue-JS
* Magic Links - Magic.js
* Firebase's GoogleAuthProvider
* Ethereum
* Supabase
* Nhost

For example implementations, please see [Authentitcation](https://github.com/redwoodjs/redwood/tree/main/packages/auth) and the use of the `getCurrentUser` and `requireAuth` helpers.

For a demonstration, check out the [Auth Playground](https://redwood-playground-auth.netlify.app).

## GraphQL

GraphQL is a fundamental part of Redwood. For details on how Redwood uses GraphQL and handles important security considerations, please see the [GraphQL Security](/docs/graphql#security) section and the [Secure Services](docs/services#secure-services) section.

## Functions

When deployed, a [serverless function](/docs/serverless-functions) is an open API endpoint. That means anyone can access it and perform any tasks it's asked to do. In many cases, this is completely appropriate and desired behavior. But there are often times you need to restrict access to a function, and Redwood can help you do that using a [variety of methods and approaches](/docs/serverless-functions#security-considerations).

For details on how to keep your functions secure, please see the [Serverless functions & Security considerations](/docs/serverless-functions#security-considerations) section in the RedwoodJS documentation.

## Webhooks

[Webhooks](/docs/webhooks) are a common way that third-party services notify your RedwoodJS application when an event of interest happens. 

They are a form of messaging or automation and allows web applications to communicate with each other and send real-time data from one application to another whenever a given event occurs.

Since each of these webhooks will call a function endpoint in your RedwoodJS api, you need to ensure that these run **only when they should**. That means you need to:

* Verify it comes from the place you expect
* Trust the party 
* Know the payload sent in the hook hasn't been tampered with
* Ensure that the hook isn't reprocessed or replayed 

For details on how to keep your incoming webhooks secure and how to sign your outgoing webhooks, please see [Webhooks](/docs/webhooks).