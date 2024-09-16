# Discord Bot AWS Template

Built to run perpetualy as a ECS container running on AWS EC2 t2.micro for very cheap/free. 

Has a clear separation of concerns between the bot and the commands it can run. This allows for easy extensibility and maintainability. 

Has 100% test coverage so you can trust that this bot works exactly as intended, and start adding new tests for new commands from a clean slate.

Written in typescript and runs as a daemon process using `ts-node`.

## Running Locally

```sh
npm i
npm run start
```

Bot will run inside of terminal until killed as it's essentially a DAEMON process.

## Linting

```sh
npm run lint # fixes any issues it can fix automatically
```

## Getting Credentials

### Your Bot Token
1. Go to the [Discord Developer Portal](https://discord.com/developers/applications)
2. Create a new application
3. Go to the Bot tab and create a new bot
4. Copy the token

### Your Guild ID
1. Go to your Discord server
2. Right click on the server name in the left sidebar
3. Click on "Copy ID"

### Your Client ID
1. Go to the [Discord Developer Portal](https://discord.com/developers/applications)
2. Click on the application you created earlier
3. Go to the OAuth2 tab
3. Copy the Client ID

## Deploying to AWS

1. Install AWS CLI and configure your AWS credentials.
2. Install AWS CDK: `npm install -g aws-cdk`
3. Bootstrap your AWS environment: `cdk bootstrap`
4. Deploy the stack: `npm run cdk:deploy`

Note: Ensure you have set up the necessary environment variables (CLIENT_ID, GUILD_ID, BOT_TOKEN) in your AWS account or directly in the CDK stack.

## Inviting Your Bot to Your Server

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications)
2. Click on the application you created earlier
3. Go to the OAuth2 tab
4. In the "OAuth2 URL Generator" section, select the "bot" scope
5. Copy the generated URL and paste it into your browser
6. Select the server you want to invite the bot to
7. Click "Authorize"
