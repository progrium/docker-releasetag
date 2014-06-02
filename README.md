# docker-releasetag

Prototype of how `docker tag` should work to help aid in [12Factor](http://12factor.net/) releases in the Docker world. 

A `release` in 12Factor is a `build` + `config`, where `config` is environment variables. In this case, a `build` is a Docker container image. 

## Using docker-releasetag

You can pass the environment as arguments:

	$ docker-releasetag mybuild myrelease:v1 FOO=bar BAZ=qux

Or if you have an environment file:

	FOO=bar
	BAZ=qux

Then you can pass it via STDIN using the `-` argument:

	$ docker-releasetag mybuild myrelease:v1 - < envfile

## Docker integration

My argument is that this command should be how `docker tag` should work. It would work as usual, but with the optional ability to specify an environment via arguments or file.