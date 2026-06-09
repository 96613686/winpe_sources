# RPC_SERVER::UseRpcProtocolSequence(ushort *,ushort *,uint,ushort *,void *,ulong,ulong,ushort * *,int,MTMLinkSymmetric *,RPCP_INTERFACE_GROUP *)

- ea: `0x18006d1e4`
- end: `0x18006d9d0`
- name: `?UseRpcProtocolSequence@RPC_SERVER@@QEAAJPEAG0I0PEAXKKPEAPEAGHPEAVMTMLinkSymmetric@@PEAVRPCP_INTERFACE_GROUP@@@Z`
- size: `2028`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *Src, struct _SECURITY_DESCRIPTOR *, unsigned int, unsigned int, unsigned __int16 **, int, struct MTMLinkSymmetric *, struct RPCP_INTERFACE_GROUP *)`
- caller_count: `5`
- callee_count: `29`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18006cddc`
- `0x18006d140`
- `0x18006e120`
- `0x1800a9ce0`
- `0x1800b3890`

## callees

- `0x1800183bc`
- `0x18001d750`
- `0x180022870`
- `0x18002b7c0`
- `0x18002d420`
- `0x18004f480`
- `0x18004f554`
- `0x18006203c`
- `0x18006d1e4`
- `0x180070400`
- `0x18008cfcc`
- `0x18008ff40`
- `0x1800900ec`
- `0x180094444`
- `0x18009492c`
- `0x180095138`
- `0x180095dc4`
- `0x180095f98`
- `0x180096ce8`
- `0x180099688`
- `0x180099c84`
- `0x18009d010`
- `0x1800aa100`
- `0x1800aa1d0`
- `0x1800aa250`
- `0x1800b3c4c`
- `0x1800b3c9c`
- `0x1800c99a0`
- `0x1800d2010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18006d291`
- `ntdll!_wcsicmp` at `0x18006d49f`
- `ntdll!_wcsicmp` at `0x18006d291`
- `ntdll!_wcsicmp` at `0x18006d49f`
- `ntdll!DbgPrint` at `0x18006d305`
- `ntdll!DbgPrint` at `0x18006d319`
- `ntdll!DbgPrint` at `0x18006d365`
- `ntdll!DbgPrint` at `0x18006d37a`
- `ntdll!DbgPrint` at `0x18006d43c`
- `ntdll!DbgPrint` at `0x18006d449`
- `ntdll!DbgPrint` at `0x18006d461`
- `ntdll!DbgPrint` at `0x18006d305`
- `ntdll!DbgPrint` at `0x18006d319`
- `ntdll!DbgPrint` at `0x18006d365`
- `ntdll!DbgPrint` at `0x18006d37a`
- `ntdll!DbgPrint` at `0x18006d43c`
- `ntdll!DbgPrint` at `0x18006d449`
- `ntdll!DbgPrint` at `0x18006d461`
- `ntdll!_wcsnicmp` at `0x18006d487`
- `ntdll!_wcsnicmp` at `0x18006d487`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d39c`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d3fd`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d551`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d59d`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d673`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d6f3`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d858`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d888`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d951`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d9c3`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d39c`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d3fd`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d551`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d59d`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d673`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d6f3`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d858`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d888`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d951`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d9c3`
- `ntdll!RtlEnterCriticalSection` at `0x18006d322`
- `ntdll!RtlEnterCriticalSection` at `0x18006d3b3`
- `ntdll!RtlEnterCriticalSection` at `0x18006d518`
- `ntdll!RtlEnterCriticalSection` at `0x18006d5ea`
- `ntdll!RtlEnterCriticalSection` at `0x18006d826`
- `ntdll!RtlEnterCriticalSection` at `0x18006d934`
- `ntdll!RtlEnterCriticalSection` at `0x18006d963`
- `ntdll!RtlEnterCriticalSection` at `0x18006d322`
- `ntdll!RtlEnterCriticalSection` at `0x18006d3b3`
- `ntdll!RtlEnterCriticalSection` at `0x18006d518`
- `ntdll!RtlEnterCriticalSection` at `0x18006d5ea`
- `ntdll!RtlEnterCriticalSection` at `0x18006d826`
- `ntdll!RtlEnterCriticalSection` at `0x18006d934`
- `ntdll!RtlEnterCriticalSection` at `0x18006d963`

## string_xrefs

- `0x18006d45a`: `RPC: To determine the symbolic stack, do an "ln" on the above addresses in the context of the faulting process.\n\n`
- `0x18006d2f7`: `Possible security threat: Insecure interface becomes remotely accessible`
- `0x18006d42e`: `Possible security threat: Server is forced to listen on all interfaces circumventing the firewall`

## pseudocode

```c

```
