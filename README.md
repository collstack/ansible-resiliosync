# Ansible rslsync

Install and manage a rslsync server on Linux.

* download rslsync
* install it on /usr/local
* create init service
* manage the config file with shared folders

# Role Variables

**rslsync_port**: Optional. Specify port to run on. Defaults to a random port at startup.

**rslsync_upnp**: Optional. Whether or not to use uPNP. True by default

**rslsync_user**: Required. The user who run the rslsync daemon.

**rslsync_webui.listen**: Optional. The ip to listen. Default 0.0.0.0.

**rslsync_webui.user**: Required. The username used to protect the webui

**rslsync_webui.password**: Required. The password used to protect the webui

**rslsync_webui.api_key**: Optional. The api key to use the rslsync API (http://www.bittorrent.com/sync/developers/api)

**rslsync_shared_folders**: Optional. An array of shared folders

**rslsync_shared_folders.0.path**: The path where the files will be synced

**rslsync_shared_folders.0.key**: The private key for the shared folder

# Example

```yaml
  roles:
    - role: rslsync
      rslsync_user: thelocaluser
      rslsync_webui:
        user: admin
        password: admin
        api_key: api_key
      rslsync_shared_folders:
        - path: /path/to/shared/folder
          key: PRIVATEKEY
        - add more
```

# Dependencies

None

# License

(c) 2014 François de Metz

BSD
