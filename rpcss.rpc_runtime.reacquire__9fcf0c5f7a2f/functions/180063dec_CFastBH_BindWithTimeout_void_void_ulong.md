# CFastBH::BindWithTimeout(void *,void *,ulong)

- ea: `0x180063dec`
- end: `0x180064116`
- name: `?BindWithTimeout@CFastBH@@CAJPEAX0K@Z`
- size: `810`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding, RPC_IF_HANDLE IfSpec, DWORD dwMilliseconds)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180068a10`
- `0x18006a4e0`

## callees

- `0x1800210f8`
- `0x180025950`
- `0x180063dec`
- `0x180064120`
- `0x180091a10`
- `0x1800b7ac0`
- `0x1800b8428`

## import_xrefs

- `RPCRT4!RpcAsyncInitializeHandle` at `0x180063e75`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180063e75`
- `RPCRT4!RpcAsyncCancelCall` at `0x180064016`
- `RPCRT4!RpcAsyncCancelCall` at `0x180064016`
- `RPCRT4!RpcBindingBind` at `0x180063e26`
- `RPCRT4!RpcBindingBind` at `0x180063f24`
- `RPCRT4!RpcBindingBind` at `0x180063e26`
- `RPCRT4!RpcBindingBind` at `0x180063f24`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x180063f59`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x180063f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180063e8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180063e8b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180063f3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180064029`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180063f3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180064029`

## string_xrefs

- `0x180063eaf`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x180063fb4`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x180063ff8`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x180064039`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x180064099`: `onecore\com\combase\common\core\fastbh.cxx`

## pseudocode

```c

```
