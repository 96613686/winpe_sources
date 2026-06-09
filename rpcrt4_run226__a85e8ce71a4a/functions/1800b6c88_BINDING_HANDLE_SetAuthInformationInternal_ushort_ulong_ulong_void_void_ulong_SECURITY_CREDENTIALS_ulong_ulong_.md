# BINDING_HANDLE::SetAuthInformationInternal(ushort *,ulong,ulong,void *,void *,ulong,SECURITY_CREDENTIALS *,ulong,ulong,ulong,ulong,ulong,void *,void *,int,int,void *,int)

- ea: `0x1800b6c88`
- end: `0x1800b7340`
- name: `?SetAuthInformationInternal@BINDING_HANDLE@@AEAAJPEAGKKPEAX1KPEAVSECURITY_CREDENTIALS@@KKKKK11HH1H@Z`
- size: `1720`
- prototype: `int(BINDING_HANDLE *__hidden this, unsigned __int16 *, unsigned int, unsigned int, void *, void *, unsigned int, struct SECURITY_CREDENTIALS *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void *, void *, int, int, void *, int)`
- caller_count: `2`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b6bc0`
- `0x1800b7460`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18002d420`
- `0x18002f460`
- `0x1800306c8`
- `0x1800459a8`
- `0x180054128`
- `0x18005c154`
- `0x18006ab28`
- `0x18008f9c8`
- `0x1800998e0`
- `0x180099eb8`
- `0x18009b738`
- `0x18009c8c0`
- `0x1800a3cc8`
- `0x1800a58e8`
- `0x1800a74f0`
- `0x1800aa460`
- `0x1800b6734`
- `0x1800b6760`
- `0x1800b677c`
- `0x1800b6c88`
- `0x1800b76b0`
- `0x1800c9aa0`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800b6e6a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b71f2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b72f8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b6e6a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b71f2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b72f8`
- `ntdll!RtlEnterCriticalSection` at `0x1800b6e4b`
- `ntdll!RtlEnterCriticalSection` at `0x1800b7163`
- `ntdll!RtlEnterCriticalSection` at `0x1800b71cc`
- `ntdll!RtlEnterCriticalSection` at `0x1800b72d9`
- `ntdll!RtlEnterCriticalSection` at `0x1800b6e4b`
- `ntdll!RtlEnterCriticalSection` at `0x1800b7163`
- `ntdll!RtlEnterCriticalSection` at `0x1800b71cc`
- `ntdll!RtlEnterCriticalSection` at `0x1800b72d9`
- `ext-ms-win-rpc-ssl-l1-1-0!ValidatePrincipalName` at `0x1800b710b`
- `ext-ms-win-rpc-ssl-l1-1-0!ValidatePrincipalName` at `0x1800b710b`

## pseudocode

```c

```
