# travis-docker

[![](http://badge-imagelayers.iron.io/antonmry/travis-docker:latest.svg)](http://imagelayers.iron.io/?images=antonmry/travis-docker:latest 'Get your own badge on imagelayers.iron.io')

Docker container for [travis ci client](http://blog.travis-ci.com/2013-01-14-new-client/) following 
[installation instructions](https://github.com/travis-ci/travis.rb#installation), using Ruby.

It's my own fork from https://github.com/andredumas/docker-travis-ci-cli

```
docker pull antonmry/travis-docker
```

## Usage

```
docker run --rm -v $PWD:/repo -v ~/.travis:/travis antonmry/travis-docker [command]
```

```
$ docker run --rm -v $PWD:/repo -v ~/.travis:/travis antonmry/travis-docker -v
1.8.2
```

### Detailed Example

```
$ alias travis='docker run --rm -v $PWD:/repo -v ~/.travis:/travis antonmry/travis-docker' 
$ travis whoami
not logged in, please run travis login
$ travis login --github-token <public_repo personal access token>
$ travis whoami
andredumas
$ travis setup releases
# Follow on screen instructions
```
