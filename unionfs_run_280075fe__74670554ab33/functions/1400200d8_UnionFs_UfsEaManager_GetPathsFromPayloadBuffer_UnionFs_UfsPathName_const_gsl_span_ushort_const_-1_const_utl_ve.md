# UnionFs::UfsEaManager::GetPathsFromPayloadBuffer(UnionFs::UfsPathName const &,gsl::span<ushort const,-1> const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &)

- ea: `0x1400200d8`
- end: `0x1400202c0`
- name: `?GetPathsFromPayloadBuffer@UfsEaManager@UnionFs@@CAJAEBVUfsPathName@2@AEBV?$span@$$CBG$0?0@gsl@@AEAV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAVStackEventTracer@2@@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001fbb0`

## callees

- `0x14001012c`
- `0x14001c780`
- `0x14001f37c`
- `0x1400200d8`
- `0x140043dc0`
- `0x140056ac4`
- `0x140056afc`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400201c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002024a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400202a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400201c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002024a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400202a7`

## string_xrefs

- `0x14002025a`: `PUSH: Combining ScratchRootPath, tempPath`
- `0x14002020b`: `UnionFs::UfsEaManager::GetPathsFromPayloadBuffer`
- `0x14002026b`: `UnionFs::UfsEaManager::GetPathsFromPayloadBuffer`
- `0x1400201f8`: `ORIGIN: Adding payloadPath to vector`

## pseudocode

```c

```
