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
| Health check endpoint and status for primary instance | [Record result] |
| Health check endpoint and status for secondary instance | [Record result] |
| Primary website online | [Record result] |
| Secondary website online | [Record result] |
| DNS records configured | [Record result] |
| Simulated unhealthy status | [Record measured time] |
| Primary webpage redirected to secondary | [Record result] |
| Traffic returned to primary after recovery| [Record result] |
| Traffic returned to primary after recovery | [Record result] |
