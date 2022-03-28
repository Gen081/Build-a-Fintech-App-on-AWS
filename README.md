# Build-a-Fintech-App-on-AWS
Build a Fintech App on AWS Using the Plaid API


Open Finance initiatives have been gaining momentum across the world.

The fintech app providers are generally not banks, but they offer users a variety of convenient payment and finance features on smartphone apps. Users simply need to link the app to their bank and brokerage accounts, and grant the necessary permissions.

Fintech apps offer users benefits such as:

- Viewing balances across multiple bank accounts.
- Initiating payments to friends.
- Applying for loans without gathering and scanning bank and income statements.
- Paying for things online using a “Buy Now Pay Later” plan.
- Showing monthly income and expense categories to help set budgets.
- Displaying overall investment performance across multiple brokerage accounts.
- Buying crypto-assets.


In this project, I will show you how to build and deploy a basic fintech app on Amazon Web Services (AWS) in under an hour by using the **[Plaid Link API](https://plaid.com/docs/link/)**. This app allows users to sign up, log in, select their bank from a list, connect to that bank, and display the latest transactions.

### What is Plaid?

**[Plaid](https://plaid.com/)** is a San Francisco-based financial services company and [AWS Partner](https://partners.amazonaws.com/partners/0010h00001cBFNCAA4/Plaid) that helps fintech providers connect users safely to their bank accounts.

The Plaid Link acts as a secure proxy between a fintech app and a bank. It is currently able to connect to more than 12,000 banks and financial institutions throughout the world. It provides a single API to connect to them. 


### Architectural Design

![](pics/architecture.png)



#### Prerequisites 




- Install the Amplify CLI

The Amplify Command Line Interface (CLI) is a unified toolchain to create AWS cloud services for your app. Let's go ahead and install the Amplify CLI.

```
curl -sL https://aws-amplify.github.io/amplify-cli/install | bash && $SHELL
```

![](pics/amplify-cli-install.png)


- Configure the Amplify CLI

To set up the Amplify CLI on my local machine, I have to configure it to connect to my AWS account. 

```
amplify configure
```

Amplify configure command will ask to sign into the AWS Console.

![](pics/amplify-config.png)

The following shows the new user permission credential:

![](pics/amplify-config1.png)


Initialize a new Amplify project. When prompted, Hit **Return/Enter** to accept the defaults.

![](pics/amplify-init.png)

![](pics/amplify-init1.png)


- Add authentication

```
amplify add auth
```

When prompted, Hit **Return/Enter** to accept the defaults.

![](pics/amplify-auth.png)



- Add the API:

```
amplify add api
```

![](pics/amplify-add-api.png)

When prompted for the **client_id**, it can found in the Plaid webpage dashboard that I previously created and logged in.

![](pics/amplify-add1-api.png)


