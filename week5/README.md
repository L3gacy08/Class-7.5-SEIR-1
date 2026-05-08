# WEEK 5 HOMEWORK

This is my week 5 homework terraform lab

I followed the terraform IVPAD steps as stated in the assigment and followed the class recordings of the commands and the results.

# What I used

I worked with terraform and used the Git Bash terminal and worked in the folder:

~/Documents/TheOWAF/class7.5/GCP/Terraform

The commands that were used were:

- `Terraform init`
- `Terraform validate`
- `Terraform plan`
- `Terraform apply`
- `Terraform destroy`
- `date && hostname && whoami`


# The Overview 

First I ran terraform init. This set up Terraform in the folder and installed the provider plugins.
<img width="670" height="498" alt="terraform init" src="https://github.com/user-attachments/assets/d08abc46-807f-4e42-ab00-c16164fd170f" />


Then I ran terraform validate. The output said the configuration was valid, so the Terraform files did not have any syntax or configuration problems.
<img width="620" height="74" alt="terraform validate" src="https://github.com/user-attachments/assets/feecafb0-9bd5-4d2a-81cb-74f36d7568ec" />


Next I ran terraform plan. This showed what Terraform was going to create in GCP before actually making anything.
<img width="1047" height="506" alt="terraform plan" src="https://github.com/user-attachments/assets/284b3e12-abd9-4e23-875b-e4691554eacf" />


After that I ran terraform apply and typed yes to confirm. Terraform created 5 resources, including the VPC network, private subnet, enabled services, and the Grafana disk. I also checked the GCP Console and saw the main VPC with the private-subnet.
<img width="931" height="407" alt="terraform apply" src="https://github.com/user-attachments/assets/18f373c9-925f-40fb-a300-f8dd59161a7e" />

<img width="1356" height="323" alt="terraform apply - resources created" src="https://github.com/user-attachments/assets/5508c78d-2f2f-4b38-b8c7-22fd06fa4cec" />

Resources in the console:
<img width="1238" height="372" alt="terraform apply - vpc creation terraform along with subnets" src="https://github.com/user-attachments/assets/a856c247-5369-4d97-a651-76a8ea80f6ac" />


When I was done checking the resources, I ran terraform destroy and typed yes again. Terraform deleted the resources. I checked GCP after and the custom VPC was gone, so the cleanup worked.
<img width="1165" height="255" alt="terraform destroy" src="https://github.com/user-attachments/assets/c0fa918e-98b0-4234-adbd-1cc8d3419488" />

Resources destroyed in console:
<img width="1632" height="260" alt="terraform destroy - vpc destruction along with subnets" src="https://github.com/user-attachments/assets/d5711502-625a-4278-b7b1-751141e49f54" />


At the end I ran date && hostname && whoami to show the final proof from my computer.

<img width="812" height="117" alt="date and hostname and whoami" src="https://github.com/user-attachments/assets/cc1e3449-550e-4067-bbb1-6d02bc72a889" />


# Final note
The lab worked from start to finish. Terraform created the resources, I verified them in GCP, then Terraform destroyed them and I verified they were removed.
