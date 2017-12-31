# Thumbnail nginx cache server

Based on http://charlesleifer.com/blog/nginx-a-caching-thumbnailing-reverse-proxying-image-server-/


Resizes and caches images from google cloud storage.

## Example

1. Run

**TODO:** Use image from docker hub

```
docker run -p 9000:80 resize:0.1
```

3. Fetch image:

http://localhost:9000/t/200x200/<bucket-name>/<image-path>

* `200x200` are the limits this image should resized to


**TODO:**

* [ ] Enable secure links config

## Publish

Docker image is automatically built every time we push to this repo.

Link to docker hub: **TODO**
