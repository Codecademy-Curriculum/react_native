# Spring Workspace

## Setup

Sample working Author workspace: https://author.codecademy.com/exercises/b7a31d3ba6784aaa951da88f7da8e864

In Author:
* Choose the `spring-6-gradle` workspace if the exercise requires a server (e.g checkpoints that require cURL).
* Choose `spring-6-gradle-no-server` if it doesn't require a server. This will let the workspace load up much faster.

The open port is `4001` for `localhost:4001`.

You can paste in the content of your code base including:

* `/gradle` directory
* `/src` directory
* `build.gradle.kts` 
* `gradlew`
* `setting.gradle.kts`

You can leave out `/build` because it'll regenerate when building.

`build.gradle.kts` _must_ use Spring Boot `3.3.3` for the automatic server. 

## Using

When the exercise is loaded, the server should already be running. cURL commands can be made to port `4001` without additional commands.

For example:

```bash
curl -X POST localhost:4001/api/v1/books \
  -H "Content-Type: application/json" \
  -d '{"title":"Circe","author":"Madeline Miller","price":9.99}'
```

```bash
curl -X GET localhost:4001/api/v1/books
```

Notice that `localhost:4001` does not contain `http` or `https`.

To run the application, use the command `gradle bootRun`. However, by default the application will run on port `8080`. In this case, add `server.port = 4001` to `application.properties` so that the Tomcat server will change its port to `4001` (so instructions are still valid).

The app re-compiles when learners click “Run” in the LE after making changes.