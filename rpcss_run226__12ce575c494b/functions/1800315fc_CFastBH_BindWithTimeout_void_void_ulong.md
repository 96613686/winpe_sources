# CFastBH::BindWithTimeout(void *,void *,ulong)

- ea: `0x1800315fc`
- end: `0x1800318fd`
- name: `?BindWithTimeout@CFastBH@@CAJPEAX0K@Z`
- size: `769`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding, RPC_IF_HANDLE IfSpec, DWORD dwMilliseconds)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180063470`
- `0x180064f80`

## callees

- `0x18002ba28`
- `0x18002f8cc`
- `0x1800315fc`
- `0x180031910`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `RPCRT4!RpcAsyncInitializeHandle` at `0x180031678`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180031678`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800317df`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800317df`
- `RPCRT4!RpcBindingBind` at `0x180031635`
- `RPCRT4!RpcBindingBind` at `0x1800316ff`
- `RPCRT4!RpcBindingBind` at `0x180031635`
- `RPCRT4!RpcBindingBind` at `0x1800316ff`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x180031728`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x180031728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003182e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800318b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800318da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003182e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800318b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800318da`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031775`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003184a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800318ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800318d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800318f6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031775`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003184a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800318ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800318d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800318f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031688`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031688`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031713`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800317ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031713`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800317ec`

## string_xrefs

- `0x1800316a6`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x180031780`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x1800317c4`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x1800317f6`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x180031855`: `onecore\com\combase\common\core\fastbh.cxx`

## pseudocode

```c

```
