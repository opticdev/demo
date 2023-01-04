# Optic demo repository
Try this demo repository to understand how Optic helps you work with OpenAPI specification files.

## Setup
### Cloud
Open the project in Gitpod with [this link](https://gitpod.io/#https://github.com/opticdev/demo) (open it in a new tab) and continue following the steps below in the pod's terminal.

### Local
Alternatively you can run the project in your local environment.

Clone this repository:
```
git clone git@github.com:opticdev/demo.git optic-demo && cd optic-demo
```

Then install the Optic CLI:
```
npm install -g @useoptic/optic
```

## Authenticate with Optic
Run this command and follow the instructions to login with Optic.

Login will let you visualize docs and diffs in our web application:
```
optic login
```

## Add your first API to Optic
Now that you're logged in, let's add the todo API to Optic:
```
optic api add todo-api.yaml
```

Let's check what has changed:
```
git diff
```

A custom `x-optic-url` field was added to `todo-api.yaml`.
This tells Optic to take this specification in account.

Learn more about the `optic api add` command with `optic api add --help`.

## Visualize API documentation
Time to push the spec and visualize the documentation in the Optic webapp:
```
optic spec push todo-api.yaml --web
```

## Visualize changes
Optic can let you visualize changes between two versions of an API spec.

Let's make a change to the todo API specification. For instance you could replace `in: path` by `in: query` line 10 in `todo-api.yaml`.

Then run optic diff. The `--web` flag lets Optic open the diff view in your browser:
```
optic diff todo-api.yaml --web
```

## Integrate with your CI
Optic is perfectly suited to run in your CI.

Once in your own repository, run the following command and follow the wizard to start getting automatic docs and diff visualization for your pull request and start enforcing company standards to your OpenAPI specification files:
```
optic ci-setup
```
