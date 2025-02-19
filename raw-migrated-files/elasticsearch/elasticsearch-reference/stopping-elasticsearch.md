# Stopping Elasticsearch [stopping-elasticsearch]

An orderly shutdown of Elasticsearch ensures that Elasticsearch has a chance to cleanup and close outstanding resources. For example, a node that is shutdown in an orderly fashion will remove itself from the cluster, sync translogs to disk, and perform other related cleanup activities. You can help ensure an orderly shutdown by properly stopping Elasticsearch.

If you’re running Elasticsearch as a service, you can stop Elasticsearch via the service management functionality provided by your installation.

If you’re running Elasticsearch directly, you can stop Elasticsearch by sending control-C if you’re running Elasticsearch in the console, or by sending `SIGTERM` to the Elasticsearch process on a POSIX system. You can obtain the PID to send the signal to via various tools (e.g., `ps` or `jps`):

```sh
$ jps | grep Elasticsearch
14542 Elasticsearch
```

From the Elasticsearch startup logs:

```sh
[2016-07-07 12:26:18,908][INFO ][node                     ] [I8hydUG] version[5.0.0-alpha4], pid[15399], build[3f5b994/2016-06-27T16:23:46.861Z], OS[Mac OS X/10.11.5/x86_64], JVM[Oracle Corporation/Java HotSpot(TM) 64-Bit Server VM/1.8.0_92/25.92-b14]
```

Or by specifying a location to write a PID file to on startup (`-p <path>`):

```sh
$ ./bin/elasticsearch -p /tmp/elasticsearch-pid -d
$ cat /tmp/elasticsearch-pid && echo
15516
$ kill -SIGTERM 15516
```


## Stopping on Fatal Errors [fatal-errors] 

During the life of the Elasticsearch virtual machine, certain fatal errors could arise that put the virtual machine in a questionable state. Such fatal errors include out of memory errors, internal errors in virtual machine, and serious I/O errors.

When Elasticsearch detects that the virtual machine has encountered such a fatal error Elasticsearch will attempt to log the error and then will halt the virtual machine. When Elasticsearch initiates such a shutdown, it does not go through an orderly shutdown as described above. The Elasticsearch process will also return with a special status code indicating the nature of the error.

Killed by jvmkiller agent
:   158

User or kernel SIGTERM
:   143

Slain by kernel oom-killer
:   137

Segmentation fault
:   134

JVM internal error
:   128

Out of memory error
:   127

Stack overflow error
:   126

Unknown virtual machine error
:   125

Serious I/O error
:   124

Bootstrap check failure
:   78

Unknown fatal error
:   1

