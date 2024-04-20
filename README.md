# Serverless TypeScript Starter Kit

This project is a starter kit for developing serverless applications with TypeScript.

## Requirements

- Node.js v20
- Serverless Framework

## Installation

1. Clone this repository.
2. Install the dependencies with `npm install`.
3. Install Serverless globally with `npm install -g serverless`.

## Usage

To deploy the application, run the following command:

```shell
serverless deploy --stage <stage_name>
```

## Testing

To run the tests, run the following command:

```shell
npm run test
```

## Linting

This project uses ESLint for linting. To run linting on all TypeScript files, use the following command:

```shell
npm run lint
```

## Husky

This project uses Husky to manage Git hooks. Git hooks are scripts that run automatically 
when certain events occur in Git, such as a commit or a push.

### Setup

To set up Husky, follow these steps:

1. Install Husky as a dev dependency with the following command:

```shell
npm install --save-dev husky
```
Add the following scripts to your package.json file:

```json
{
  "scripts": {
    "prepare": "husky install",
    "postinstall": "husky install"
  }
}
```

Run the prepare script to install Husky:

```shell
npm run prepare
```

Add the hooks you need. For example, to add a pre-commit hook that runs lint-staged and npm run test, you can use 
the following command:

```shell
npx husky add .husky/pre-commit "npx lint-staged && npm run test"
```

This will create a pre-commit file in the .husky folder with the specified content.

You don't need to do anything special to use Husky. The hooks run automatically when the corresponding events 
occur in Git.  If you need to temporarily disable the hooks 
(for example, if you want to make a commit without running the tests), you can do so with the following command:

```shell
git commit --no-verify
```

This command makes a commit without running the pre-commit and commit-msg hooks

## Contributing

Contributions are welcome. Please make sure to pass the tests and linting before submitting a pull request.

## License

This project is licensed under the terms of the MIT license.