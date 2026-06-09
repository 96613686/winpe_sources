# ComputeService::Communication::BridgeNotificationWatcher::WaitForNotification(ComputeService::Communication::BridgeNotificationType,ulong,long)

- ea: `0x1400609e4`
- end: `0x140060b1e`
- name: `?WaitForNotification@BridgeNotificationWatcher@Communication@ComputeService@@QEAA?AV?$shared_ptr@UOperationResult@Management@ComputeService@@@std@@W4BridgeNotificationType@23@KJ@Z`
- size: `314`
- prototype: `__int64 __fastcall(struct Vml::VmSlimReaderWriterLock *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400fa148`

## callees

- `0x14001629c`
- `0x14005bcd8`
- `0x1400609e4`
- `0x14008d158`
- `0x1400f3f04`
- `0x1400f92ac`
- `0x1401332f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140060a14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140060a14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140060af6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140060af6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140060a6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140060a8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140060a6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140060a8f`

## pseudocode

```c

```
