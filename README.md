# Minimal Docker

Running experiments in trying to create as small a Docker container as possible for a Java hello world app.

The application itself is absolutely minimal to highlight the differences between the various methods of Dockerization. Note that the resulting jar file is only 2.5 kB.

| Dockerfile   | Image size | Description                                  |
| ------------ | ---------- | -------------------------------------------- |
| Dockerfile.1 | 507 MB     | Naïve: build and distribute the same image   |
| Dockerfile.2 | 397 MB     | Multi-stage: separate build and distribution |
| Dockerfile.3 | 227 MB     | Multi-stage, but with a minimal base image   |
| Dockerfile.4 | 124 MB     | JLink to reduce JRE size                     |
| Dockerfile.5 | 94.3 MB    | GraalVM native image; no JDK needed at all   |
| Dockerfile.6 | 13.4 MB    | GraalVM native image; no Linux needed either |

Credits: many of these techniques were taken from Brian Vermeer's talk at Devoxx UK 2023: [Securing Your Java Containers by Breaking In](https://www.youtube.com/watch?v=d4Xfnc-v8S8)
