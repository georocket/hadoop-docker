# Apache Hadoop 2.7.3 Docker image

**NOTE: THIS REPOSITORY IS BASED ON [sequenceiq/hadoop-docker](https://github.com/sequenceiq/hadoop-docker) BUT PRODUCES A MUCH SMALLER DOCKER IMAGE. WE'RE USING IT TO TEST [GeoRocket](https://georocket.io). WE CANNOT GUARANTEE THE IMAGE WILL WORK FOR ANYTHING ELSE. IF YOU WANT A FULLY FUNCTIONAL AND TESTED HADOOP DOCKER IMAGE PLEASE USE [sequenceiq/hadoop-docker](https://github.com/sequenceiq/hadoop-docker)**

# Build the image

If you'd like to try directly from the Dockerfile you can build the image as:

```
docker build  -t georocket/hadoop-docker:2.7.3 .
```

# Pull the image

The image is also released as an image from Docker's automated build repository - you can always pull or refer the image when launching containers.

```
docker pull georocket/hadoop-docker:2.7.3
```

# Start a container

In order to use the Docker image you have just build or pulled use:

**Make sure that SELinux is disabled on the host. If you are using boot2docker you don't need to do anything.**

```
docker run -it georocket/hadoop-docker:2.7.3 /etc/bootstrap.sh -bash
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
