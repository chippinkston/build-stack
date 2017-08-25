# build-stack
This project is meant to be a _reasonably_ simple containerized version of the Atlassian stack.

It exists solely as a demonstration tool to allow for showing a workflow from:
1. Requirements discussed in **Confluence**
1. Leading to tickets in **Jira**
1. Branches created from Jira in **BitBucket**
1. To workflows advancing a build via **Bamboo**

Ideally, there will be an example of the **Xray** jira plugin to demonstrate automated testing as a value add all along the way.

## Approach
Each service has a local _Dockerfile_ so that in the event there is something which needs to be rolled into the build (host entries, etc) there is an existing stub for that.

## Implementation notes
* `docker-compose.yml` variables are set in the `.env` file.
* Everything is currently targeting `localhost`.
  * The following entries need to be made in the host machines `hosts` file
    * 127.0.0.1	jira.localhost
    * 127.0.0.1	confluence.localhost
    * 127.0.0.1	bitbucket.localhost
    * 127.0.0.1	bamboo.localhost
    * 127.0.0.1	postgres.localhost