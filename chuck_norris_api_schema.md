openapi: 3.1.0
info:
  title: "Chuck Norris Jokes API"
  description: "A free JSON API for hand-curated Chuck Norris facts."
  version: "v1.0.0"
servers:
  - url: "https://api.chucknorris.io"
paths:
  /jokes/random:
    get:
      summary: "Retrieve a random Chuck Norris joke in JSON format."
      operationId: "GetRandomChuckJoke"
      responses:
        200:
          description: "Successful response with a Chuck Norris joke."
          content:
            application/json:
              example:
                icon_url: "https://assets.chucknorris.host/img/avatar/chuck-norris.png"
                id: "4glls4ZTTEe4-D9QFd883g"
                url: ""
                value: "Learn to spell & your jokes are shit. Chuck Norris deserves more than this."
  /jokes/random?category={category}:
    get:
      summary: "Retrieve a random Chuck Norris joke from a given category in JSON format."
      operationId: "GetRandomChuckJokeByCategory"
      parameters:
        - name: "category"
          in: "query"
          description: "The category of Chuck Norris joke to retrieve"
          required: true
          schema:
            type: "string"
      responses:
        200:
          description: "Successful response with a Chuck Norris joke from the specified category."
          content:
            application/json:
              example:
                icon_url: "https://assets.chucknorris.host/img/avatar/chuck-norris.png"
                id: "4glls4ZTTEe4-D9QFd883g"
                url: ""
                value: "Learn to spell & your jokes are shit. Chuck Norris deserves more than this."
  /jokes/categories:
    get:
      summary: "Retrieve a list of available categories for Chuck Norris jokes."
      operationId: "GetChuckJokeCategories"
      responses:
        200:
          description: "Successful response with a list of available Chuck Norris joke categories."
          content:
            application/json:
              example: ["animal", "dev", "food", "history", "music", "science", "sport"]
  /jokes/search?query={query}:
    get:
      summary: "Perform a free-text search for Chuck Norris jokes."
      operationId: "SearchChuckJokes"
      parameters:
        - name: "query"
          in: "query"
          description: "The search query to find Chuck Norris jokes"
          required: true
          schema:
            type: "string"
      responses:
        200:
          description: "Successful response with Chuck Norris jokes matching the search query."
          content:
            application/json:
              example:
                - icon_url: "https://assets.chucknorris.host/img/avatar/chuck-norris.png"
                  id: "4glls4ZTTEe4-D9QFd883g"
                  url: ""
                  value: "Learn to spell & your jokes are shit. Chuck Norris deserves more than this."
components:
  schemas: {}`
