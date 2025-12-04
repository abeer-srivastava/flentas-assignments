````
# AWS Assessment – Question 1  
## Networking & Subnetting (AWS VPC Setup)

This assignment implements a basic AWS network architecture using one VPC, two public subnets, two private subnets, an Internet Gateway (IGW), a NAT Gateway, and public/private route tables. All resources are configured exactly as per requirements.

---

## 📌 1. Brief Explanation (Approach & Design)

I created a VPC with CIDR `10.0.0.0/16`, which provides a large address space suitable for subnetting.  
Then, I divided it into four `/24` subnets:

- **Two public subnets** (10.0.1.0/24, 10.0.2.0/24) for internet-facing components  
- **Two private subnets** (10.0.3.0/24, 10.0.4.0/24) for internal services  

An Internet Gateway was attached for public subnets, and a NAT Gateway in Public Subnet 1 enables private subnets to access the internet securely.  
Separate route tables were configured for public and private networks to control routing behavior.

---

## 📌 2. AWS Screenshots

### 🔹 VPC
![VPC Screenshot](screenshots/image.png)

### 🔹 Subnets
![Subnets](screenshots/image3.png)

### 🔹 Internet Gateway
![IGW](screenshots/image4.png)

### 🔹 NAT Gateway
![NAT](screenshots/image5.png)

### 🔹 Route Tables
#### Public Route Table
![Public Route Table](screenshots/public-rt.png)

#### Private Route Table
![Private Route Table](screenshots/private-rt.png)

> Replace each file path under `screenshots/` with your actual screenshot file names.

---

## 📌 3. Terraform Code

The Terraform file used to deploy the entire setup is included here:  
➡️ **`question1_vpc_setup/main.tf`**

This file contains:

✔ VPC  
✔ Public Subnets  
✔ Private Subnets  
✔ Internet Gateway  
✔ NAT Gateway  
✔ Route Tables  
✔ Associations  

All resource names match the AWS console:  
`my-vpc`, `my-subnet-1`, `my-private-subnet-1`, `my-nat-gw`, etc.

---

## 📌 4. CIDR Block Justification

| Component | CIDR Range | Reason |
|----------|------------|--------|
| **VPC** | `10.0.0.0/16` | Large private IP range with easy subnetting |
| **Public Subnet 1** | `10.0.1.0/24` | `/24` provides 256 IPs, isolated public tier |
| **Public Subnet 2** | `10.0.2.0/24` | High availability across AZs |
| **Private Subnet 1** | `10.0.3.0/24` | Internal workloads, no public exposure |
| **Private Subnet 2** | `10.0.4.0/24` | Redundancy for internal services |

This structure follows AWS best practices:  
- Public subnets for internet-facing resources  
- Private subnets for application/database layers  
- NAT Gateway for secure outbound access  

---

## 📌 5. How to Use the Terraform Code

### **Initialize Terraform**
```bash
terraform init
````

### **Preview Changes**

```bash
terraform plan
```

### **Apply Infrastructure**

```bash
terraform apply
```

To destroy resources after submission (as required):

```bash
terraform destroy
```

---

## 📁 Folder Structure

```
Abeer_Srivastava_AWS_Assessment/
│
├── question1_vpc_setup/
│   ├── main.tf
│   └── screenshots/
│        ├── vpc.png
│        ├── subnets.png
│        ├── igw.png
│        ├── nat.png
│        ├── public-rt.png
│        └── private-rt.png
│
└── README.md
```

---

## ✅ Assignment Completed

Your VPC, Subnets, IGW, NAT Gateway, Route Tables, and Terraform Code are fully configured and documented.

```

---

# 🎉 Your README is ready!

Now you only need to:

1. Create a **screenshots folder** inside your repo  
2. Upload all screenshot PNGs  
3. Update the image paths in README.md  
4. Commit + Push

---

