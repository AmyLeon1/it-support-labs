## DNS Troubleshooting Lab

In this lab, I simulated a common IT support issue where a user has network connectivity but cannot access domain resources due to a DNS misconfiguration.

---

### Breaking the Configuration

On the Windows 11 client, I manually changed the DNS server to an incorrect value.

This caused domain-related services to fail while basic network connectivity still worked.

![Wrong DNS](screenshots/wrong-dns.png)

---

### Testing the Issue

I tested connectivity to the server using:

ping <Server-IP>

The ping was successful, confirming that the network connection was working.

![Ping Success](screenshots/ping-server-success.png)

However, when testing DNS resolution using:

nslookup corp.local

The request failed, indicating that DNS was not resolving correctly.

![NSLookup Fail](screenshots/nslookup-fail.png)

---

### Fixing the Issue

I corrected the DNS settings by setting the preferred DNS server to the domain controller's IP address.

![Fixed DNS](screenshots/fixed-dns.png)

---

### Verifying the Fix

After updating the DNS settings, I tested again using:

nslookup corp.local

This time, the domain resolved successfully, confirming the issue was fixed.

![DNS Fixed](screenshots/dns-fixed.png)

---

### What I learned

- DNS is critical for Active Directory and domain services  
- A system can have network connectivity but still fail to access domain resources  
- `ping` tests connectivity, while `nslookup` tests DNS resolution  
- Misconfigured DNS is a common cause of login and resource access issues  
- Step-by-step troubleshooting helps isolate the root cause  

This lab helped me understand how to diagnose and resolve real-world network issues in a domain environment.
