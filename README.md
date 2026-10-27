# aws-ec2-route53-dns-failover
Implementation of DNS-based failover using AWS EC2 and Amazon Route 53 to improve website availability.

<br>

## 1. Project Overview

This project implements DNS-level failover for a web application using Amazon EC2 and Amazon Route 53 health checks.
The goal is to improve website availability by redirecting DNS responses to a secondary web server when the primary server becomes unhealthy.

<br>

## 2. Problem Statement

A website hosted on a single EC2 instance has a single point of failure. If its web server stops responding, users may be unable to access the website.

<br>

## 3. Proposed Solution

Deploy two independent EC2 web servers and configure Amazon Route 53 failover routing.

<br>

## 4. Architecture

```text
Users
  |
  v
Amazon Route 53
  |
  +---- Primary EC2 / Nginx
  |
  +---- Secondary EC2 / Nginx
```

## 5. AWS Services and Technologies

- Amazon EC2
- Amazon Route 53
- Route 53 health checks
- Amazon Linux 2023
- Nginx
- HTTP and DNS
- GitHub and Markdown

<br>

## 6. Security Considerations

- Restricted SSH access to a trusted source IP.
- Exposed only required inbound web traffic.
- Did not commit private keys or AWS credentials.
- Used separate health-check endpoints to monitor HTTP availability.

<br>

## 7. References

- Route 53 failover routing:
  https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-failover.html
- Route 53 health checks:
  https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/welcome-health-checks.html
- Amazon EC2 documentation:
  https://docs.aws.amazon.com/ec2/
