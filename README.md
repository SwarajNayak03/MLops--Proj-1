# MLOps Project – Vehicle Insurance Data Pipeline
Welcome to the Vehicle Insurance MLOps Pipeline Project!
This project demonstrates how to manage a real-world ML pipeline—from data ingestion to model deployment—using tools like MongoDB, AWS, Docker, and GitHub Actions. Designed to highlight production-ready MLOps practices, this project is perfect for showcasing skills to recruiters or as a professional portfolio project.

# 🧱 Project Structure and Setup
✅ Step 1: Project Initialization
Run template.py to scaffold the entire project folder structure and placeholder files automatically.

✅ Step 2: Package Management
Manage local packages using setup.py and pyproject.toml.

For quick guidance, refer to crashcourse.txt.

✅ Step 3: Virtual Environment and Installation
bash
Copy
Edit
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt
pip list  # to verify installed packages
📊 MongoDB Setup and Data Management
✅ Step 4: MongoDB Atlas Configuration
Sign up at MongoDB Atlas.

Create a Free M0 cluster and a user.

Whitelist all IPs (0.0.0.0/0).

Get the Python connection string.

✅ Step 5: Pushing Data to MongoDB
Add dataset inside the notebook/ folder.

Create and run mongoDB_demo.ipynb to push data to MongoDB Atlas.

Verify the upload via Browse Collections.

📝 Logging, Exception Handling, and EDA
✅ Step 6: Logging & Exception Handling
Implement reusable modules and test them in demo.py.

✅ Step 7: EDA and Feature Engineering
Perform data analysis and transformation using Jupyter in EDA_FeatureEngg.ipynb.

📥 Data Ingestion Pipeline
✅ Step 8: Build Ingestion Module
Set up connection utilities in configuration/mongo_db_connection.py.

Implement logic in:

data_access/
components/data_ingestion.py
Define configs in:
entity/config_entity.py
entity/artifact_entity.py

🔐 Set MongoDB URL Environment Variable
For Bash:
bash
Copy
Edit
export MONGODB_URL="mongodb+srv://<username>:<password>@..."
For PowerShell:
powershell
Copy
Edit
$env:MONGODB_URL = "mongodb+srv://<username>:<password>@..."

🔍 Data Validation, Transformation, and Model Training
✅ Step 9: Data Validation
Define schema in config/schema.yaml.
Validate data using utils/main_utils.py.

✅ Step 10: Data Transformation
Implement in components/data_transformation.py.

Add estimators in entity/estimator.py.

✅ Step 11: Model Training
Develop model trainer in components/model_trainer.py.

🌐 AWS Setup for Storage & Model Evaluation
✅ Step 12: AWS Credentials
Create IAM user and set credentials:

export AWS_ACCESS_KEY_ID="..."
export AWS_SECRET_ACCESS_KEY="..."
✅ Step 13: Push Model to S3
Create an S3 bucket: my-model-mlopsproj (Region: us-east-1)

Add code in:

src/aws_storage/

entity/s3_estimator.py

🚀 Model Deployment & Prediction Pipeline
✅ Step 14: Evaluation, Pusher, and Prediction
Evaluate model and deploy using custom components.

Integrate with app.py for API serving.

✅ Step 15: Add Web UI
Add UI resources in static/ and templates/ directories.

🔄 CI/CD with Docker, GitHub Actions, and AWS
✅ Step 16: Docker & GitHub Actions
Add Dockerfile and .dockerignore.

Set up GitHub Actions and add secrets:

AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_DEFAULT_REGION

ECR_REPO

✅ Step 17: AWS EC2 & ECR Deployment
Launch EC2 instance and install Docker.

Register the EC2 instance as a self-hosted GitHub runner for auto-deployments.

📌 Key Tools & Technologies
Area	Tools/Services
Version Control	Git, GitHub
Data Storage	MongoDB Atlas
Cloud	AWS (EC2, S3, ECR)
CI/CD	GitHub Actions, Docker
Programming	Python, Jupyter
Web API	Flask (via app.py)
ML Lifecycle	Custom components/, pipeline/, entity/
