# Apache Hadoop 2.7.3 Docker image


_Note: this is the master branch - for a particular Hadoop version always check the related branch_


This image is a fork of sequenceiq/hadoop-docker with JDK 1.8 support

# Build the image

If you'd like to try directly from the Dockerfile you can build the image as:

```
docker build  -t fluddeni/hadoop-docker:2.7.3 .
```
# Pull the image

The image is also released as an official Docker image from Docker's automated build repository - you can always pull or refer the image when launching containers.

```
docker pull fluddeni/hadoop-docker:2.7.3
```

# Start a container

In order to use the Docker image you have just build or pulled use:

**Make sure that SELinux is disabled on the host. If you are using boot2docker you don't need to do anything.**

```
docker run -it fluddeni/hadoop-docker:2.7.3 /etc/bootstrap.sh -bash
```

## Testing

You can run one of the stock examples:

```
cd $HADOOP_PREFIX
# run the mapreduce
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.3.jar grep input output 'dfs[a-z.]+'

# check the output
bin/hdfs dfs -cat output/*
```

## Automate everything

As we have mentioned previousely, a Docker file was created and released in the official [Docker repository](https://registry.hub.docker.com/u/fluddeni/hadoop-docker/)
