# Microsoft::Diagnostics::MetadataEngine::RegistryUpdateThreadProc(void)

- ea: `0x1801baacc`
- end: `0x1801bae1f`
- name: `?RegistryUpdateThreadProc@MetadataEngine@Diagnostics@Microsoft@@AEAAKXZ`
- size: `851`
- prototype: `unsigned int __fastcall(Microsoft::Diagnostics::MetadataEngine *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801baed0`

## callees

- `0x180001bf4`
- `0x1800035ec`
- `0x18005d050`
- `0x1800a1e24`
- `0x1800bc2e0`
- `0x1800d0d7c`
- `0x1800d0d9c`
- `0x18012eb08`
- `0x18013079c`
- `0x1801b93e4`
- `0x1801b98a8`
- `0x1801baacc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801badc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801badc5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1801baba0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1801bad2c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1801baba0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1801bad2c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801bac2b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801bac2b`

## string_xrefs

- `0x1801bac87`: `onecore\base\telemetry\utc\service\engine\metadataengine.cpp`
- `0x1801bad80`: `onecore\base\telemetry\utc\service\engine\metadataengine.cpp`
- `0x1801bad94`: `onecore\base\telemetry\utc\service\engine\metadataengine.cpp`
- `0x1801bae0c`: `onecore\base\telemetry\utc\service\engine\metadataengine.cpp`

## pseudocode

```c

```
