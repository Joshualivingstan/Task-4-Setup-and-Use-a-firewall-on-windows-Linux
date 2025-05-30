# Task-4-Setup-and-Use-a-firewall-on-windows-Linux

🔒 Option 1: Windows Firewall

🔧 Steps:

1. Open Windows Firewall GUI:

Press Win + R, type wf.msc, press Enter.



2. List Current Firewall Rules:

In the left panel, click on Inbound Rules or Outbound Rules to view existing rules.



3. Block Inbound Traffic on Port 23 (Telnet):

In the right panel, click New Rule.

Choose Port > Click Next.

Select TCP, enter port 23 > Next.

Choose Block the connection > Next.

Select all profiles (Domain, Private, Public) > Next.

Name it Block Telnet > Finish.



4. Test the Rule:

Use Telnet or a tool like Nmap to scan/open port 23 (you should see it blocked).

Example: telnet localhost 23 → Connection should fail.



5. Allow SSH (optional on Windows):

If SSH server is running, allow port 22 using similar steps, but choose Allow the connection.



6. Remove the Block Rule:

Find the Block Telnet rule in Inbound Rules.

Right-click > Delete.



7. Documented Steps:

Use screenshots for: opening firewall, rule creation, testing connection, deleting rule.





---

🛡 Option 2: Linux (UFW)

> Ensure UFW is installed and active. Run these as root or with sudo.



🔧 Commands:

1. Enable UFW:

sudo ufw enable


2. List Current Rules:

sudo ufw status numbered


3. Block Port 23 (Telnet):

sudo ufw deny 23/tcp


4. Test the Rule:

Try: telnet localhost 23 → Should fail.

Or use: nc -zv localhost 23



5. Allow SSH (Port 22):

sudo ufw allow 22/tcp


6. Remove the Block Rule:

sudo ufw delete deny 23/tcp


7. Take Screenshot / Save Config:

sudo ufw status verbose

You can also export UFW rules:

sudo iptables-save > firewall-rules.txt




---

🧠 Firewall Summary

A firewall filters incoming and outgoing network traffic based on a set of rules.

It can block/allow traffic based on IP addresses, port numbers, or protocols.

Example: Blocking port 23 prevents Telnet connections, which reduces exposure to certain attacks.

Allowing only essential services, like SSH, reduces the attack surface.
