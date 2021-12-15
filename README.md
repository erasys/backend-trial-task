# Trial task for back-end developers

Someone from support notified us that users are using too many times passwords like "password", "dog123", or "heeello" and their accounts are getting hacked by their neighbours to see private pictures of their private parts.
We need this fixed ASAP, but our developers are busy working on the next-cool-feature™ using the next-cool-stack™, and they have no time for implementing the changes needed to fix the issue. So our only chance is YOU!*

Your objective for this task is to build two components:
- a REST API that receives a password and gives information about its validity, given a set of rules
- a script that reads the already existing passwords from the database and sets a validity flag based on the API you implement

We ask you to use Node.js 12+ (TypeScript is an option), MySQL and a web framework of your choice to implement the following trial task. You can use TypeScript and any node libraries you think are necessary or helpful for you, but it helps us a lot if you keep it minimal. We recommend using some code-formatter and linter of your choice (we recommend [Prettier](https://prettier.io/) and [XO](https://github.com/xojs/xo)).

What we value when reviewing your task:
- attention to perfomance and scalability
- a good README with instructions on how to run your execution
- good code architecture
- consistent styling, and not too many typos or commented code

If you have any questions regarding the task, please reach out to us anytime!

## Task 1 - Password validation API

Implement an API that provides an endpoint to validate a password. The endpoint should allow to POST a password and respond with either a [204](https://httpstatusdogs.com/204-no-content) if the password is fine or with a [400](https://httpstatusdogs.com/400-bad-request) and a set of errors in case the password does not match the minimal password rules. Consult the [Swagger UI in the GitHub page of this project](https://erasys.github.io/backend-trial-task/?url=swagger.yml) for the desired API structure.

The rules to check if a password is valid should be stored in a separate configuration file (JSON, YAML or something else). This file should include the following information per rule:

- Regular expression to check the rule
- Error message to show in case the rule is not met

The ruleset the passwords have to be validated against is:
- Length is minimum five characters
- At least one digit is used
- There are no more than two repeating consecutive characters (like 'bbb' – two are allowed, but not three or more)
- There is at least one upper-case character OR one special character [anything that is neither letter nor a number]

## Task 2 - Script for batch-validation of passwords

We provided you with an SQL dump of 200 passwords. Write a CLI script in Node.js that reads those passwords from a DB and uses the API you created earlier to validate each of them. It should output a success message or the errors you received from the API for each response.

The script must also set the `valid` field to 1 or 0 for valid and invalid passwords in the given MySQL table.

Please provide and document a possibility to change the MySQL connection settings used by the script.

## Task 3 (BONUS) - Checking for compromised passwords

Extend the script you produced for Task 2 to include a check that uses a second API which tells you if passwords have been compromised in the past.
This second API is already provided by [this image](https://hub.docker.com/r/erasys/compromised-pw-api). It exposes a very simple API via port 5000.
You can find the API documentation in the [Swagger UI in the GitHub page of this project](https://erasys.github.io/backend-trial-task/?url=swagger-compromised.yml).


## Sending the solution to us

You can choose to send the solution as a ZIP archive (https://git-scm.com/docs/git-archive) or upload it as a private repository to a GIT hoster of your choice, giving us access to it.

*this is just a joke, our systems does not accept passwords that are so simple, duh! 💅
