## Simple EDA Testing Repo

1. Build the container.

```bash
docker build . -t local-eda-test
```

2. Run the docker container

```bash
docker run -it local-eda-test bash
```

3. Run the ansible-rulebook

Once the docker container is running and you're in the cli run the playbook.

```bash
ansible-rulebook --rulebook rb-nb-events.yml -i inventory.yml --verbose
```

4. Add new fake partial events to `rb-nb-events.yml`

Below is a starting fake record.

```yaml
          - device_type:
              object_type: dcim.devicetype
              part_number: ASR1000v
            display: ams01-jlk-02
            id: 773b8e60-f744-458a-9680-fd004fd30311
            last_updated: '2024-07-15T18:13:42.833317Z'
            location:
              display: Europe → Netherlands → AMS01
              name: AMS01
            name: ams01-jlk-02
            platform:
              display: Cisco IOS
              name: cisco_ios
              napalm_args: 
              napalm_driver: ios
              natural_slug: cisco-ios_f48f
              network_driver: cisco_ios
              network_driver_mappings:
                ansible: cisco.ios.ios
                hier_config: ios
                napalm: ios
                netmiko: cisco_ios
                netutils_parser: cisco_ios
                ntc_templates: cisco_ios
                pyntc: cisco_ios
                scrapli: cisco_ios
              object_type: dcim.platform
            role:
              display: wan
              name: wan
            serial: ''
            status:
              description: Unit is active
              display: Active
              name: Active
            tenant:
              name: Nautobot Airports
              natural_slug: nautobot-airports_1f7f
              object_type: tenancy.tenant
```
