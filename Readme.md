### Docker & Java

This repo contains demo materials for:
+ Tips minimize java containers images
+ Tricks for fast startup java apps running in containrs
+ gotchas and issues while running java apps in containers and the improvements that has been made

The repo is splitte into multiple branchs, each contains a specific topic. The `Dockerfile`s uses the generated jar after running the build (`mvn clean package`). The build step could be integrated in the provided `Dockerfile`s, but it would slow the demoing the intetntion of this repo, so I kept it outside. Below branch details:
+ `master`: simple netty app, running in a container