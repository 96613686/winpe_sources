# CFTMCrossProcClientImpl::_UnwrapStream(UnmarshalAction,IStream *)

- ea: `0x1800081c8`
- end: `0x1800083bb`
- name: `?_UnwrapStream@CFTMCrossProcClientImpl@@AEAAJW4UnmarshalAction@@PEAUIStream@@@Z`
- size: `499`
- prototype: `int __high(enum UnmarshalAction, struct IStream *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008170`
- `0x180092ca0`

## callees

- `0x1800081c8`
- `0x1800083d0`
- `0x180008474`
- `0x18001e800`
- `0x18001f74c`
- `0x18002064c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008291`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000832f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000832f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000829b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000829b`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18000820e`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18000820e`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800082bf`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800082bf`

## pseudocode

```c

```
