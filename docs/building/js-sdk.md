---
id: js-sdk
title: JavaScript SDK
---

Use the [Transposit JavaScript SDK](https://github.com/transposit/transposit-js-sdk) to call operations from a web app.

## Configure user sign-in

Your web app can be shared publicly or protected by sign-in. Web apps protected by sign-in can whitelist specific Google GSuite domains or specific users.

### Enable user sign-in

1. Navigate to **Authentication &gt; User Sign-in**.
2. Check **Require users to register and sign in with Google**
3. Specify **Successful sign-in URIs**.
Transposit only allows redirection to these URIs during sign-in. This list should be empty if you are only using [hosted apps](/building/hosted-apps).
4. Ensure a **Google Client ID** and **Google Client Secret** are present
5. Save the configuration
6. Optionally, choose to **Restrict to specific whitelisted domains and users**

### Disable user sign-in

1. Navigate to **Authentication &gt; User Sign-in**
2. Uncheck **Require users to register and sign in with Google**

## Deploy endpoints

Deploy the operations you want to call from your web app as endpoints.

### Public endpoints

If your app is shared publicly, deploy your endpoints without authentication.

1. Navigate to **Deploy &gt; Endpoints**
2. Find the operation you want to deploy
3. Choose **Deployed** from the dropdown menu
4. Save your changes

### Signed-in user endpoints

If your app is protected by sign-in, deploy your endpoints with user sign-in required.

1. Navigate to **Deploy &gt; Endpoints**
2. Find the operation you want to deploy
3. Choose **Deployed** from the dropdown menu
4. Check only **Require user sign-in**
5. Save your changes

## Read the SDK documentation

Once you have configured user sign-in and deployed endpoints, use the SDK to build your web app. Follow our [SDK documentation on GitHub](https://github.com/transposit/transposit-js-sdk).