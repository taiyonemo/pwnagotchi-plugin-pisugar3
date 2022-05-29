# pwnagotchi-plugin-pisugar3
pwnagotchi plugin for pisugar 3 UPS.

# Installation
1.  Enable i2c by running `sudo raspi-config` select option 3 and enable i2c. You can skip this if you have already enabled I2c to setup a RTC.

3. use scp to copy the plugin to `/usr/local/lib/python3.7/dist-packages/pwnagotchi/plugins/default` .
```bash
scp pisugar3.py pi@10.0.0.2:/usr/local/lib/python3.7/dist-packages/pwnagotchi/plugins/default/pisugar3.py
```

2. Enable the plugin in `/etc/pwnagotchi/config.toml` by adding the following line.
```toml
main.plugins.pisugar3.enabled = true
```

3. Set the percentage that should trigger a power off.
```toml
main.plugins.pisugar3.shutdown = 5
```

# TODO
- [x] Display battery percentage as read from register 0x2a
- [ ] Add provisions for callibrating the value from 0x2a
- [ ] Display battery voltage from 0x22 and 0x23
- [ ] Display charging status. 6th bit from 0x02
- [ ] Safe shutdown using soft switch or powerswitch.

