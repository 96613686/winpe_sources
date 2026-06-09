# CTptReadFile::GetData(_ULARGE_INTEGER,_ULARGE_INTEGER,void * *,int *,ulong *)

- ea: `0x18000cdd0`
- end: `0x18000cf31`
- name: `?GetData@CTptReadFile@@QEAAKT_ULARGE_INTEGER@@0PEAPEAXPEAHPEAK@Z`
- size: `353`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, union _ULARGE_INTEGER, union _ULARGE_INTEGER, void **, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006c90`

## callees

- `0x18000cad4`
- `0x18000cdd0`
- `0x180060e42`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000cdfa`
- `KERNEL32!EnterCriticalSection` at `0x18000cdfa`
- `KERNEL32!LeaveCriticalSection` at `0x18000cf0e`
- `KERNEL32!LeaveCriticalSection` at `0x18000cf0e`
- `WDSSRV!WdsPacketAllocate` at `0x18000ce98`
- `WDSSRV!WdsPacketAllocate` at `0x18000ce98`

## pseudocode

```c

```
