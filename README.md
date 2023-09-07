Welcome to the Caddy Reverse Proxy.
The purpose of this project is to take in all web traffic on a server, and
depending on the domain of the traffic, route it to other dockerized projects
running on the server.

# Requirements
- Docker Compose

# Setting up the droplet
- Use Ubuntu
- Update the Ubuntu packages
- Create a non-root user
- Enable ssh access to the droplet as that user
- Set up github access between the droplet and caddy repo
- Ensure password access to the droplet is disabled
- Use UFW to disabled all ports other than 80, 443, and 22
- Ensure docker compose is installed, and your user has permission to use it


// What is the the deal?
// We are going to spin up the caddy reverse proxy and the projects in docker
// compose. Ports 443 and 80 will go to caddy. Caddy will read the domain and
// forward the traffic to the ports that the projects are bound to.

// Levi told me there is a caddy variable or shorthand for referencing the local
// ip. The best option he suggested though would be to have all the projects and
// the caddy reverse proxy running in the same docker network. This would be 
// more secure, as it would mean the databases aren't exposed to the whole server.
// He said that this may not work, as the projects may have mysql containers 
// identical names.
