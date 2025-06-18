# End-to-End-Waste-Detection-Yolo-V5

An end-to-end MLOps pipeline for automated waste detection and classification using YOLOv5 object detection model. This project implements best practices for machine learning operations including experiment tracking, model versioning, automated training, and deployment.
🎯 Project Overview
This system automatically detects and classifies different types of waste materials in images using computer vision. The MLOps pipeline ensures reproducible training, continuous integration, and scalable deployment for real-world waste management applications.
Key Features

Automated Waste Detection: Detects multiple waste categories (plastic, glass, metal, organic, paper, etc.)
MLOps Pipeline: Complete CI/CD pipeline with experiment tracking and model versioning
Real-time Inference: Fast inference API for real-time waste classification
Data Versioning: Automated data pipeline with validation and versioning
Model Monitoring: Performance monitoring and drift detection in production
Scalable Deployment: Containerized deployment with Dockers support

📋 Requirements
System Requirements

Python 3.8+
CUDA 11.0+ (for GPU training)
Docker 20.10+
8GB+ RAM (16GB recommended)
20GB+ storage space



# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/Durgeshsingh12712/End-to-End-Waste-Detection-Yolo-V5
```
### Setup Environment

```bash
conda create -n waste python=3.7 -y
```

```bash
conda activate waste
```


### install the requirements
```bash
pip install -r requirements.txt
```

Dataset Statistics

Total Images: 15,000+
Training Set: 12,000 images
Validation Set: 2,000 images
Test Set: 1,000+ images
Annotations: YOLO format with bounding boxes
Average Objects per Image: 3.2

📈 Experiment Tracking
Weights & Biases Integration
The project uses W&B for comprehensive experiment tracking:

Metrics: mAP, precision, recall, F1-score, training loss
Parameters: Learning rate, batch size, epochs, architecture
Artifacts: Model weights, configuration files, training plots
Visualizations: Training curves, confusion matrices, prediction samples


```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```

📊 Model Performance
Latest Model Metrics

mAP@0.5: 0.847
mAP@0.5:0.95: 0.623
Precision: 0.821
Recall: 0.786
F1-Score: 0.803
Inference Speed: 45ms (GPU), 180ms (CPU)

🔄 CI/CD Pipeline
GitHub Actions Workflow

Code Quality: Linting, formatting, security checks
Testing: Unit tests, integration tests, model validation
Training: Automated retraining on data updates
Deployment: Automated deployment to staging/production
Monitoring: Performance monitoring and alerting

Pipeline Triggers

Manual: On-demand training and deployment
Scheduled: Weekly retraining with new data
Event-driven: Triggered by data drift detection
Pull Request: Model validation on code changes

📊 Monitoring & Observability
Model Monitoring

Performance Metrics: Real-time accuracy, latency, throughput
Data Drift: Input distribution monitoring
Model Drift: Output distribution analysis
Business Metrics: Waste detection accuracy in production

Alerting

Performance Degradation: mAP drops below threshold
High Latency: Inference time exceeds SLA
Data Quality Issues: Corrupted or unexpected inputs
System Health: API downtime or resource constraints

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.
🙏 Acknowledgments

Ultralytics YOLOv5 for the object detection framework
Weights & Biases for experiment tracking and visualization
Open source waste detection datasets and research community
Contributors and maintainers of this project

📞 Support
For questions, issues, or contributions:

Issues: GitHub Issues
Discussions: GitHub Discussions
Email: Durgeshsingh12712@gmail.com

🔗 Related Projects

YOLOv5 Official Repository
Waste Detection Datasets
MLOps Best Practices

# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 566373416292.dkr.ecr.ap-south-1.amazonaws.com/waste

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal
```bash
sudo apt-get update -y

sudo apt-get upgrade
	
	#required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
```
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

```bash
    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app

```


# AZURE-CICD-Deployment-with-Github-Actions

## Save pass:

secret pass =


## Run from terminal:

docker build -t wasteDetectionapp.azurecr.io/wasteDetection:latest .

docker login wasteDetectionapp.azurecr.io

docker push wasteDetectionapp.azurecr.io/wasteDetection:latest


## Deployment Steps:

1. Build the Docker image of the Source Code
2. Push the Docker image to Container Registry
3. Launch the Web App Server in Azure 
4. Pull the Docker image from the container registry to Web App server and run