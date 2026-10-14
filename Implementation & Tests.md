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

## 7. Testing and Results

| Test | Actual Result |
|------|---------------|
| Health check endpoint and status for primary instance | [Health-check-primary.png](screenshots/Health-check-primary.png) |
| Health check endpoint and status for secondary instance | [Health-check-secondary.png](screenshots/Health-check-secondary.png) |
| Primary website online | [Primary-website.png](screenshots/Primary-website.png) |
| Secondary website online | [Secondary-website.png](screenshots/Secondary-website.png) |
| DNS records configured | [Hosted-zones&records.png](screenshots/Hosted-zones%26records.png)|
| Simulated unhealthy status | [Unhealthy-status-simulated.png](screenshots/Unhealthy-status-simulated.png)|
| Primary webpage redirected to secondary | [Failover-target-successfull.png](screenshots/Failover-target-successfull.png) |
| Traffic returned to primary after recovery| [Restore-primary-web.png](screenshots/Restore-primary-web.png) |
| Traffic returned to primary after recovery | [Restore-primary-webb.png](screenshots/Restore-primary-webb.png) |
