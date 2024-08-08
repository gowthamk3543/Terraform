# Terraform
It is open source infrastructure as a code tool developed by Hashicorp.
It allows developers to define, manage and provision infrastructure resources in declarative manner using simple and human readable configuration languages.
With terraform u can define your entire infrastructure stack including VM storage network other cloud resources.

Benefits:
•	Consistency
•	Version control
•	Automation
•	Reduced human error

Key Features:
•	Supports multiple cloud providers
•	Declarative configuration language (HCL - HashiCorp Configuration  Language)
•	Execution plans
•	Resource graph
•	Change automation

Terraform Commands
Initialize Terraform: terraform init
Format Configuration Files: terraform fmt
Validate Configuration: terraform validate
Generate Execution Plan: terraform plan
Apply Changes: terraform apply
Destroy Resources: terraform destroy

Terraform files
•	Main.tf
•	Variable.tf
•	Provider.tf
•	Output.tf
•	Backend.tf
Provider Block: 
•	The provider block specifies the cloud or infrastructure provider you want to use. 
•	It defines the connection details and credentials required to authenticate with the provider's API.
Resource Blocks: 
•	Resource blocks define the individual infrastructure resources that Terraform will manage.
•	They represent the resources you want to create, modify, or delete. Each resource block has a unique type and a set of arguments that configure the resource.
Data Blocks: 
•	Data blocks allow you to fetch information from external sources, like existing resources or APIs, and use that data in your configuration.
Variable Blocks: 
•	Variables allow you to parameterize your Terraform configuration, making it more flexible and reusable. 
•	You can define variables in a separate .tf file or within the same configuration file.
Output Blocks: 
•	Output blocks define values that are exposed to the user after the Terraform execution.
•	They allow you to view useful information, such as IP addresses or resource IDs, that you may need after the deployment is complete.
Terraform Backend: 
•	The backend is responsible for storing the state file securely and making it available for team collaboration. 
•	Terraform supports various backends, including local file storage, Amazon S3, Azure Blob Storage, HashiCorp Consul, and more.
Terraform locally installed and configured AWS and created resources

Process:
We need to install terraform
•	URL: https://developer.hashicorp.com/terraform/install
•	Select windows (AMD64)
•	Unzip it and place in C drive (new folder: terraform)
•	Then search for edit system environment variables (settings) – select environment variables – then select PATH click edit – then click new – add path where you placed in C drive (C:\terraform)
•	Terraform is installed – check in command prompt – terraform --version

We need to install AWS CLI
•	URL: https://awscli.amazonaws.com/AWSCLIV2.msi
•	Normal installing process click next, next and it will do it.
•	AWS CLI is installed - check in command prompt – aws --version

In order to work with AWS we need to configure it for that we need access key that we get after create IAM user
•	Go to aws console – search IAM user – create user – give permissions – create 
•	We can see security credentials click – click access key – select Command Line Interface (CLI) – click next – click access key 
•	After that copy access key and access password
or 
we can add in provider.tf file

Now open Visual studio (you need to install extension terraform)
•	Create folder terraform – create new file main.tf write file to create AWS EC2 instances – save
•	Now open terminal – check terraform and AWS version
•	We need to configure aws – aws configure (provide access key & secret key) or we can add in provider.tf file
•	Now run terraform commands
- terraform init
- terraform fmt
- terraform validate
- terraform plan
- terraform apply
Now you can see in AWS console that EC2 instance is created.
If you want to delete what you have created use
- terraform destroy
