# ScSaveTriggerInfo(_SERVICE_CONFIG_ROOT *,ushort const *,HKEY__ *,ulong,int,_SERVICE_TRIGGER_INFO *)

- ea: `0x140016844`
- end: `0x140016faa`
- name: `?ScSaveTriggerInfo@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEBGPEAUHKEY__@@KHPEAU_SERVICE_TRIGGER_INFO@@@Z`
- size: `1894`
- prototype: `unsigned int(struct _SERVICE_CONFIG_ROOT *, const unsigned __int16 *, HKEY, unsigned int, int, struct _SERVICE_TRIGGER_INFO *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x140029908`
- `0x14006b060`

## callees

- `0x140003e54`
- `0x140008b90`
- `0x14000d58c`
- `0x140015b14`
- `0x140016664`
- `0x140016844`
- `0x1400188fc`
- `0x14001df34`
- `0x140032be0`
- `0x140042b24`
- `0x14004b524`
- `0x1400575b0`
- `0x140064a90`
- `0x140064c4c`
- `0x14007ae5c`
- `0x14007e5c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016cb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016f3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016f4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016f7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016cb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016f3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016f4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016f7b`

## pseudocode

```c

```
