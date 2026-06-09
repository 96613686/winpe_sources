# GetJetColumnFromUSPropVal(TableHandleInfo * const,_USPROPVAL const *,int,ColumnDetails *,void const * *,ulong *)

- ea: `0x18000f6d0`
- end: `0x18000f870`
- name: `?GetJetColumnFromUSPropVal@@YAJQEAUTableHandleInfo@@PEBU_USPROPVAL@@HPEAUColumnDetails@@PEAPEBXPEAK@Z`
- size: `416`
- prototype: `int(struct TableHandleInfo *const, const struct _USPROPVAL *, int, struct ColumnDetails *, const void **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180096ef0`

## callees

- `0x1800068f0`
- `0x18000f6d0`
- `0x18000f880`
- `0x18006ab60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f796`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f825`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f796`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f825`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f72c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f72c`

## string_xrefs

- `0x18000f7c7`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f7e0`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f7f9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f856`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c

```
