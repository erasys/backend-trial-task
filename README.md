# Trial task for back-end developers

Please use Node.js 12+, MySQL and a web framework of your choice to implement the following trial task. You can use any node libraries you think are necessary or helpful for you, but it helps us a lot if you keep it minimal. It is recommended to use some code-formatter and linter of your choice (we recommend [Prettier](https://prettier.io/) and [XO](https://github.com/xojs/xo)).

If you have any questions regarding the task, feel free to reach out to us anytime!

## 1 - Password check API

Implement an API in Node.js that provides an endpoint to check a password. The endpoint should allow to POST a password and respond with either a [204](https://httpstatusdogs.com/204-no-content) if the password is fine or with a [400](https://httpstatusdogs.com/400-bad-request) and a set of errors in case the password does not match the minimal password rules. Please consult the [Swagger UI in the GitHub page of this project](https://erasys.github.io/backend-trial-task/?url=swagger.yml) for the desired API structure.

The rules to check if a password is valid should be stored in a separate configuration file (JSON, YAML or something else). This file should include the following information per rule:

- Regular expression to check the rule
- Error message to show in case the rule is not met

The ruleset the passwords have to be validated against is:
- length is minimum 5 characters
- At least one digit is used
- There are no more than two repeating characters (like 'bbb' – 2 are allowed, but not 3 or more)
- There is at least one upper-case character OR one special character [anything that is neither letter or a number]

## 2 - Script for checking passwords

We provided you with an SQL dump of 200 passwords. Write a CLI script in Node.js that reads those passwords from a DB and uses the API you created earlier to validate each of them. It should output a success message or the errors you received from the API for each of the responses.

The script must set the `valid` field to 1 or 0 for valid and invalid passwords.

Please provide and document a possibility to change the MySQL connection settings used by the script.

## 3 (BONUS) - Checking for compromised passwords

Extend your script to check each password not only for validity but also if it has been compromised in the past. Please use the provided compromised password API for this.

### Using the compromised password API

There is a docker image available for you [on docker-hub](https://hub.docker.com/r/erasys/compromised-pw-api). It exposes a very simple API via port 5000. You can find the API documentation in the [Swagger UI in the GitHub page of this project](https://erasys.github.io/backend-trial-task/?url=swagger-compromised.yml).

## Sending the solution to us

You can choose to send the solution as a ZIP archive (https://git-scm.com/docs/git-archive) or upload it as a private repository to a GIT hoster of your choice, giving us access to it.
