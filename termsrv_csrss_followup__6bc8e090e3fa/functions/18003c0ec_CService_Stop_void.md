# CService::Stop(void)

- ea: `0x18003c0ec`
- end: `0x18003c192`
- name: `?Stop@CService@@QEAAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003c2e0`

## callees

- `0x18003bbbc`
- `0x18003c0ec`
- `0x18003c204`
- `0x1800a12a8`
- `0x1800a3bd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003c12e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003c12e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003c100`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003c100`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18003c15a`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18003c15a`
- `WS2_32!__imp_WSACleanup` at `0x18003c170`
- `WS2_32!__imp_WSACleanup` at `0x18003c170`
- `USER32!UnregisterDeviceNotification` at `0x18003c14a`
- `USER32!UnregisterDeviceNotification` at `0x18003c14a`

## pseudocode

```c

```
