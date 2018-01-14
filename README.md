# BOSH influxdata Release

WIP

## TODO

- [ ] Add TLS and Auth (BOSH UAA & a load balancer).
- [ ] Create `/var/vcap/store` directories.
- [ ] Disable sending of usage stats to influxdata.com.

      ```shell
      # in /var/vcap/sys/log/influxdata-influxdb/stderr.log
      # " Sending usage statistics to usage.influxdata.com"
      ```

- [ ] Add database creation to post-start or errand, etc.
