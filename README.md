# Comprehensive Guide to ML Project Lifecycle with MLflow

This guide outlines the end-to-end process of executing a Machine Learning project, leveraging MLflow for efficient project management, version control, and deployment.

## Workflow Steps

To maintain and update the project efficiently, follow these steps:

1. Update `config.yaml` to modify project configurations.
2. Refresh `schema.yaml` as per the latest data schema.
3. Adjust `params.yaml` to update model parameters.
4. Revise the entity definitions as required.
5. Modify the configuration manager in `src/config` to reflect any new configurations.
6. Make necessary changes to the project components.
7. Revise the pipeline to accommodate new changes or improvements.
8. Update `main.py` with the latest project logic.
9. Revamp `app.py` to reflect the latest application functionalities.

## Execution Instructions

### Getting Started

Clone the project repository:

```bash
git clone https://github.com/entbappy/End-to-end-Machine-Learning-Project-with-MLflow
```

### Setting Up the Environment

1. **Create a Conda Environment**: After accessing the project directory, create a new Conda environment:

    ```bash
    conda create -n mlproj python=3.8 -y
    conda activate mlproj
    ```

2. **Install Dependencies**: Install the project requirements:

    ```bash
    pip install -r requirements.txt
    ```

3. **Launch the Application**: Execute the following command to start the application:

    ```bash
    python app.py
    ```

   Subsequently, access the application via your local host and designated port.

## Utilizing MLflow

For detailed documentation on MLflow, refer to [MLflow Documentation](https://mlflow.org/docs/latest/index.html).

### Commands

- Launch the MLflow UI:

    ```cmd
    mlflow ui
    ```

### Integration with DagsHub

Set up DagsHub for tracking and version control:

```bash
export MLFLOW_TRACKING_URI=https://dagshub.com/vaibhavkhuranaaa/MLFlow.mlflow
export MLFLOW_TRACKING_USERNAME=vaibhavkhuranaaa
export MLFLOW_TRACKING_PASSWORD=434a6ec1a38f52ebd3ca0435cfef94c0201b8c3d

```

## AWS CI/CD Deployment with GitHub Actions

### Initial Setup

1. **AWS Console Login**: Access your AWS management console.
2. **Create an IAM User**: Ensure the user has:
   - EC2 Access for virtual machine management.
   - ECR (Elastic Container Registry) Access to store Docker images.

### Deployment Process

1. **Build**: Construct a Docker image from the source code.
2. **Push**: Upload your Docker image to ECR.
3. **Launch**: Initiate an EC2 instance.
4. **Deploy**: Retrieve your Docker image from ECR to EC2.
5. **Run**: Launch your Docker image on the EC2 instance.

### Necessary Policies

- `AmazonEC2ContainerRegistryFullAccess`
- `AmazonEC2FullAccess`

### Additional Steps

1. **Create an ECR Repository**: Note down the URI for later use.
2. **Set Up an EC2 Instance**: Opt for Ubuntu and proceed with Docker installation.
3. **Configure EC2 as a Self-hosted Runner**: Follow GitHub's guide under repository settings.
4. **Establish GitHub Secrets**: Include AWS credentials and repository details for seamless CI/CD pipelines.

## Insights on MLflow

MLflow is a robust tool designed for the professional management of Machine Learning projects. It offers comprehensive capabilities for experiment tracking, model logging, and tagging, ensuring a streamlined path from development to deployment.

By adhering to these guidelines, you can harness the power of MLflow to elevate your Machine Learning projects, ensuring efficiency, reproducibility, and scalability.