# OSF_CCONNECTION::SendBindPacket(OSF_BINDING_HANDLE *,int,OSF_CCALL *,uchar,ulong,AssocGroupIdLockMode *,int,rpcconn_common * *,uint *,rpcconn_common *,uint)

- ea: `0x18005feb0`
- end: `0x180060b92`
- name: `?SendBindPacket@OSF_CCONNECTION@@QEAAJPEAVOSF_BINDING_HANDLE@@HPEAVOSF_CCALL@@EKPEAW4AssocGroupIdLockMode@@HPEAPEAUrpcconn_common@@PEAIPEAU5@I@Z`
- size: `3298`
- prototype: `__int64 __usercall@<rax>(OSF_CCONNECTION *__hidden this@<rcx>, struct OSF_BINDING_HANDLE *@<rdx>, int@<r8d>, struct OSF_CCALL *@<r9>, char, unsigned int, enum AssocGroupIdLockMode *, int, struct rpcconn_common **, unsigned int *, struct rpcconn_common *, unsigned int)`
- caller_count: `3`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005f404`
- `0x180066ffc`
- `0x18006a45c`

## callees

- `0x1800217d0`
- `0x180022e80`
- `0x180026500`
- `0x1800295d8`
- `0x18005d568`
- `0x18005f3d0`
- `0x18005f968`
- `0x18005feb0`
- `0x18006112c`
- `0x180061518`
- `0x180061584`
- `0x180061b24`
- `0x180061bd0`
- `0x180061d24`
- `0x180062e78`
- `0x18006b690`
- `0x180089c90`
- `0x180094fa0`
- `0x18009a740`
- `0x18009ab68`
- `0x18009dbd8`
- `0x18009deb0`
- `0x1800a0c5c`
- `0x1800a5db4`
- `0x1800ceda0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800603ff`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800603ff`
- `ntdll!RtlAcquireSRWLockShared` at `0x180060604`
- `ntdll!RtlAcquireSRWLockShared` at `0x180060604`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180060100`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180060100`
- `SspiCli!SeciAllocateAndSetCallTarget` at `0x1800602b2`
- `SspiCli!SeciAllocateAndSetCallTarget` at `0x1800602b2`
- `SspiCli!SeciFreeCallContext` at `0x18006087e`
- `SspiCli!SeciFreeCallContext` at `0x18006087e`

## pseudocode

```c

```
