# SEIR-I Lab 2 - GCP Terraform VM

For this lab I deployed a basic Google Cloud VM using Terraform. The point of the lab was to use infrastructure as code instead of making the VM manually in the GCP console. Terraform created the Compute Engine VM, the network/firewall setup, and allowed HTTP traffic on port 80.

The VM is in Iowa, which is us-central1-a. 

I put my GCP key file in the Terraform folder:


The main commands I ran were:

terraform init
<img width="676" height="354" alt="terraform init" src="https://github.com/user-attachments/assets/bef6b14d-c730-47f5-a6ef-6f91e73c8b56" />

terraform validate
<img width="610" height="59" alt="terraform validate" src="https://github.com/user-attachments/assets/929ab929-7bf2-47c6-bc13-7b1edc7166ba" />

terraform plan -out tfplan
<img width="1008" height="476" alt="terraform plan -out tfplan" src="https://github.com/user-attachments/assets/4c9642e0-3da0-49e5-a716-494becdbc384" />

terraform show tfplan > plan.txt
<img width="585" height="64" alt="terraform show plan save" src="https://github.com/user-attachments/assets/70bbee85-3663-4d6f-8fd2-2b84409582d9" />

terraform apply tfplan
<img width="1045" height="459" alt="terraform apply" src="https://github.com/user-attachments/assets/77f86ffb-9830-43eb-9f8e-f86ee79d7300" />

terraform output vm_url
<img width="550" height="151" alt="terraform outputs" src="https://github.com/user-attachments/assets/c6ea8864-8322-435f-9f38-6d39197cdc95" />


The tfplan file is the saved Terraform plan that gets applied. The plan.txt file is the readable version of the plan that I used for the homework submission.

After the apply finished, I used the VM URL from Terraform and opened it in the browser. If the output only shows the IP address, then the URL is just:

http://34.41.6.80
<img width="1289" height="685" alt="terraform vm ip http port 80 page" src="https://github.com/user-attachments/assets/d65b3382-8d90-4330-bfb7-63288ba2afac" />


Then I downloaded the gate script, and ran it from the CLI:

chmod +x gate_lab2_http.sh
VM_IP=$(terraform output -raw vm_external_ip)
VM_IP="$VM_IP" ./gate_lab2_http.sh

<img width="586" height="67" alt="lab 2 gate - pass" src="https://github.com/user-attachments/assets/8c1621c6-5e78-49b0-8728-270842f03950" />


After that I checked the gate files:

cat gate_result.json
cat badge.txt

For submission I included the Terraform files, plan.txt, proof of the apply, gate_result.json, badge.txt, and a screenshot of the web page loading from the VM URL.
