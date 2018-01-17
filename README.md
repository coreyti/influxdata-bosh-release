# InfluxData TICK stack BOSH Release

pre-alpha/WIP (stay tuned)

## TODO

- [ ] Get certs into telegraf, from links
- [ ] Correctly configure telegraf --> influxdb address and cert SANs.
      Try `use_dns_addresses`

- [ ] Add TLS and Auth (BOSH UAA & a load balancer).
- [ ] Create `/var/vcap/store` directories.
- [ ] Disable sending of usage stats to influxdata.com.

      ```shell
      # in /var/vcap/sys/log/influxdata-influxdb/stderr.log
      # " Sending usage statistics to usage.influxdata.com"
      ```

- [ ] Add database creation to post-start or errand, etc.
- [ ] Add note to telegraf spec re ENV variable availability.
- [ ] Add handling of non-String value types in `toml` helper.
- [ ] Write `wal` and `data` directories to separate disks. See:
      https://docs.influxdata.com/influxdb/v1.4/guides/hardware_sizing/ (bottom of page).
- [ ] Determine appropriate sizing for VM and configs.
- [ ] Determine desired downsampling and data retention policies.
- [ ] (?) Add configuration for influxdb, `subscriber.ca-certs`.
- [ ] (?) Remove the 'influxdata-' prefix from jobs, etc.
- [ ] Determine whether there's a way to seed users:
  - admin
  - telegraf

  Perhaps via `influx -execute 'command'`

  ```shell
  $ /var/vcap/packages/influxdata-influxdb/influx -execute 'show users' -ssl -unsafeSsl -host 127.0.0.1
  # if exit code is non-zero, create users.
  ```
