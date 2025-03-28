# gdmount

## Rationale

- Saving various project files only to one shared place (Google drive) but have them mounted ubder local filesystem.
- In particular be able to save downloaded files directly to the shared drive in the system "Save as" dialog.
- Mount / unmount automaticaly depending on the available connection, only allow for specified stable WIFI networks.
  Otherwise the lagging filesystems could lead to hanging of various applications.
  
## Usage

```
./gdrive_mount.sh {setup|mount|unmount|check|clean} [config_file]
```

`setup <config_file>` : interactive setup of new mount point


## Solution
- based on rclone
- use 'iwgetid' to get SSID of the actuall WIFI network and compare it to allowed networks for mount
- user space `$HOME/.config/systemd/user` systemd config is setup for periodic network checks
