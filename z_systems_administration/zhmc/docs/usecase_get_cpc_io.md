# usecase_get_cpc_io.yml playbook

The [usecase_get_cpc_io.yml](../playbooks/usecase_get_cpc_io.yml) playbook
gathers facts about the CPC and its adapters and partitions and generates a
Markdown file that shows the I/O configuration of the CPC.

This is an example invocation of the playbook:

```
$ ansible-playbook usecase_get_cpc_io.yml

PLAY [localhost] ***************************************************************

TASK [Gathering Facts] *********************************************************
ok: [localhost]

TASK [Get facts for CPC CPCA] **************************************************
ok: [localhost]

TASK [Get facts for all adapters of CPC CPCA] **********************************
ok: [localhost] => (item=FCP1.D1)
ok: [localhost] => (item=FCP1.D2)
ok: [localhost] => (item=FCP2.D1)
ok: [localhost] => (item=FCP2.D2)
ok: [localhost] => (item=OSD1)
ok: [localhost] => (item=OSM1)
ok: [localhost] => (item=OSD2)
ok: [localhost] => (item=OSD3)
ok: [localhost] => (item=CRYP00)
ok: [localhost] => (item=CRYP01)
ok: [localhost] => (item=OSD4)
ok: [localhost] => (item=OSM2)
ok: [localhost] => (item=CRYP02)
ok: [localhost] => (item=test_hip)

TASK [Get facts for all partitions of CPC CPCA] ********************************
ok: [localhost] => (item=TEST1)
ok: [localhost] => (item=TEST2)

TASK [Using Jinja2 template to create output file: playbooks/cpc_io_CPCA.md] ***
changed: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=5    changed=1    unreachable=0    failed=0
                             skipped=0    rescued=0    ignored=0
```

This is the Markdown file showing the I/O configuration of the CPC that was
generated by the example invocation of the playbook:

![playbooks/cpc_io_CPCA.md](usecase_get_cpc_io_output.md)
