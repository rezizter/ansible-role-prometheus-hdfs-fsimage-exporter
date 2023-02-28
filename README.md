# Prometheus HDFS FSImage Exporter

## Description

Installs a Prometheus exporter for HDFS FSImages

## Requirements

- rgibert.single_binary_service role in roles path

## Role Variables

| Variable | Description |
|----------|-------------|
| prometheus_hdfs_fsimage_exporter_base_url | Base URL for other variables |
| prometheus_hdfs_fsimage_exporter_checksum | SHA256 URL for tarball |
| prometheus_hdfs_fsimage_exporter_dl_url | Tarball download URL |
| prometheus_hdfs_fsimage_exporter_group | Default group for the user to run as |
| prometheus_hdfs_fsimage_exporter_user | User to run the exporter as |
| prometheus_hdfs_fsimage_exporter_version | Version to install |
| prometheus_hdfs_fsimage_exporter_max_heap | Max heap allocated to the exporter |
| prometheus_hdfs_fsimage_exporter_ip | IP to listen on |
| prometheus_hdfs_fsimage_exporter_port | Port to listen on |
| prometheus_hdfs_fsimage_exporter_conf_path | Path to the config file |
| prometheus_hdfs_fsimage_exporter_conf_file | Config file |
| prometheus_hdfs_fsimage_exporter_fsimage_path | Path the HDFS fsimage |
| prometheus_hdfs_fsimage_exporter_skip_file_distrib_for_group_stats | Skip file size distribution for group based stats |
| prometheus_hdfs_fsimage_exporter_skip_file_distrib_for_user_stats | Skip file size distribution for user based stats |
| prometheus_hdfs_fsimage_exporter_paths | Paths to track stats for |
| prometheus_hdfs_fsimage_exporter_skip_file_distrib_for_path_stats | Skip file size distribution for path based stats |
| prometheus_hdfs_fsimage_exporter_path_sets | Sets for grouping paths |
| prometheus_hdfs_fsimage_exporter_skip_file_distrib_for_path_set_stats | Skip file size distribution for path set based stats |
| prometheus_hdfs_fsimage_exporter_file_size_buckets |  |


## Dependencies

- none

## Example Playbook
Create a role in your group var

```bash
vi ./inventories/group_vars/yourserverhost_legacy/prometheus.yml
```
Add the following
```yaml
---
prometheus_hdfs_fsimage_exporter_version: 1.4.6
```
Now create a playbook

```bash
vi playbooks/once_off_prometheus_hdfs_exporters.yml
```
Now add

```yaml
    - name: include role prometheus exporters
      ansible.builtin.include_role:
        name: rezizter.prometheus_hdfs_fsimage_exporter
```

## License

GPLv3

Forked from rgibert.ansible-role-prometheus-hdfs-fsimage-exporter

