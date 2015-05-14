# munin-fastd-plugin
A munin plugin to monitor fastd uptime, peers and traffic

### Desciption

This plugin get's fastd status from its status socket, decode the JSON and extracts uptime, number of peers and traffic.

### Config
The plugin needs some basic configuration. You have to set user and group of a user that have access to the socket. This should be "fastd".

If the path to your socket is not /tmp/fastd.sock you have to set the path too.

#####Example
    [fastd_*]
    user fastd
    group fastd
    env.socketfile /tmp/fastd.sock

### Usage
To use this plugin, just copy it to your box (I prefer /usr/local/share/munin/plugins to seperate it from the plugins shipped with munin) and link it to /etc/munin/plugins with the type of graph (uptime, peers, traffic) prepend to the name of the link.

#####Example
    ln -s /usr/local/share/munin/plugins/fastd_ /etc/munin/plugins/fastd_uptime
    ln -s /usr/local/share/munin/plugins/fastd_ /etc/munin/plugins/fastd_peers

