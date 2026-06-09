# OSF_CCONNECTION::FinishSecurityContextSetup(OSF_CCALL *,rpcconn_common * *,uint *,int *,ulong)

- ea: `0x18009179c`
- end: `0x180091ada`
- name: `?FinishSecurityContextSetup@OSF_CCONNECTION@@QEAAJPEAVOSF_CCALL@@PEAPEAUrpcconn_common@@PEAIPEAHK@Z`
- size: `830`
- prototype: `__int64 __fastcall(OSF_CCONNECTION *this, struct OSF_BINDING_HANDLE **, struct rpcconn_common **, unsigned int *, int *, unsigned int)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180056ee0`
- `0x1800ac898`

## callees

- `0x180021e70`
- `0x180025280`
- `0x180048ae8`
- `0x180049064`
- `0x18004f480`
- `0x180053bc0`
- `0x180053ca4`
- `0x180053f60`
- `0x180054ccc`
- `0x1800578fc`
- `0x18005c0d4`
- `0x18009179c`
- `0x1800923dc`
- `0x1800925c4`
- `0x1800ada48`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180091a6a`
- `ntdll!RtlLeaveCriticalSection` at `0x180091a6a`
- `ntdll!RtlEnterCriticalSection` at `0x180091a13`
- `ntdll!RtlEnterCriticalSection` at `0x180091a13`

## pseudocode

```c

```
