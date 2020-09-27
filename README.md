# murmurc

This is a WIP of an utility to manage Mumble (`murmurd`) servers. Currently offers a few options that I needed to make my life easier, more will come as I need them.

## what can i do with it?

You can either import it as a regular python module, or run it as a regular cli application.  
When run as a cli application, it'll start in *interactive mode*, which means that it'll try to run an `ipython` shell or a `pdb` trace as fallback.


```
welcome to murmur conf
----------------------

## Server
    mumble.get_conf(server, key)
    mumble.set_conf(server, key, value)

    mumble.server_start(server)
    mumble.server_stop(server)

    mumble.get_server(server_id)
    mumble.get_servers()
    mumble.get_all_servers()
    mumble.get_booted_servers()

    mumble.get_server_name(server)
    mumble.get_server_host(server)
    mumble.get_server_port(server)
    mumble.get_server_password(server)
    mumble.get_server_welcometext(server)
    mumble.get_server_tree(server)
    mumble.get_server_channels(server)
    mumble.get_server_uptime(server, for_humans=False)
    mumble.get_server_users(server)
    mumble.get_server_registered_users(server)

    mumble.set_server_name(server, value)
    mumble.set_server_host(server, value)
    mumble.set_server_port(server, value)
    mumble.set_server_password(server, value)
    mumble.set_server_welcometext(server, value)
    mumble.set_server_users(server, value)
    mumble.set_server_timeout(server, value)
    mumble.set_server_bandwidth(server, value)

##  User
    mumble.set_user_mute(server, user)
    mumble.set_user_unmute(server, user)
    mumble.send_user_message(server, user, msg)
    mumble.kick_user(server, user, msg)

## Channel
    mumble.add_channel(server, name, level=0)
    mumble.remove_channel(server, channel_id)
    mumble.get_channel_state(server, channel_id)
    mumble.send_channel_message(server, channel_id, msg)
```


### cli help

```
usage: murmurc [-h] [--ice-host ICE_HOST] [--ice-port ICE_PORT]
               [--ice-root ICE_ROOT] [--ice-murmur ICE_MURMUR]
               [--secret SECRET]

optional arguments:
  -h, --help            show this help message and exit
  --ice-host ICE_HOST   Ice host (eg: localhost)
  --ice-port ICE_PORT   Ice Port (eg: 6502)
  --ice-root ICE_ROOT   Ice Slices root directory (eg: /usr/share/ice/slice)
  --ice-murmur ICE_MURMUR
                        Murmur Ice File
  --secret SECRET       Also reads the environment variable MURMUR_SECRET

```

## dependencies

* mumble-server (>= 1.3.0)
* python3-zeroc-ice (>= 3.5)
* zeroc-ice-all-dev (>= 3.5)
* ipython (optional)

## license

see [LICENSE](LICENSE)

