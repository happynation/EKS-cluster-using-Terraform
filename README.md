# EKS cluster using Terraform
![Ansible](/images/amazoneks.jpg)

___

 ### What is EKS?

The Amazon Elastic Kubernetes Service (EKS) is the AWS service for deploying, managing, and scaling containerized applications with Kubernetes.

___

 ### Prerequisites
 For this guide, you will need:

- an AWS account with the IAM permissions listed on the EKS module documentation, (https://github.com/terraform-aws-modules/terraform-aws-eks/blob/master/docs/iam-permissions.md)
- a configured AWS CLI (https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-mac.html)
- AWS IAM Authenticator (https://docs.aws.amazon.com/eks/latest/userguide/install-aws-iam-authenticator.html)
- kubectl (https://kubernetes.io/docs/tasks/tools/install-kubectl/)

### Set up and initialize your Terraform workspace
In your terminal, clone the following repository. Once you have cloned the repository, initialize your Terraform workspace, which will download and configure the providers.
In your initialized directory, run terraform apply and review the planned actions. Your terminal output should indicate the plan is running and what resources will be created.
Now that you've provisioned your EKS cluster, you need to configure .kubeconfig
```
terraform output kubeconfig > ~/.kube/config
```
To verify that your cluster is configured correctly and running, run 
```
kubectl get all --all-namespaces
```