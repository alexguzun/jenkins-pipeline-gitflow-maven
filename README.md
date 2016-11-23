# jenkins-pipeline-gitflow-maven
This is a sample Maven project with a Jenkinsfile for doing [gitflow](http://nvie.com/posts/a-successful-git-branching-model/) based release management.

The [Jenkinsfile](https://jenkins.io/doc/book/pipeline/jenkinsfile/) is used by Jenkins to build a pipeline with the described steps. 
Actual gitflow release management is performed by [jgitflow-maven-plugin](https://bitbucket.org/atlassian/jgit-flow) maven plugin.

## Jenkins job
In order to fully use the gitflow for a project, it is better to create a [Multibranch Pipeline](https://jenkins.io/blog/2015/12/03/pipeline-as-code-with-multibranch-workflows-in-jenkins/) job. 
For each branch, Jenkins will create a separate pipeline from the Jenkinsfile, available in the branch.
Note that I was able to have avoid multiple problems with flow by specifying the _Wipe out repository & force clone_ additional behaviour for the job. 