# Squid Forward Proxy Home Lab

## Overview

This project implements a Squid forward proxy in a virtualized home lab using Oracle VirtualBox, Ubuntu Server, and Kali Linux.

The goal is to understand how a forward proxy handles web requests, enforces access-control policies, authenticates users, and records proxy activity.

## Lab Architecture

- **Virtualization:** Oracle VirtualBox
- **Proxy server:** Ubuntu Server
- **Client:** Kali Linux
- **Proxy service:** Squid
- **Proxy port:** TCP 3128
- **Lab subnet:** `192.168.10.0/24`

### Network Traffic Flow

`Kali Linux → Squid Proxy → Internet → Destination Website`

## Features Implemented

- Squid installation and configuration
- Client subnet access control using ACLs
- Website blocking for Facebook and YouTube
- Domain allowlisting
- Basic proxy authentication using `basic_ncsa_auth`
- Username and password management using `htpasswd`
- SSH local port forwarding to protect proxy credentials in transit
- HTTP and HTTPS proxy testing
- Configuration validation and service management
- Access-log and service-log monitoring

## Testing

The lab uses `curl` to test proxy behavior:

- Access to permitted websites
- Blocking of restricted domains with HTTP 403
- Authentication challenges with HTTP 407
- Rejection of invalid credentials
- Successful requests with valid credentials
- Monitoring requests in the Squid access log

## Security Considerations

Basic proxy authentication does not encrypt credentials by itself. The lab uses SSH local port forwarding to protect the client-to-proxy connection.

The SSH tunnel does not encrypt traffic between the proxy server and the destination website beyond the protection already provided by HTTPS.

This is a learning environment, not a production-ready security architecture.

## Documentation

Read the complete technical report:

[[Squid proxy.pdf]]

## Learning Outcomes

This project provides hands-on experience with forward proxies, network access control, authentication, SSH tunneling, HTTP/HTTPS proxying, and log analysis.

## Disclaimer

This project is intended for educational purposes in an authorized lab environment.
