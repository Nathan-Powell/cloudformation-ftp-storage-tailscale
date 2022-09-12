# CloudFormation Template for EFS FTP Storage over Tailscale VPN
A template to build a private EC2 instance with FTP server for access over a Tailscale VPN.
- Public instance provides access to private subnet by advertising subnet on Tailscale network.
- Private instance uses egress only internet gateway to install FTP server and NFS/EFS packages.
- VPC endpoints are used for private instance to connect to SSM, KMS & EFS.
- Tailscale auth key and FTP password are stored in SSM for aws cli access in user data.
- Private instance uses EFS to provide elastic storage for FTP server.

![AWS Diagram](/aws_tailscale_router.png?raw=true "AWS Diagram")