# OSF_CCALL::ActuallyProcessPDU(rpcconn_common *,uint,_RPC_MESSAGE *,int,int *)

- ea: `0x18005f9cc`
- end: `0x18005fea9`
- name: `?ActuallyProcessPDU@OSF_CCALL@@AEAAJPEAUrpcconn_common@@IPEAU_RPC_MESSAGE@@HPEAH@Z`
- size: `1245`
- prototype: `__int64 __usercall@<rax>(OSF_CCALL *__hidden this@<rcx>, struct rpcconn_common *@<rdx>, unsigned int@<r8d>, struct _RPC_MESSAGE *@<r9>, int, int *)`
- caller_count: `3`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005e7d0`
- `0x180068fb0`
- `0x1800985e0`

## callees

- `0x1800162e0`
- `0x180022e80`
- `0x180023020`
- `0x180026500`
- `0x18002cab0`
- `0x18005ee10`
- `0x18005f9cc`
- `0x18006112c`
- `0x180061160`
- `0x180061d24`
- `0x180062e78`
- `0x180068464`
- `0x180068b80`
- `0x18009e040`
- `0x1800a5db4`
- `0x1800b03a8`
- `0x1800b23ac`
- `0x1800b27f4`
- `0x1800cec85`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18005fb00`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fb50`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fc52`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fc70`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fccd`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fd61`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fd97`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fdce`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fe1c`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fb00`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fb50`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fc52`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fc70`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fccd`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fd61`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fd97`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fdce`
- `ntdll!RtlLeaveCriticalSection` at `0x18005fe1c`
- `ntdll!RtlEnterCriticalSection` at `0x18005fae8`
- `ntdll!RtlEnterCriticalSection` at `0x18005fc22`
- `ntdll!RtlEnterCriticalSection` at `0x18005fd26`
- `ntdll!RtlEnterCriticalSection` at `0x18005fae8`
- `ntdll!RtlEnterCriticalSection` at `0x18005fc22`
- `ntdll!RtlEnterCriticalSection` at `0x18005fd26`

## pseudocode

```c

```
