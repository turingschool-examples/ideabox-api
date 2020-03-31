# IdeaBox API

To be used with the React III lesson.

## Set Up

Clone down this repo. (Do **NOT** nest it inside your IdeaBox repo!)

CD into this repo.

Run `npm install`.

Run `node server.js` to start the server.

## Endpoints

### GET all ideas

URL: `http://localhost:3001/api/v1/ideas`

Sample response (200):

```js
[
  {id: 1, title: 'Sweaters for pugs', description: 'To keep them warm'},
  {id: 2, title: 'Film a romcom', description: 'But make it ghosts'},
  {id: 3, title: 'A game show called Ether/Or', description: 'When you lose you get chloroformed'},
]
```

### GET an idea by its id

URL: `http://localhost:3001/api/v1/ideas/:id`

Sample URL: `http://localhost:3001/api/v1/ideas/3`

Sample response (200):

```js
{id: 3, title: 'A game show called Ether/Or', description: 'When you lose you get chloroformed'}
```

Sample response (404):

```js
{message: 'No idea found with an id of 3'}
```

### POST a new idea

URL: `http://localhost:3001/api/v1/ideas`

Sample request:

```js
{
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    id: 98623913021,
    title: 'Title',
    description: 'Description'
  })
}
```

Sample response (201): This is the idea that was submitted in the POST request

```js
  { id: 98623913021, title: 'Title', description: 'Description' }
```

Sample BAD request:

```js
{
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    id: 98623913021,
    title: 'Title'
  })
}
```

Sample BAD response (422):

```js
  { message: 'You are missing a required parameter of description' }
```

### DELETE an idea

URL: `http://localhost:3001/api/v1/ideas/:id`

Sample URL: `http://localhost:3001/api/v1/ideas/2`

Sample response (204): no content in the body, nothing to parse

Sample BAD response (404):

```js
{message: 'No idea found with an id of 2'}
```
