# GCR Practice

## Docker 認証

```sh
% gcloud auth configure-docker
Adding credentials for all GCR repositories.
WARNING: A long list of credential helpers may cause delays running 'docker build'. We recommend passing the registry name to configure only the registry you are using.
After update, the following will be written to your Docker config file located at [/Users/USER/.docker/config.json]:
 {
  "credHelpers": {
    "gcr.io": "gcloud",
    "us.gcr.io": "gcloud",
    "eu.gcr.io": "gcloud",
    "asia.gcr.io": "gcloud",
    "staging-k8s.gcr.io": "gcloud",
    "marketplace.gcr.io": "gcloud"
  }
}

Do you want to continue (Y/n)?  Y

Docker configuration file updated.
```

## Docker Build & Push

```sh
% PROJECT_ID=YOUR-PROJECT-ID
% IMAGE=go-sample
% TAG=latest
% docker build -f Dockerfile --tag=gcr.io/$PROJECT_ID/$IMAGE/$TAG .
% docker push gcr.io/$PROJECT_ID/$IMAGE/$TAG
```

## Edit Tag

```sh
% gcloud container images add-tag gcr.io/$PROJECT_ID/$IMAGE/$TAG:$TAG gcr.io/$PROJECT_ID/$IMAGE/$TAG:v2
```
