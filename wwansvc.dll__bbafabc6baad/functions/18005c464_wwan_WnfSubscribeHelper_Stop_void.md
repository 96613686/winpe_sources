# wwan::WnfSubscribeHelper::Stop(void)

- ea: `0x18005c464`
- end: `0x18005c4f8`
- name: `?Stop@WnfSubscribeHelper@wwan@@QEAAJXZ`
- size: `148`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005c2ec`
- `0x18005db28`
- `0x180073f18`
- `0x18007eb08`

## callees

- `0x18001678c`
- `0x18005c464`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWithCompletionCallback` at `0x18005c4a3`
- `ntdll!RtlUnsubscribeWnfNotificationWithCompletionCallback` at `0x18005c4a3`
- `ntdll!RtlNtStatusToDosError` at `0x18005c4f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c46d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c46d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c47d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c48e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c47d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c48e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005c4b8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005c4b8`

## string_xrefs

- `0x18005c4d1`: `onecoreuap\net\wwan\service\core\wwanwnfmessage.cpp`

## pseudocode

```c

```
