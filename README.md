NextAuth.js is a complete open source authentication solution.

This is an example application that shows how `next-auth` is applied to a basic Next.js app.

The deployed version can be found at [`authsandbox.vercel.app](https://authsandbox.vercel.app/)

## Getting Started

### 1. Clone the repository and install dependencies

```
git clone https://github.com/nextauthjs/next-auth-example.git
cd next-auth-example
npm install
```

### 2. Configure your local environment

Copy the .env.local.example file in this directory to .env.local (which will be ignored by Git):

```
cp .env.local.example .env.local
```
### 3. Configure Authentication Providers

1. Review and update options in `pages/api/auth/[...nextauth].js` as needed.

2. When setting up OAuth, in the developer admin page for each of your OAuth services, you should configure the callback URL to use a callback path of `{server}/api/auth/callback/{provider}`.

  e.g. For Google OAuth, visit: `https://console.cloud.google.com/apis/credentials`, add a new OAuth 2.0 Client, and make sure to have `http://localhost:3000/api/auth/callback/google` as the [Authorized redirect URI]. While you are there, you need to copy both ClientID and ClientSecrete and update .env.local file (i.e., GOOGLE_ID = ClientId, GOOGLE_SECRET = ClientSecrete).

  A list of configured providers and their callback URLs is available from the endpoint `/api/auth/providers`. You can find more information at https://next-auth.js.org/configuration/providers/oauth

3. You can also choose to specify an SMTP server for passwordless sign in via email.

### 4. Start the application

To run your site locally, use:

```
npm run dev
```

To run it in production mode, use:

```
npm run build
npm run start
```

### 5. Preparing for Production

Follow the [Deployment documentation](https://next-auth.js.org/deployment)

## Acknowledgements

This is a fork of https://github.com/nextauthjs/next-auth.

## License

ISC

