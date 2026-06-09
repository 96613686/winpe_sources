# Microsoft::Diagnostics::ApiServer::RegisterInterface(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,void *)

- ea: `0x18006ec80`
- end: `0x18006eec0`
- name: `?RegisterInterface@ApiServer@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAX@Z`
- size: `576`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006e038`
- `0x1801817c4`

## callees

- `0x180001bf4`
- `0x18001d160`
- `0x180026ecc`
- `0x180035698`
- `0x18005d050`
- `0x18006dd98`
- `0x18006ec80`
- `0x18006f66c`
- `0x18007fae8`
- `0x18012de40`
- `0x1801d0080`
- `0x1802b46d4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006ece6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006ece6`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18006edec`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18006edec`
- `RPCRT4!RpcServerRegisterIf3` at `0x18006ed51`
- `RPCRT4!RpcServerRegisterIf3` at `0x18006ed51`
- `RPCRT4!RpcServerInqBindings` at `0x18006eda1`
- `RPCRT4!RpcServerInqBindings` at `0x18006eda1`
- `RPCRT4!RpcEpRegisterW` at `0x18006ee0a`
- `RPCRT4!RpcEpRegisterW` at `0x18006ee0a`

## string_xrefs

- `0x18006ed0b`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x18006ed77`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x18006edc5`: `onecore\base\telemetry\utc\common\apiserver.cpp`

## pseudocode

```c

```
