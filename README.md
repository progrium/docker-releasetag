# docker-releasetag

Prototype of how `docker tag` should work to help aid in [12Factor](http://12factor.net/) releases in the Docker world. 

A [release in 12Factor](http://12factor.net/build-release-run) is a "build" + "config", where "config" is environment variables. In this case, a "build" is a Docker container image. 

## Using docker-releasetag

It works roughly as `docker tag`, but you can pass the environment as arguments:

	$ docker-releasetag mybuild myrelease:v1 FOO=bar BAZ=qux

Or if you have an environment file:

	FOO=bar
	BAZ=qux

Then you can pass it via STDIN using the `-` argument:

	$ docker-releasetag mybuild myrelease:v1 - < envfile
