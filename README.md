# Airbyte

## there are three ways this can work 
* No Code
 ```URL
  https://www.youtube.com/watch?v=mE655VHbP-c&feature=youtu.be
  ```
* Low Code
 ```URL
  https://www.youtube.com/watch?v=i7VSL2bDvmw
  ```
* Language Specific
 ```URL
  https://www.youtube.com/watch?v=sfCr6JjSH_Y
  ```


``` URL
https://airbyte.com/product/connector-development-kit
```

## No code

- **Connector Builder UI**: A user-friendly interface for iterating on low-code connectors, currently in beta. Feedback can be shared via Slack or email.
- **Development Updates**: Announcements and updates are shared through the #help-connector-development Slack channel.
- **Building Process**: Differentiates between the connector, configured source, and connection, detailing their roles in data extraction and syncs.
- **Contributing Connectors**: Guides on exporting connectors to YAML, building Docker images, and contributing to the Airbyte catalog.
- **Importing Connectors**: Instructions on importing `manifest.yaml` files from Airbyte-managed connectors into the builder.

## Low code

- **Low-code connector development**: Airbyte’s low-code framework enables you to build source connectors for REST APIs via a connector builder UI or by modifying boilerplate YAML files via terminal or text editor.
- **Developer updates**: Announcements and updates are shared through the #help-connector-development Slack channel.
- **Why low-code?**: API Connectors are common and formulaic. API connector code almost always solves small variations of these problems: Making requests to various endpoints under the same API URL, Authenticating using a common auth strategy such as Oauth or API keys, Pagination using one of the 4 ubiquitous pagination strategies: limit-offset, page-number, cursor pagination, and header link pagination, Gracefully handling rate limiting by implementing exponential backoff, fixed-time backoff, or variable-time backoff, Describing the schema of the data returned by the API, so that downstream warehouses can create normalized tables, Decoding the format of the data returned by the API (e.g JSON, XML, CSV, etc..) and handling compression (GZIP, BZIP, etc..), Supporting incremental data exports by remembering what data was already synced, usually using date-based cursors and so on.
- **A declarative, low-code paradigm commoditizes solving formulaic problems**: Given that these problems each have a very finite number of solutions, we can remove the need for writing the code to build these API connectors by providing configurable off-the-shelf components to solve them. In doing so, we significantly decrease development effort and bugs while improving maintainability and accessibility].
- **What connectors can I build using the low-code framework?**: Refer to the REST API documentation for the source you want to build the connector for and answer the following questions: Does the REST API documentation show which HTTP method to use to retrieve data, and that the response is a JSON object? Do the queries return data synchronously? Does the API support any of the following pagination mechanisms: Offset count passed either by query params or request header Page count passed either by query params or request header.

## Language specific

- **Connector Development Kit (CDK)**: The Airbyte Python CDK is a framework for rapidly developing production-grade Airbyte connectors. Over the next few months, the project will only accept connector contributions that are made using the Low-Code CDK or the Connector Builder.
- **Python CDK**: The Python CDK offers helpers specific for creating Airbyte source connectors for HTTP APIs (REST APIs, GraphQL, etc..) and Generic Python sources.
- **Getting Started**: You can generate an empty connector using the code generator. After generating, you will find all TODOs in the generated project directory. They're accompanied by comments explaining what you'll need to do in order to implement your connector.
- **Concepts & Documentation**: If you want to learn more about the classes required to implement an Airbyte Source, head to the basic concepts doc. For tips on useful Python knowledge, see the Python Concepts page.
- **Tutorials**: You can find a complete tutorial for implementing an HTTP source connector in this tutorial.
- **Developer updates**: Announcements and updates are shared through the #help-connector-development Slack channel.

