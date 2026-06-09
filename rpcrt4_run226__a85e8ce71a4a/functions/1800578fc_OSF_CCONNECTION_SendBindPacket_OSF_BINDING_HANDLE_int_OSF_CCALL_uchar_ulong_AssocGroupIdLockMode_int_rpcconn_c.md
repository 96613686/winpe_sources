# OSF_CCONNECTION::SendBindPacket(OSF_BINDING_HANDLE *,int,OSF_CCALL *,uchar,ulong,AssocGroupIdLockMode *,int,rpcconn_common * *,uint *,rpcconn_common *,uint)

- ea: `0x1800578fc`
- end: `0x1800585bf`
- name: `?SendBindPacket@OSF_CCONNECTION@@QEAAJPEAVOSF_BINDING_HANDLE@@HPEAVOSF_CCALL@@EKPEAW4AssocGroupIdLockMode@@HPEAPEAUrpcconn_common@@PEAIPEAU5@I@Z`
- size: `3267`
- prototype: `__int64 __usercall@<rax>(OSF_CCONNECTION *__hidden this@<rcx>, struct OSF_BINDING_HANDLE *@<rdx>, int@<r8d>, struct OSF_CCALL *@<r9>, char, unsigned int, enum AssocGroupIdLockMode *, int, struct rpcconn_common **, unsigned int *, struct rpcconn_common *, unsigned int)`
- caller_count: `3`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056ee0`
- `0x18009179c`
- `0x18009ea0c`

## callees

- `0x1800206a0`
- `0x180021ce0`
- `0x180025280`
- `0x1800283bc`
- `0x1800550b0`
- `0x180056eb0`
- `0x180057410`
- `0x1800578fc`
- `0x180058b5c`
- `0x180058f24`
- `0x180058f90`
- `0x180059504`
- `0x1800595ac`
- `0x180059700`
- `0x18005a81c`
- `0x180086c5c`
- `0x180090c30`
- `0x180096e28`
- `0x180097264`
- `0x18009a280`
- `0x18009a5f4`
- `0x18009d3ec`
- `0x18009f390`
- `0x1800a27e4`
- `0x1800ca140`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180057e3e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180057e3e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005803d`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005803d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180057b4c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180057b4c`
- `SspiCli!SeciAllocateAndSetCallTarget` at `0x180057cf7`
- `SspiCli!SeciAllocateAndSetCallTarget` at `0x180057cf7`
- `SspiCli!SeciFreeCallContext` at `0x1800582b1`
- `SspiCli!SeciFreeCallContext` at `0x1800582b1`

## pseudocode

```c

```
