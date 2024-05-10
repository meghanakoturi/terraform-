# main.tf #
Create a directory for your Terraform project and create a module name monitoring then Terraform configuration file named `main.tf' in that directory. In this file, you define the resource block.
This file typically contains the main configuration of your infrastructure. It declares the resources you want to create, modify, or manage using Terraform. These resources can include virtual machines, storage accounts, networks, databases, etc.
Inside main.tf, you define the provider you're using (like AWS, Azure, Google Cloud, etc.), any data sources you require (like retrieving information from existing infrastructure), and the actual resources you want to manage.

# variables.tf #
Create an other Terraform configuration file named 'variables.tf' this file is used to declare the variables that you want to accept as input for your Terraform configuration.

# outputs.tf #
Create an other Terraform configuration file named 'outputs.tf' this file is used to define the output values that you want to display after Terraform has applied your configuration. These outputs can be useful for providing information to users or other systems after the infrastructure has been provisioned or updated.
