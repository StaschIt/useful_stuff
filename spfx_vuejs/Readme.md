## Introduction
This Dockerfile is for everybody who has problems to bring SharepointFramework to work with Vue.js. As the `npm install` step after Yeoman build needed python 2.7, I decided to build my own Dockerfile with Python 2.7 base.

## Worflow
- Prepare
  - Copy the Dockerfile to your system
  - Build docker image with `docker build -t your-image-name`
- Create project
  - `mkdir your-new-project`
  - `cd your-new-project` 
  - `docker run --net=host -it --rm -v ${PWD}:/usr/app/spfx your-image-name`
  - `yo @pnp/spfx`
- Run project
  - `gulp serve`

## Notes:
- For me it was the easiest way to run the docker container with `--net=host`, as port forwarding did not bring the WebPart to the test workbench. Please let me know if there is a better way to run the container
