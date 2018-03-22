# Test-Kitchen - InSpec with Puppet on Dcoker Example

## Install dependenceies

```bahs
$ bundle install --path vendor/bundle
```

## Show available tests

```bash
$ bundle exec kitchen list
Instance         Driver  Provisioner  Verifier  Transport  Last Action    Last Error
default-centos7  Docker  PuppetApply  Inspec    Ssh        <Not Created>  <None>
```

## Run test

```bash
$ bundle exec kitchen test
-----> Starting Kitchen (v1.20.0)
-----> Cleaning up any prior instances of <default-centos-7>
-----> Destroying <default-centos-7>...
       Finished destroying <default-centos-7> (0m0.00s).
-----> Testing <default-centos-7>
-----> Creating <default-centos-7>...
       Sending build context to Docker daemon  41.11MB

.................

Version: (not specified)
Target:  ssh://kitchen@localhost:32781

  ✔  01: Verify nginx service
     ✔  Service nginx should be enabled
     ✔  Service nginx should be installed
     ✔  Service nginx should be running

  System Package nginx
     ✔  should be installed
  User nginx
     ✔  should exist

Profile Summary: 1 successful control, 0 control failures, 0 controls skipped
Test Summary: 5 successful, 0 failures, 0 skipped
       Finished verifying <default-centos-7> (0m0.70s).
-----> Destroying <default-centos-7>...
       PID                 USER                TIME                COMMAND
       18923               0                   0:00                {systemd} /sbin/init
       18966               0                   0:00                /usr/lib/systemd/systemd-journald
       18976               0                   0:00                /usr/lib/systemd/systemd-udevd
       19607               0                   0:00                /usr/lib/systemd/systemd-logind
       19608               81                  0:00                /bin/dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation
       19636               0                   0:00                /usr/sbin/sshd -D
       19646               0                   0:00                /sbin/agetty --noclear tty1 linux
       19665               0                   0:00                sshd: kitchen [priv]
       19667               1000                0:03                sshd: kitchen@notty
       19928               0                   0:00                nginx: master process /usr/sbin/nginx -c /etc/nginx/nginx.conf
       19929               999                 0:00                nginx: worker process
       19959               0                   0:00                sshd: kitchen [priv]
       19961               1000                0:00                sshd: kitchen@notty
       b1cdead29ded9e318a250729007c51b27bfbbf311c4f0d3a25fb12b309f3c296
       b1cdead29ded9e318a250729007c51b27bfbbf311c4f0d3a25fb12b309f3c296
       Finished destroying <default-centos-7> (0m1.24s).
       Finished testing <default-centos-7> (1m22.66s).
-----> Kitchen is finished. (1m23.99s)
```
