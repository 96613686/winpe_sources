# CService::Stop(void)

- ea: `0x180039ff0`
- end: `0x18003a077`
- name: `?Stop@CService@@QEAAJXZ`
- size: `135`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003a190`

## callees

- `0x180039b34`
- `0x180039ff0`
- `0x18003a0e4`
- `0x18009cef4`
- `0x18009e7ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a02c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a02c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a004`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a004`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18003a04c`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18003a04c`
- `WS2_32!__imp_WSACleanup` at `0x18003a05c`
- `WS2_32!__imp_WSACleanup` at `0x18003a05c`
- `USER32!UnregisterDeviceNotification` at `0x18003a042`
- `USER32!UnregisterDeviceNotification` at `0x18003a042`

## pseudocode

```c

```
