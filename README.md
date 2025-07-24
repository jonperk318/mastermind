# Mastermind

The Mastermind board game built with Vue.js

## Run

```bash
pnpm dev
```

Go to `http://localhost:3333`

## Build

```bash
pnpm build
```

The app can be served from the `dist` directory

## Deploy on Netlify

Go to [Netlify](https://app.netlify.com/start) and select your clone, `OK` along the way, and your App will be live in a minute.

## Docker Production Build

First, build the vitesse image by opening the terminal in the project's root directory.

```bash
docker buildx build . -t vitesse:latest
```

Run the image and specify port mapping with the `-p` flag.

```bash
docker run --rm -it -p 8080:80 vitesse:latest
```
