
# Build the image.
```
docker build -t flask_demo .

```
Run your container using the `docker run ` command and specify the name of the image you just created:

```
docker run -dp 127.0.0.1:9000:9000 flask_demo
```
Run the following `docker ps` command in a terminal to list your containers.
```
docker ps
```
Use the `docker stop` command to stop the container. Replace `<the-container-id>` with the ID from `docker ps`.
```
docker stop <the-container-id>
```
Once the container has stopped, you can remove it by using the ` docker rm` command.
```
docker rm <the-container-id>
```
Use the `docker tag` command to give the `flask_demo` image a new name. Replace `YOUR-USER-NAME` with your Docker ID.

```
 docker tag getting-started YOUR-USER-NAME/getting-started
```
Run the `docker push` command . If you're copying the value from Docker Hub, you can drop the` tagname` part, as you didn't add a tag to the image name. If you don't specify a tag, Docker uses a tag called `latest`.
```
 docker push YOUR-USER-NAME/flask_demo
```
