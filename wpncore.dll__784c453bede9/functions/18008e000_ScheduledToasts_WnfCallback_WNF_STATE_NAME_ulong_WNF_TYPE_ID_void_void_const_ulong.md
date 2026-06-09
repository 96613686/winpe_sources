# ScheduledToasts::WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x18008e000`
- end: `0x18008e364`
- name: `?WnfCallback@ScheduledToasts@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `868`
- prototype: `static int(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002cec`
- `0x180022888`
- `0x18002ee38`
- `0x18002ff5c`
- `0x1800708e4`
- `0x180073424`
- `0x18008a97c`
- `0x18008e000`
- `0x1800af0a4`
- `0x1800b99f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008e097`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008e097`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008e060`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008e060`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e317`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e317`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e325`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e325`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008e330`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008e330`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008e12e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008e12e`

## string_xrefs

- `0x18008e0d8`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x18008e13e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x18008e18f`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`

## pseudocode

```c

```
