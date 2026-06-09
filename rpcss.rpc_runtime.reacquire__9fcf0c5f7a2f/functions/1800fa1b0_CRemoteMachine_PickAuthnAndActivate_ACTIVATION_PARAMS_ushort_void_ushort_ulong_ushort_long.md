# CRemoteMachine::PickAuthnAndActivate(ACTIVATION_PARAMS *,ushort *,void * *,ushort,ulong,ushort,long *)

- ea: `0x1800fa1b0`
- end: `0x1800faad0`
- name: `?PickAuthnAndActivate@CRemoteMachine@@AEAAJPEAUACTIVATION_PARAMS@@PEAGPEAPEAXGKGPEAJ@Z`
- size: `2336`
- prototype: `__int64 __usercall@<rax>(CRemoteMachine *__hidden this@<rcx>, struct ACTIVATION_PARAMS *@<rdx>, unsigned __int16 *@<r8>, void **@<r9>, unsigned __int16, unsigned int AuthnLevel, unsigned __int16, int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f8b2c`

## callees

- `0x180002044`
- `0x18001a374`
- `0x180034260`
- `0x180034ce4`
- `0x180046930`
- `0x180046994`
- `0x1800835c0`
- `0x18008a028`
- `0x18008bdcc`
- `0x1800a64e4`
- `0x1800a78c8`
- `0x1800b7ac0`
- `0x1800f8688`
- `0x1800f9490`
- `0x1800f9a30`
- `0x1800f9e94`
- `0x1800fa084`
- `0x1800fa1b0`
- `0x1800fb0f4`
- `0x180114010`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x1800fa931`
- `RPCRT4!RpcBindingFree` at `0x1800fa931`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800fa389`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800fa6cc`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800fa988`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800fa389`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800fa6cc`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800fa988`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800fa29f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800fa50e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800fa29f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800fa50e`

## string_xrefs

- `0x1800fa447`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800fa758`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800faa4b`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`

## pseudocode

```c

```
