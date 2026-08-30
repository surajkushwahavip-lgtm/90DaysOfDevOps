# #Day 15 – Networking Concepts: DNS, IP, Subnets & Ports
Task
Today I learned some important networking concepts that are useful in DevOps.
I focused on DNS, IP addresses, CIDR/subnetting and ports.

# 1. DNS – How Names Become IPs
   
When we enter google.com in a browser, the system first needs to find the IP address of that domain.
DNS resolves the domain name to an IP address. After getting the IP, the browser connects to the server and sends the request.
DNS Records
	• A → Maps a domain to an IPv4 address.
	• AAAA → Maps a domain to an IPv6 address.
	• CNAME → Points one domain name to another domain name.
	• MX → Defines mail servers for a domain.
	• NS → Specifies the authoritative name servers for a domain.

DNS Check
# Command:
dig google.com
I used dig to check the DNS records.
Example:
A Record: <IP_ADDRESS>
TTL: <TTL_VALUE>

# 3. IP Addressing
An IPv4 address is made up of 4 numbers separated by dots.
Example:
192.168.1.10
Each part can range from 0 to 255.
Public vs Private IP
	• Public IP → Used to communicate over the internet. Example: 8.8.8.8
	• Private IP → Used inside private networks. Example: 192.168.1.10

# Private IP Ranges
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
Check IPs
ip addr show
The IP addresses from my local network were private IP addresses.

# 4. CIDR & Subnetting
CIDR tells us how many bits are used for the network portion of an IP address.
For example:
192.168.1.0/24
/24 means the first 24 bits are used for the network.
CIDR Table
CIDR	Subnet Mask	Total IPs	Usable Hosts
/24	255.255.255.0	256	254
/16	255.255.0.0	65,536	65,534
/28	255.255.255.240	16	14

# Why do we subnet?
Subnetting helps divide a large network into smaller networks.
It helps with better IP management, network organization and controlling traffic between different network sections.

# 5. Ports – The Doors to Services
A port identifies a specific service running on a machine.
For example, a web server can listen on port 80 or 443, while SSH normally uses port 22.
# Common Ports

Port	Service
22	SSH
80	HTTP
443	HTTPS
53	DNS
3306	MySQL
6379	Redis
27017	MongoDB
Check Listening Ports
ss -tulpn
I used this command to check which services were listening on my machine.
Example:
22  → SSH
80  → HTTP


# 6. Putting It Together
curl http://myapp.com:8080
Here DNS can resolve myapp.com to an IP address.
Then the connection is made to port 8080 and the HTTP request is sent to the application.
Database Connection Problem
If my application cannot reach:
10.0.1.50:3306
I would first check whether the database server is reachable and whether port 3306 is open.
ping 10.0.1.50
nc -zv 10.0.1.50 3306
I would also check the database service and firewall rules.


# What I Learned

  1. DNS helps convert domain names into IP addresses.
	
  2. CIDR and subnetting help divide and manage networks.
	
  3. Ports are used to identify different services running on a machine.

# #90DaysOfDevOps
# #DevOpsKaJosh 
# #TrainWithShubham

