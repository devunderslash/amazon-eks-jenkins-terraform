# Continuous Intergration on Amazon EKS
<br />

## Prerequisites
To implement the instructions in this post, you will need the following accounts:

* An AWS account – [how to create a new AWS account](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/)
* A Docker hub account – [how to register for docker id](https://success.docker.com/article/how-do-you-register-for-a-docker-id)
* A GitHub account – [sign up for a new GitHub account](https://help.github.com/en/github/getting-started-with-github/signing-up-for-a-new-github-account)

<br />

## Updates
* Update the Keyname in terraform.tfvars to match the one you created on AWS EC2
* Update Region and AMI (terraform.tfvars) depending on where you want to host your pipeline
* For the docker section of your pipeline to work you will need to add the Docker Pipeline plugin in Jenkins also

<br />

## Architecture

<img width="1042" alt="architecture-screenshot" src="images/Architecture.png">

<br />


## Sample Application [![Build Status](https://travis-ci.org/spring-projects/spring-petclinic.png?branch=master)](https://travis-ci.org/spring-projects/spring-petclinic/)

### Understanding the Spring Petclinic application with a few diagrams


### Running petclinic locally
Petclinic is a [Spring Boot](https://spring.io/guides/gs/spring-boot) application built using [Maven](https://spring.io/guides/gs/maven/). You can build a jar file and run it from the command line:


```
git clone https://github.com/aws-samples/amazon-eks-jenkins-terraform
cd amazon-eks-jenkins-terraform
./mvnw package
java -jar target/*.jar
```

You can then access petclinic here: http://localhost:8080/

<img width="1042" alt="petclinic-screenshot" src="https://cloud.githubusercontent.com/assets/838318/19727082/2aee6d6c-9b8e-11e6-81fe-e889a5ddfded.png">

Or you can run it from Maven directly using the Spring Boot Maven plugin. If you do this it will pick up changes that you make in the project immediately (changes to Java source files require a compile as well - most people use an IDE for this):

```
./mvnw spring-boot:run
```


### TODO
Add SSH key pair creation to main.tf - https://registry.terraform.io/modules/terraform-aws-modules/key-pair/aws/latest - Done


### Tutorial Link - https://aws.amazon.com/blogs/opensource/continuous-integration-using-jenkins-and-hashicorp-terraform-on-amazon-eks/