# UnionFs::UnionFsFilter::CreateBootUnion(utl::vector<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>,utl::allocator<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>>> const &,UnionFs::StackEventTracer &)

- ea: `0x140008b3c`
- end: `0x140008c5f`
- name: `?CreateBootUnion@UnionFsFilter@UnionFs@@AEAAJAEBV?$vector@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000b218`

## callees

- `0x140008b3c`
- `0x140008c68`
- `0x1400093fc`
- `0x140056afc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008bb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008bb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c40`

## string_xrefs

- `0x140008b83`: `PUSH: CreateBootUnionConfigMessage`
- `0x140008b94`: `UnionFs::UnionFsFilter::CreateBootUnion`
- `0x140008c06`: `UnionFs::UnionFsFilter::CreateBootUnion`

## pseudocode

```c

```
