# emeraldjava-hack
Repo for hack an HHVM related experiments.

From [https://docs.hhvm.com/hhvm/getting-started/getting-started](https://docs.hhvm.com/hhvm/getting-started/getting-started) start the HHVM process

```
hhvm -m server -p 8080
```

## Run the hh_client

```
pauloconnell@pauloconnell-HP-ZBook-15 ~/projects/github/emeraldjava-hack $ hh_client
Error: could not find a .hhconfig file in /home/pauloconnell/projects/github/emeraldjava-hack or any of its parent directories. Do you have a .hhconfig in your code's root directory?
```

Add a hhconfig file
```
pauloconnell@pauloconnell-HP-ZBook-15 ~/projects/github/emeraldjava-hack $ touch .hhconfig
```

Then run the typechecker
```
pauloconnell@pauloconnell-HP-ZBook-15 ~/projects/github/emeraldjava-hack $ hh_client
[2017-07-24 09:50:03] Unix.Unix_error(Unix.ENOENT, "connect", "")
For more detailed logs, try `tail -f $(hh_client --logname)`
Server launched with the following command:
	'/usr/bin/hh_server' '-d' '/home/pauloconnell/projects/github/emeraldjava-hack' '--waiting-client' '5'
Spawned hh_server (child pid=9228)
Logs will go to /tmp/hh_server/zShomezSpauloconnellzSprojectszSgithubzSemeraldjava-hack.monitor_log
No errors!
```

## Docker

docker build .
```
docker run -p 0.0.0.0:8081:8081 [image]
docker ps
docker stop [ps]
sudo iptables -t nat -L -n
```

https://github.com/wsargent/docker-cheat-sheet#exposing-ports
https://docs.docker.com/engine/userguide/networking/default_network/binding/

To tag and push the image to docker hub run commands

```
docker tag 159ec emeraldjava/emeraldjava-hack:version1
docker push emeraldjava/emeraldjava-hack:version1
```

https://docs.docker.com/engine/reference/commandline/tag/#examples
https://docs.docker.com/docker-cloud/builds/push-images/
