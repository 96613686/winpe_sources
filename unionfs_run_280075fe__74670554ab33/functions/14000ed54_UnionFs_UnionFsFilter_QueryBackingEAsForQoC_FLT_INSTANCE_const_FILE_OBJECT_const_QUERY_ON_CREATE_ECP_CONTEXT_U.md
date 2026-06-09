# UnionFs::UnionFsFilter::QueryBackingEAsForQoC(_FLT_INSTANCE const &,_FILE_OBJECT const &,_QUERY_ON_CREATE_ECP_CONTEXT *,UnionFs::StackEventTracer &)

- ea: `0x14000ed54`
- end: `0x14000ef28`
- name: `?QueryBackingEAsForQoC@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAU_QUERY_ON_CREATE_ECP_CONTEXT@@AEAVStackEventTracer@2@@Z`
- size: `468`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, struct _QUERY_ON_CREATE_ECP_CONTEXT *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a7c8`

## callees

- `0x14000ed54`
- `0x140056a50`
- `0x140056ac4`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000eec1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eec1`
- `ntoskrnl!ExAllocatePool2` at `0x14000ee12`
- `ntoskrnl!ExAllocatePool2` at `0x14000ee12`
- `FLTMGR!FltQueryInformationFile` at `0x14000ed96`
- `FLTMGR!FltQueryInformationFile` at `0x14000ed96`
- `FLTMGR!FltQueryEaFile` at `0x14000ee7e`
- `FLTMGR!FltQueryEaFile` at `0x14000ee7e`

## pseudocode

```c

```
