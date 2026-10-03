# PiAi

A judgement is only as good as the labels it was taught from. This is the little React game that collects
them: a shape is drawn on the screen, and the player decides whether the thing shown sits **inside or outside
the circle** in the square. It is a deliberately simple task with a right answer, which makes it training data
rather than an opinion poll.

It is the front end of the `inputresponse` family — a small web app used to gather human answers that a model
can then be checked against.

## What it does

- Draws the circle-in-a-square figure and takes the player's answer.
- Signs the player in with Google when `REACT_APP_GOOGLE_CLIENTID` is set (`gapi-script`).
- Reads and writes through a GraphQL API with `@apollo/client` over HTTP and `graphql-ws`.
- Keeps its URL state in the address bar with `@scaleway/use-query-params`, and renders with `antd`.

## Run it

```bash
npm install
cp .env.example .env
npm start        # react-scripts, http://localhost:3000
```

`.env`:

| Variable | What it is |
|---|---|
| `REACT_APP_ENV` | the environment label |
| `REACT_APP_GOOGLE_CLIENTID` | the Google client ID, and it must match the API's own setting |
| `REACT_APP_API_URL` | the GraphQL endpoint |
| `REACT_APP_WSS_URL` | the GraphQL web socket endpoint |
| `REACT_APP_ISSUES_URL` | where a report of a problem goes |

```bash
npm run build    # production bundle
npm test         # standard --verbose
```

## Licence

MIT — see [LICENSE](./LICENSE).
