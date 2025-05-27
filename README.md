# Deploy Machine Learning Pipeline on Google Kubernetes Engine


- Build a Docker image and upload it on Google Container Registry (GCR).
```
docker build -t gcr.io/${PROJECT_ID}/insurance-app:v1 .

```

```
gcloud auth configure-docker gcr.io
```

```
docker push gcr.io/${PROJECT_ID}/insurance-app:v1
```

```
gcloud config set compute/zone us-central1
```

```
gcloud container clusters create insurance-cluster --num-nodes=1
```

- Create clusters(Kubernetes) and deploy machine learning pipeline with Flask app as a web service.

```
kubectl create deployment insurance-app --image=gcr.io/${PROJECT_ID}/insurance-app:v1
```

- See a web app in action that uses a trained machine learning pipeline to predict on new data points in real-time.


