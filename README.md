### What it does
This is repository of demo node app for codebuild to docker image and register to an AWS ECR.

### Things i learned
- AWS CodeBuild
- AWS CodePipeline
- ECS Fargate
- ECS Cluster and Task Definition
- ALB and Target Groups
- Docker Image Building

### How to run?

CICD Pipeline using AWS CodePipeline from Github to ECS Tasks with load balancing across containers.
- Create a cluster
- Create a task definition
- To add container (port 8080) you should give image path of ECR, that push and pull and to deploy to ecs cluster.
- Make a repository and use uri in adding container while creating task definition
- To balance between task: Create ALB and load balancer will listen to port 80 . Use port 8080 and IP’s in Target Group because docker container will expose that.
- Create a service in cluster, and select your load balancer and the vpc to operate. Listen to 8080 via custom http in security group.
- CICD Pipeline : Now setup cicd, create codebuild project, which will pull from github and build using buildspec.yml a docker image and push to ecr.
- Give permission to service role for Amazonec2ContainerRegistryFullAccess.
- Create a codepipeline, enable github webhooks.
