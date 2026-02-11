# CST8915 Lab3

## Links

- Youtube Demo Video: https://www.youtube.com/watch?v=sxJbqlYdOl8
- Order service repo: https://github.com/Sara-Aithssayene/order-service
- Product service repo: https://github.com/Sara-Aithssayene/product-service-Lab3
- Store front repo: https://github.com/Sara-Aithssayene/store-front

## Reflection Questions

### What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?

The main challenge I encountered with` configuring environment variables in GitHub Actions was understanding the difference between build-time variables and runtime variables (Azure Web App Environment Variables). Some variables, like service URLs or connection strings, needed to be configured directly in Azure rather than in the workflow file. Another challenge was troubleshooting deployment failures when variables were missing or incorrectly formatted, especially for services like RabbitMQ where a small mistake in the connection string could cause the application to crash at startup.

### How does deploying microservices on Azure Web App Service differ from running them locally?

Deploying microservices on Azure Web App Service is different from running them locally because I had less direct control over the environment and configuration. When I ran the services locally, I installed dependencies myself, used a local .env file, and ran each service on fixed ports like 3000 or 3030. When I ran them on a VM, I still controlled the ports and networking but had to configure firewall and access rules. When deploying to Azure Web App Service, dependencies were installed during deployment, and I had to configure environment variables in the Azure portal instead of using a local .env file. I also learned that instead of using public ports, Azure uses a public HTTPS URL.

### Why is it important to use environment variables for configurations in a cloud environment?

Environment variables are important in cloud environments because they allow applications to remain flexible, secure, and portable across different environments. Sensitive data such as connection strings, credentials, and service endpoints should not be hardcoded in source code, especially in public repositories. Using environment variables also allows cloud platforms like Azure to dynamically provide runtime configurations such as ports and service endpoints, making applications easier to scale and deploy across multiple environments.

## Static Web App Error

During this lab, I was not able to create the Azure Static Web App due to policy restrictions applied to the student Azure subscription. The deployment consistently failed with a policy violation error, even after attempting deployment in multiple available regions. Because of this limitation, I followed the alternative approach of running the store-front locally as recommended. Here is a screenshot of the Azure error message to document this issue.

![Static Web App Policy Error](./static-app-policy-error.png)
