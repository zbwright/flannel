# Troubleshooting flannel

## Firewalls
When using `udp` backend, flannel uses UDP port 8285 for sending encapsulated packets.
When using `vxlan` backend, kernel uses UDP port 8472 for sending encapsulated packets.
Make sure that your firewall rules allow this traffic for all hosts participating in the overlay network.

## Poor performance

** Dataplane - latency, limited bandwidth
*** Backend selection
*** MTU - make sure containers are using the right value

Flannel writes an MTU setting to the env file. That is read by either the Docker daemon or the CNI flannel plugin. Potentially we could instruct people to run ifconfig |grep mtu or seomthing in their containers to make sure it's all being configured properly.

** Daemon - memory/CPU

## Strange log messages

## Subnet reservations
** Lost leases
*** Clock issues
** Cannot allocate a lease
*** net/subnet config
