# CTptReadFile::UpdateCache(_ULARGE_INTEGER,_ULARGE_INTEGER,ITptReadFileCallback *,void *,ulong *)

- ea: `0x18000d2bc`
- end: `0x18000d3de`
- name: `?UpdateCache@CTptReadFile@@QEAAKT_ULARGE_INTEGER@@0PEAVITptReadFileCallback@@PEAXPEAK@Z`
- size: `290`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, union _ULARGE_INTEGER, union _ULARGE_INTEGER, struct ITptReadFileCallback *, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x18000710c`

## callees

- `0x18000cf38`
- `0x18000d2bc`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000d2e7`
- `KERNEL32!EnterCriticalSection` at `0x18000d2e7`
- `KERNEL32!LeaveCriticalSection` at `0x18000d3b9`
- `KERNEL32!LeaveCriticalSection` at `0x18000d3b9`

## string_xrefs

- `0x18000d377`: `base\eco\wds\transport\lib\tptreadfile.cpp`

## pseudocode

```c

```
