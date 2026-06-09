# CQueryResultsCache::GetQueryResults(ushort const *,_WMCSortItem *,ulong,CQueryResultsEntry * *)

- ea: `0x140078a48`
- end: `0x140078bce`
- name: `?GetQueryResults@CQueryResultsCache@@QEAAJPEBGPEAU_WMCSortItem@@KPEAPEAVCQueryResultsEntry@@@Z`
- size: `390`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, const unsigned __int16 *@<rdx>, struct _WMCSortItem *@<r8>, unsigned int@<r9d>, struct CQueryResultsEntry **)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x140076684`
- `0x140076a14`
- `0x140076cd0`
- `0x14007bec0`

## callees

- `0x14004639c`
- `0x1400753f8`
- `0x1400789b4`
- `0x140078a48`
- `0x14007c9f8`
- `0x14009ad04`
- `0x14009ad10`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140078a74`
- `KERNEL32!EnterCriticalSection` at `0x140078a74`
- `KERNEL32!LeaveCriticalSection` at `0x140078bac`
- `KERNEL32!LeaveCriticalSection` at `0x140078bac`
- `KERNEL32!GetTickCount64` at `0x140078b61`
- `KERNEL32!GetTickCount64` at `0x140078b61`

## pseudocode

```c

```
