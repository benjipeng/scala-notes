# Notes on Learning Scala

## Getting Started
Use a `docker image` to build a `container` to run the code. Visit [scala-sbt docker hub](https://hub.docker.com/r/sbtscala/scala-sbt/tags) for a list of images.

- [x] Pull the image `docker pull sbtscala/scala-sbt:eclipse-temurin-focal-11.0.17_8_1.8.2_3.2.2`
- [x] Run the image as a container `docker run --name scala3 --rm -it -v /$(pwd)/code:/root/code -w /root/code sbtscala/scala-sbt:eclipse-temurin-focal-11.0.17_8_1.8.2_3.2.2`. The`-v /$(pwd)/code:/root/code` can be any dir needed -> `{outside}`:`{inside container}`.
  
  - `--rm` Automatically remove the container when it exits.
  - `-i`, `--interactive` STDIN.
  - `--tty`, `-t` Pseudo-TTY
  - `--name` Assign a name to container.
  - `--workdir`, `-w` Set the Working Dir inside the container.
  - `--detach`, `-d` Run in background but return a container ID.
  - `-v` *does not* accept relative paths
  - `--mount` Attach a filesystem mount.

- [x] Open another session `docker exec -it scala3 bash`.
  
  - `scala` to go to a console (`:quit` to exit).
  - `scala {file-name}.scala` to run the function (def).
  
