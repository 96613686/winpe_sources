# UnionFs::UfsUnionCtx::AllocAndInitShared(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::UfsInstanceCtx &,void *,utl::shared_ptr<UnionFs::UfsUnionCtx> &,UnionFs::StackEventTracer &,_GUID const *)

- ea: `0x14005f4e4`
- end: `0x14005f917`
- name: `?AllocAndInitShared@UfsUnionCtx@UnionFs@@SAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVUfsInstanceCtx@2@PEAXAEAV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@PEBU_GUID@@@Z`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400093fc`

## callees

- `0x14000f7fc`
- `0x140024f90`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14005a6fc`
- `0x14005cf30`
- `0x14005cffc`
- `0x14005f4e4`
- `0x140062e54`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x14005f601`
- `ntoskrnl!PsIsHostSilo` at `0x14005f601`
- `ntoskrnl!PsGetJobSilo` at `0x14005f5d8`
- `ntoskrnl!PsGetJobSilo` at `0x14005f5d8`
- `ntoskrnl!ObIsKernelHandle` at `0x14005f51d`
- `ntoskrnl!ObIsKernelHandle` at `0x14005f51d`
- `ntoskrnl!PsJobType` at `0x14005f529`
- `ntoskrnl!ExAllocatePool2` at `0x14005f6c1`
- `ntoskrnl!ExAllocatePool2` at `0x14005f6c1`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f698`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f752`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f83c`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f8da`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f698`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f752`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f83c`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f8da`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005f54d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005f54d`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f574`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f5b9`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f76b`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f859`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f8f7`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f574`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f5b9`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f76b`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f859`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f8f7`

## string_xrefs

- `0x14005f7b4`: `newUnionCtx->GetSiloContext()->GetPathCache()`

## pseudocode

```c

```
