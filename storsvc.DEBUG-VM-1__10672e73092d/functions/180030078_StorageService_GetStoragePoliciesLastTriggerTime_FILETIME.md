# StorageService::GetStoragePoliciesLastTriggerTime(_FILETIME *)

- ea: `0x180030078`
- end: `0x1800301bb`
- name: `?GetStoragePoliciesLastTriggerTime@StorageService@@QEAAJPEAU_FILETIME@@@Z`
- size: `323`
- prototype: `int(StorageService *__hidden this, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180037700`

## callees

- `0x180001148`
- `0x1800011d0`
- `0x1800108f4`
- `0x180010d24`
- `0x180012734`
- `0x180019db4`
- `0x180030078`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030131`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030131`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800300b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800300b0`

## string_xrefs

- `0x1800300ec`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c

```
