[![CircleCI](https://circleci.com/gh/iotexproject/iotex-explorer.svg?style=svg)](https://circleci.com/gh/iotexproject/iotex-explorer)

# iotex-explorer

Frontend website for [IoTeX blockchain](https://github.com/iotexproject/iotex-core).

Check our site hosted at [https://iotexscan.io].

Or deploy your own instance on Heroku.

<a href="https://heroku.com/deploy?template=https://github.com/iotexproject/iotex-explorer">
  <img src="https://www.herokucdn.com/deploy/button.svg" alt="Deploy">
</a>

## Development

Prepare environment variables.

```
cp ./.env.tmpl ./.env
```

And specify environment variables in `.env` file.

```
nvm install 8.11.3
npm install

# watch the change during development
npm run watch
# go visit http://localhost:4004/

# test
npm run test
```

We use [inferno-test-utils](https://www.npmjs.com/package/inferno-test-utils/v/3.10.1) for the view test.

## Build and Run in Production

```
npm run bp
NODE_ENV=production npm run start
```

### Scripts

- `npm run test` to run all tests
- `npm run ava <path/to/file>` to run a specific test

### Run with Docker if you want

##### Please install Docker: `https://docs.docker.com/install/`

Building your image:
`docker build -t <your username>/explorer .`

Your image is now listed by Docker:
`docker images`

##### Run the image

`docker run -p <port>:4004 -d <your username>/explorer`
the `-p` flag redirects a public prot to a private port inside the container.
Just choose any port ex) 49160

Print the output of the app:
`docker ps`

print app output
`docker logs <container id>`

If you need to test your app, get the port of your app that Docker mapped:
`docker ps`
`curl -i localhost:<port ex) 49160>`
