While Home Assistant does provide built-in services for creating backups, these are not documented and do not provide a way to automatically remove them, this custom component aims to fix that.

**Note: Requires [Hass.io](https://www.home-assistant.io/hassio) to Create Snapshots.**

## Features
* `keep_days` parameter to automatically remove backups.
* `keep_days` can be set individually for each service call.
* Provides Documented Backup Services (Partial, Full snapshots).
* Support for Generational Backup Schemes.
* Backup to an alternative directory (for example a usb drive).
* Allows use of addon names instead of slugs.
* Allows friendly folder names.
* Adds a sensor to monitor the status of your backups.

## Services
* **auto_backup.snapshot_full**
* **auto_backup.snapshot_partial**
* **auto_backup.purge**

For more information and examples check the [full documentation](https://github.com/jcwillox/ha-auto-backup).

## Events
* **auto_backup.snapshot_successful**
* **auto_backup.snapshot_failed**
* **auto_backup.purged_snapshots**

## Configuration

Just add `auto_backup` to your home assistant configuration.yaml file.

```yaml
# Example configuration.yaml entry
auto_backup:
  auto_purge: true
```

### Configuration Variables

- **auto_purge** _(boolean) (Optional)_
  - _Default value:_ `true`
  - This option will automatically purge any expired snapshots when creating a new snapshot.

- **backup_timeout** _(integer) (seconds) (Optional)_
  - _Default value:_ `1200` (20 min)
  - You can increase this value if you get timeout errors when creating a snapshot. This can happen with very large snapshots.