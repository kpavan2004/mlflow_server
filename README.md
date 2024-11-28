# Mlflow

Mlflow is used for the Capstone project for experiment tracking and register best models.

In MLflow, the backend store URI and artifact destination are critical configurations for the tracking server. Here's a brief explanation and examples of how to set them up:

## Backend Store URI
The backend store is where MLflow stores metadata such as experiment details, run data, metrics, and parameters.

Configuration: --backend-store-uri
Common values:
1. SQLite: sqlite:///path/to/database.db
2. MySQL/PostgreSQL: mysql+pymysql://user:password@hostname/database
3. File-based store: file:/path/to/local/folder

## Artifact Destination
The artifact destination is where MLflow stores artifacts such as models, logs, and other files generated during experiments.

Configuration: --default-artifact-root
Common values:
1. Amazon S3: s3://bucket-name/artifact-path/
2. Google Cloud Storage: gs://bucket-name/artifact-path/
3. Local filesystem: file:/path/to/artifacts

- **Example:
  ```bash
  mlflow ui --host 0.0.0.0 --port 5000 --backend-store-uri sqlite:///mlflow.db --artifacts-destination s3://<bucket>/<folder>/
  ```
  
## Note
The parameters required to connect to backend store DB and Artefacts destination should be provided while launching the mlflow. For example for S3 AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY and AWS_DEFAULT_REGION should be passed.

