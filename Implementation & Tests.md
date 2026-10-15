## 1. Implementation Steps

1. Launched two EC2 instances & Configured security groups for HTTP and restricted administrative access.
3. Installed and configured Nginx on both instances.  
4. created Healthcheck endpoints on both instances.
5. Created separate primary and secondary website pages.
6. Created a public Route 53 hosted zone & updated NS for the domain.
7. Configured HTTP health checks for both servers.
8. Created primary and secondary A records with failover routing.
9. Disabled nginx web server on Primary EC2 instance
10. Primary health check shows unhealthy and & webpage redirects to secondary server 's public IP.
11. Enabled Nginx on primary instance
12. Primary health check shows healthy again and primary web page is back online.

<br>
<br>


## 7. Testing and Results

| Test | Description | Result |
|------|-------------|--------|
|  1 | Created the health check endpoint and checked its status for the primary instance to confirm it was responding correctly and reported as healthy | [Health-check-primary.png](screenshots/Health-check-primary.png) |
|  2 | Created the health check endpoint and checked its status for the secondary instance to confirm it was also responding correctly and ready to take over traffic | [Health-check-secondary.png](screenshots/Health-check-secondary.png) |
|  3 | Verified that the primary website was online and accessible through the browser, serving content as expected | [Primary-website.png](screenshots/Primary-website.png) |
|  4 | Verified that the secondary website was online and accessible through the browser, serving content as expected | [Secondary-website.png](screenshots/Secondary-website.png) |
|  5 | Reviewed the hosted zone and confirmed that the DNS records were configured correctly for the primary and secondary routing setup | [Hosted-zones&records.png](screenshots/Hosted-zones%26records.png) |
|  6 | Simulated an unhealthy status on the primary instance so that the health check would fail and trigger the failover process | [Unhealthy-status-simulated.png](screenshots/Unhealthy-status-simulated.png) |
|  7 | Confirmed that failover worked, with the primary webpage request being redirected to the secondary website after the primary was marked unhealthy | [Failover-target-successfull.png](screenshots/Failover-target-successfull.png) |
|  8 | Restored the primary instance and verified that traffic returned to the primary website after recovery | [Restore-primary-web.png](screenshots/Restore-primary-web.png) |
|  9 | Verified once more that traffic was being served from the primary website after recovery, confirming the failback was stable | [Restore-primary-webb.png](screenshots/Restore-primary-webb.png) |

<br>
<br>
<br>
CONCLUSION


This project solves the problem of website downtime caused by server failures by implementing high availability and automatic DNS failover using AWS EC2, Route 53, and health checks. In real-world scenarios, such as e-commerce websites, banking portals, and business applications, this solution helps maintain website availability by redirecting users to a secondary server when the primary server becomes unhealthy and routing traffic back after recovery. This reduces service disruption, improves reliability, and provides a better user experience.
