# nodevirtualenv

A virtualenv clone for NodeJS. Provides a flow that borrows from the convenience of both [n](https://github.com/tj/n) and [virtualenv](https://github.com/pypa/virtualenv)

#### Rationale

At [crisp](https://getcrisp.news), NodeJS powers our article content extraction services. A cause of concern during development/ deployment has been version maintenance. With containers, smaller team bandwidths meant high maintenance costs.

Currently, [n](https://github.com/tj/n) powers most of our NodeJS versioning requirements. It has been convenient for the most part since it installs a non-intrusive binary at /usr/local. The missing part with n was with a single version's use between two packages with different needs.

A virtualenv kind of solution would be an ideal solution for these cases. While [nodeenv](https://github.com/ekalinin/nodeenv) exists, the activate flow, pip install (as the primary mode) added load to picking it up.

Ergo, [nodevirtualenv](https://github.com/techiev2/node-virtualenv) comes in as an alternative.



#### Usage

In its current state, nodevirtualenv allows installation of specific NodeJS versions inside ```$HOME/.node-envs/```

>>>
	nodevirtualenv -v <version> -p <envPath>

	  -v        NodeJS version to install/use to run.
	  -p        NodeJS installation path to use.
	  -c        Script path to run with the requested version.

	  --bin     Get the path for the NodeJS binary for the version specified.
                    -v <10.9.0> / -p <test-api-env-10.9.0>
                    The -v switch looks for direct version names inside the envs path and doesn't right now look
                    inside all installed envs to filter out on version.
	  --list    List all locally installed NodeJS versions.



#### Caveat emptor

* As such, the script works only on 64-bit GNU/Linux systems and uses the corresponding binary paths from NodeJS distribution channels. Support for Windows/non-GNU/Linux systems are forthcoming.
