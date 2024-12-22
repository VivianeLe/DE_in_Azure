# Azure Data Factory Project - DE_in_Azure

This repository contains the **Azure Data Factory (ADF)** configurations, pipelines, datasets, and linked services required for implementing a scalable Data Engineering solution in Azure. The project is designed to showcase best practices in **data orchestration, integration, and pipeline automation** using ADF.

---

## Table of Contents

1. [Overview](#overview)
2. [Project Structure](#project-structure)
3. [Key Components](#key-components)
4. [Deployment Instructions](#deployment-instructions)
5. [How to Use](#how-to-use)
6. [Future Enhancements](#future-enhancements)
7. [Contributing](#contributing)
8. [License](#license)

---

## Overview

This project demonstrates how to create, manage, and deploy Data Factory pipelines and resources using **ARM templates** and other artifacts. The project follows the modular design to separate data integration components such as pipelines, datasets, and linked services, enabling better manageability and reusability.

### Key Objectives:
- Automate the orchestration of data movement and transformation using Azure Data Factory.
- Manage resources (pipelines, datasets, dataflows, linked services) programmatically.
- Enable CI/CD for deploying ADF configurations using ARM templates and `publish_config.json`.

---

## Project Structure

```plaintext
DE_in_Azure/
├── dataflow/               # Dataflows for data transformation (mapping, wrangling)
├── dataset/                # Datasets for source and sink configurations
├── factory/                # Root directory for the Azure Data Factory configuration
├── integrationRuntime/     # Self-hosted or Azure-hosted integration runtimes
├── linkedService/          # Linked service configurations for external connections
├── pipeline/               # Data Factory pipelines for orchestration
├── udacityFactory/         # ARM templates and parameters for deployment
├── README.md               # Project documentation
└── publish_config.json     # Configuration for publishing ADF pipelines
```

### Description of Key Folders:
1. **`dataflow/`**: Contains mapping and wrangling dataflows for transforming data within ADF.
2. **`dataset/`**: Stores dataset definitions that represent data sources and destinations.
3. **`factory/`**: Metadata and settings for the Azure Data Factory instance.
4. **`integrationRuntime/`**: Definitions of integration runtimes (self-hosted or Azure-hosted).
5. **`linkedService/`**: Linked services for securely connecting to external resources like SQL databases, Blob storage, or APIs.
6. **`pipeline/`**: JSON files representing ADF pipelines that orchestrate data workflows.
7. **`udacityFactory/`**: Contains ARM templates for deploying ADF resources programmatically.

---

## Key Components

1. **Pipelines**:
   - Handles the orchestration of employee data ingestion and transformation.
   - Modular pipelines to handle specific data workflows.

2. **Datasets**:
   - Source datasets for ingesting raw data.
   - Sink datasets for storing processed data in SQL, Data Lake, or Blob Storage.

3. **Linked Services**:
   - Connections to external resources like Azure Blob Storage, Azure SQL Database, or other cloud services.

4. **Integration Runtime**:
   - Configurations for Azure-hosted or self-hosted runtimes to enable secure data movement.

5. **Dataflows**:
   - Mapping dataflows for performing ETL/ELT operations.

---

## Deployment Instructions

### Deploying Using Azure Portal:
1. Navigate to the **udacityFactory** directory.
2. Locate the ARM templates:
   - `template.json`
   - `parameters.json`
3. Deploy the templates in the Azure Portal:
   - Go to **Deploy a custom template**.
   - Upload the `template.json` and `parameters.json` files.
   - Specify the necessary parameters (resource group, factory name, etc.).

### Deploying Using Azure CLI:
1. Run the following command to deploy the ARM templates:
   ```bash
   az deployment group create \
       --resource-group <RESOURCE_GROUP> \
       --template-file udacityFactory/template.json \
       --parameters udacityFactory/parameters.json
   ```

### Publish ADF Changes:
- Use the `publish_config.json` file to push changes to Azure:
   ```bash
   az datafactory publish --resource-group <RESOURCE_GROUP> --factory-name <FACTORY_NAME>
   ```

---

## How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/VivianeLe/DE_in_Azure.git
   cd DE_in_Azure
   ```

2. Modify the pipeline JSON or ARM templates to match your resource configurations (e.g., storage account, SQL server).

3. Deploy the configurations to Azure using the steps above.

4. Monitor pipeline runs in the Azure Data Factory interface.

---

## Future Enhancements

- Add examples for real-time data ingestion using Event Hubs.
- Implement CI/CD workflows with GitHub Actions or Azure DevOps.
- Integrate with Databricks for advanced data transformations.
- Add logging and monitoring dashboards using Azure Monitor.

---

## Contributing

Contributions are welcome! Follow these steps:
1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit your changes and open a pull request.

---

## License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

This README provides a comprehensive overview of your project, its structure, deployment steps, and future directions. Let me know if you'd like any adjustments!
