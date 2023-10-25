# Prismic + Vue + Nuxt Project

This dummy website repository is built with the following technologies:

## Technologies Used

- **Prismic**: Content management system (CMS) for creating and managing structured content with an API.
- **Vue 3**: Progressive JavaScript framework for building interactive web applications.
- **Nuxt**: Framework for building web applications with server-side rendering
- **TypeScript**: Improving code quality and productivity with static typing.
- **Tailwind CSS**: A utility-first CSS framework for simplified and consistent styling.


[Explore the Live Demo](https://flowrise-nuxt-project-pdqe4tx2k-dmitriyangve.vercel.app/)

## Features:

- Tailwind design, animations, effects and responsive


### Prerequisites

**Node version 18.x.x**

## Installation and Usage

### 1. Cloning the repository

```shell
git clone https://github.com/DmitriyAngve/sass-ai
```

### 2. Install packages

```shell
npm i
```

### 3. Setup .env file

```js
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=

NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/dashboard
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/dashboard

OPENAI_API_KEY=
REPLICATE_API_TOKEN=

DATABASE_URL=

STRIPE_API_KEY=
STRIPE_WEBHOOK_SECRET=

NEXT_PUBLIC_APP_URL="http://localhost:3000"
```

### 4. Setup Prisma

Add MySQL Database (I used PlanetScale)

```shell
npx prisma db push
```

### 5. Start the app

```shell
npm run dev
```

## 6. Available commands

Running commands with npm `npm run [command]`

| command         | description                              |
| :-------------- | :--------------------------------------- |
| `dev`           | Starts a development instance of the app |
