# workspace-server
Running a CSIRO Workspace Server in docker container

This is a script to generate a docker image for Workspace (https://research.csiro.au/workspace/).
By default the image will start a workspace-server listening on port 42151, allowing schedule workflows onto it.

## How to use
1. `./build.sh` command line to build the image: workspace-server
2. `./run.sh` command line to run a container of the image
3. Add a workspace server entry in workspace-gui
    1. The host is the host which runs the container, for docker-machine, you may get its IP address with `docker-machine ip <name>`
    2. Port should be 42151
    3. Change the `Authentication Provider` to None in `Configure` of the entry.
4. Use CountedLoop operation with parallel ticked or ScheduleWorkflow operation with the host name specified to schedule workflows onto the instance.

