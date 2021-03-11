# Trial task for back-end developers

Please use Node.js 12+ and a web framework of your choice to implement the following trial task. You can use any node libraries you think are necessary or helpful for you, but it helps us a lot if you keep it minimal. It is recommended to use some code-formatter and linter of your choice (we recommend [Prettier](https://prettier.io/) and [XO](https://github.com/xojs/xo)).

## Password check API

Implement an API in Node.js that provides an endpoint to check a password. The endpoint should allow to POST a password and respond with either a [204](https://httpstatusdogs.com/204-no-content) if the password is fine or with a [400](https://httpstatusdogs.com/400-bad-request) and a set of errors in case the password does not match the minimal password rules. Please consult the swagger UI at https://erasys.github.io/backend-trial-task/ (browsing `swagger.yml`) for the desired API structure.

## Script for checking passwords

We provided you with an SQL dump of 200 passwords. Write a CLI script in Node.js that reads those passwords from a DB and uses the API you created earlier to try each of them. It should output a success message or the errors you received from the API for each of the responses.

## Checking for compromised passwords (BONUS)

Extend your script to check each password not only for validity but also if it has been compromised in the past. Consolidate the provided compromised-password API for this.

### Using the compromised password API

There is a docker image available for you [on docker-hub](https://hub.docker.com/r/erasys/compromised-pw-api). It exposes a very simple API via port 5000. You can find the API documentation in the Swagger UI at https://erasys.github.io/backend-trial-task/ – **please browse `swagger-compromised.yml` to see the correct API definitions**.

## Sending the solution to us

You can choose to send the solution as a ZIP archive (https://git-scm.com/docs/git-archive) or upload it as private repository to a GIT hoster of your choice, giving us access to it.
