# Thumbnail nginx cache server

Based on http://charlesleifer.com/blog/nginx-a-caching-thumbnailing-reverse-proxying-image-server-/


Resizes and caches images from google cloud storage.

## Example

1. Run

```
docker run -p 9000:80 selaamo/thumbnails
```

3. Fetch image:

http://localhost:9000/t/200x200/[bucket-name]/[image-path]

* `200x200` are the limits this image should resized to


**TODO:**

* [ ] Enable secure links config

## Publish

Docker image is automatically built every time we push to this repo.

Link to docker hub: https://hub.docker.com/r/selaamo/thumbnails/

## GCP setup

1. Create cluster

```
gcloud container clusters create [CLUSTER-NAME]
```

1. Setup kubectl

```
gcloud container clusters get-credentials [CLUSTER-NAME]
```

1. Create static IP address

```
gcloud compute addresses create thumbnails-ip --global
```

1. Apply k8s resources

```
kubectl apply -f manifests/deployment.yaml
kubectl apply -f manifests/service.yaml
kubectl apply -f manifests/ingress.yaml
```
