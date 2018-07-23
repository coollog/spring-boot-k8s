# Dockerize and deploy a Spring Boot application to Kubernetes

This is an example of how to easily build a Docker image for a Spring Boot application with Jib and deploy it to Kubernetes with `kubectl`.

Read more about Jib at the [official blog post](https://cloudplatform.googleblog.com/2018/07/introducing-jib-build-java-docker-images-better.html).

<!-- Dockerize and deploy a @springboot app to #Kubernetes @kubernetesio @docker #jib -->
<p align="center">
    <a href="https://twitter.com/intent/tweet?text=Dockerize%20and%20run%20a%20%22Hello%20World%22%20%40Java%20%40micronautfw%20app%20with%20%23Jib%20in%20seconds&url=https://asciinema.org/a/191805&hashtags=docker,kubernetes">
    <img src="https://github.com/coollog/micronaut-jib/blob/master/dockerize-micronaut-jib.gif?raw=true" width="600" alt="Dockerize Micronaut app with Jib">
  </a>
</p>

## Try it yourself

*Make sure you have `kubectl` [configured with a cluster](https://cloud.google.com/kubernetes-engine/docs/how-to/creating-a-cluster).*

```shell
IMAGE=<your image, eg. gcr.io/my-project/spring-boot-jib>

./mvnw compile jib:build -Dimage=$IMAGE

kubectl run spring-boot-jib --image=$IMAGE --port=8080 --restart=Never

# Wait until pod is running
kubectl port-forward spring-boot-jib 8080 > /dev/null 2>&1 &
```
```shell
curl localhost:8080
> Greetings from Kubernetes!
```

<!-- Run a @springboot app on #Kubernetes in seconds @kubernetesio #jib #java-->
Give it a [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Run%20a%20%22Hello%20World%22%20%40java%20%40micronautfw%20app%20on%20%23Kubernetes%20with%20%23Jib%20in%20seconds&url=https://github.com/coollog/micronaut-jib&hashtags=docker,kubernetes)

## More information

Learn [more about Jib](https://github.com/GoogleContainerTools/jib).
