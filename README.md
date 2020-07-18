# Submission Judge

![Docker](https://github.com/Giantpizzahead/submission-judge/workflows/Docker/badge.svg)

A simple judge for checking the correctness of code. Designed to be used for simple competitive programming problems.

This is a personal project, and it is **still in EARLY DEVELOPMENT**. Please do not use this in its current form.

Documentation is currently lacking (will be added later... whenever i feel like it lol), but most of the function / variable names should be self-explanatory.

Hard-coding things is bad, so most of the 'hard-coded' values are configurable via environment variables! Check the variables in **env_vars.py** to figure out what they do.

Also look at the sample problems in the **problem_info** folder (check the README.txt in problem #1 as well) to figure out how problems are structured. The problem creation process will probably be abstracted into a web form at some point though.

## Usage
You'll need to manually build the docker image to use it at the moment (this will hopefully be changed later). To play around with the submission judge, first <a href="https://docs.docker.com/get-docker/">install docker</a>, then run:
```commandline
swapoff -a
```
The above command disables memory swapping on the machine, which is required for the submission judge to enforce memory limits. By default, this does not persist across reboots.

Finally, run the below command to start the Docker container (Warning: The container may temporarily change some kernel settings to make sure judging is consistent; these changes also do not persist across reboots):
```commandline
docker run -p 8080:8080 --privileged DOCKER_IMAGE_NAME
```
(Yes, it requires privileged mode. rip <a href="https://github.com/ioi/isolate">isolate</a>)

The web server listens on **port 8080**. You'll be greeted by a testing interface to mess around with.

Andddd that's it! Go get that AC! (Legends say there might even be an AC\* verdict...)

## Licensing
uhhhh idk just use it i guess?

Note: This is a personal project, so PLEASE do not use this in any official setting. There's a lot of stuff that is much better handled by other judges, like uh... basically everything. xD

&copy;Corona 2020 Giantpizzahead