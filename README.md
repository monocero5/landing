# Monoceros

## Contents

1. [Short description](#short-description)
1. [Demo video](#demo-video)
1. [The architecture](#the-architecture)
1. [Getting started](#getting-started)
1. [Deployment](#deployment)
1. [Live demo](#live-demo)
1. [Built with](#built-with)
1. [Contributing](#contributing)
1. [Authors](#authors)
1. [License](#license)

## Short description

### What's the problem?

The World Humanitarian Summit set a goal of increasing transparency and insight of the supply chain processes in the ‘Agenda for Humanity. Supply chain is a key enabler for one of the NGOs’ major missions: distributing drugs, vaccines and food. To succeed, they need to reach the right place at the right time, but if dealing with an inefficient system, they may incur in severe human and monetary losses, as supply chain spending accounts for ~70% of operational costs.

### How can technology help? 

Data is at the core of the supply chain and inventory management. But if not done right, data issues can have dramatic consequences especially in emergency response such as for COVID-19, where resources are limited and logistics is challenging.

Technology can help to bridge the current data-gap by:

* automatically monitoring warehouse without requiring additional training or infrastructure changes.
* simplifying data collection over the whole supply-chain, giving managers a complete visibility on what is happening where along the entire journey, allowing them to optimise the resources.
* detecting in real-time any issue such as delays, variations in storage conditions and theft.

### The idea

Our technology is a user-centric, cost-efficient platform adaptable to any mission’s type, specifically designed to collect relevant data and turn them into actionable insights. Our smart technology uses an AI-powered sensor to autonomously updates the inventory levels and send you real-time alerts such as delays in the delivery, conditions breaching the limits and theft.

Schools and teachers can continue to engage with their students through virtual classrooms, and even create interactive spaces for classes. As parents face a new situation where they may need to homeschool their children, finding appropriate online resources is important as well.

## Getting started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

## Requirements
* Node 6.0.0 or higher

## Running Locally

Run the following commands:
```bash
npm install
npm start
```
Use the link http://localhost:3000 to load the web application in browser.

## Live demo

[![Watch the video](https://img.youtube.com/vi/pVBU1RJazkc/maxresdefault.jpg)](https://youtu.be/pVBU1RJazkc)

You can find a running system to test at [welcome.seeone.io](https://welcome.seeonee.io/)

The data used in the live demo can be found here: [dummy data](https://drive.google.com/drive/folders/13IV-g2vblpzRwJxzZrQmLWwCxGdTQfJG?usp=sharing)

## Deployment

**Important:** Before going live, remove http://localhost:3000/* from the list of web redirect URLs located in "Manage Authentication" -> "Authentication Settings" page in the AppID dashboard.

1. Login to IBM Cloud.

  `ibmcloud login -a https://api.{{domain}}`

2. Target a Cloud Foundry organization and space in which you have at least Developer role access:

  Use `ibmcloud target --cf` to target Cloud Foundry org/space interactively.

3. Bind the sample app to the instance of App ID:

  `ibmcloud resource service-alias-create "appIDInstanceName-alias" --instance-name "appIDInstanceName" -s {{space}}`
  
4. Add the alias to the manifest.yml file in the sample app.

   ```
   applications:
        - name: [app-instance-name]
        memory: 256M
        services:
        - appIDInstanceName-alias
   ```

5. Deploy the sample application to IBM Cloud. From the app's folder do:

  `ibmcloud app push`
  
6. Now configure the OAuth redirect URL at the App ID dashboard so it will approve redirecting to your cluster. Go to your App ID instance at [IBM Cloud console](https://cloud.ibm.com/resources) and under Manage Authentication->Authentication Settings->Add web redirect URLs add the following URL:

   `https://{App Domain}/ibm/cloud/appid/callback`
   
   You find your app's domain by visiting Cloud Foundry Apps at the IBM Cloud dashboard: https://cloud.ibm.com/resources.

7. Open your IBM Cloud app route in the browser.

## Built with

* [IBM App ID](https://cloud.ibm.com/catalog?search=app%20id#search_results) - The Oauth
* [IBM Cloud Foundry](https://cloud.ibm.com/catalog?search=Cloud%20Foundry#search_results) - PaaS
* [IBM Cloud Delivery](https://cloud.ibm.com/catalog?search=CDN#search_results) - Distribute the content and add encryption
* [Grafana](http://www.dropwizard.io/1.0.2/docs/) - The dashboards

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Authors

* **Dorian Vetrila** 
* **Théophile Griveau-Billion**

See also the list of [contributors](https://github.com/Code-and-Response/Project-Sample/graphs/contributors) who participated in this project.

## License

This project is licensed under the Apache 2 License - see the [LICENSE](LICENSE) file for details
