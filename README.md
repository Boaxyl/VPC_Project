# VPC_Project

```markdown
# Step-by-Step Guide to Setting Up AWS VPC

## Step 1: Create a Virtual Private Cloud (VPC)
- Navigate to **AWS Management Console** and go to **VPC**.
- Click on **Create VPC** and choose **IPv4 CIDR block** (e.g., `10.0.0.0/16`).
- Enable **DNS hostnames** and **DNS resolution** if needed.
- Click **Create VPC**.

## Step 2: Create Subnets
- Go to **Subnets** and click **Create Subnet**.
- Select your **VPC**, define a **Subnet CIDR block** (e.g., `10.0.1.0/24` for public and `10.0.2.0/24` for private).
- Assign subnets to **Availability Zones** for redundancy.
- Click **Create Subnet**.

## Step 3: Configure Route Table
- Navigate to **Route Tables** and click **Create Route Table**.
- Associate it with your **VPC**.
- Add routes:
  - For public subnets: Route to **Internet Gateway** (`0.0.0.0/0` → `igw-xxxxxx`).
  - For private subnets: Route through **NAT Gateway** (`0.0.0.0/0` → `nat-xxxxxx`).
- Click **Save Routes**.

## Step 4: Set Up an Internet Gateway
- Go to **Internet Gateways** and click **Create Internet Gateway**.
- Attach the **Internet Gateway** to your **VPC**.
- Edit the public **Route Table** to include the Internet Gateway (`igw-xxxxxx`).

## Step 5: Configure NAT Gateway (For Private Subnet Internet Access)
- Navigate to **NAT Gateways** and click **Create NAT Gateway**.
- Select a **Public Subnet** and allocate an **Elastic IP**.
- Attach the NAT Gateway to private subnet’s **Route Table** for internet access.

## Step 6: Establish VPC Peering Connection
- Go to **VPC Peering Connections** and click **Create Peering Connection**.
- Choose **Requester VPC** and **Accepter VPC**.
- Accept the **Peering Request** from the other **VPC’s Console**.
- Update **Route Tables** to enable communication between **VPCs**.

## Step 7: Review and Validate Configuration
- Ensure **Security Groups** and **Network ACLs** allow required traffic.
- Test **connectivity** between instances in different subnets.
- Use AWS **VPC Flow Logs** to monitor network activity.

## Step 8: Deploy Applications and Optimize Resources
- Launch EC2 instances within the VPC.
- Optimize networking settings for **cost-efficiency and security**.

```



