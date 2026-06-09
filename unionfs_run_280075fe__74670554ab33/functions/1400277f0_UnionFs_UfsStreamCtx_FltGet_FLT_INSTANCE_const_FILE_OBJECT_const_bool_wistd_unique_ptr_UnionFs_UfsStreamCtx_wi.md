# UnionFs::UfsStreamCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x1400277f0`
- end: `0x140027936`
- name: `?FltGet@UfsStreamCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `326`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e2dc`
- `0x140027e58`
- `0x140034890`
- `0x140079600`

## callees

- `0x1400277f0`
- `0x140056a50`

## import_xrefs

- `FLTMGR!FltGetStreamContext` at `0x140027852`
- `FLTMGR!FltGetStreamContext` at `0x140027852`
- `FLTMGR!FltReleaseContext` at `0x140027820`
- `FLTMGR!FltReleaseContext` at `0x140027879`
- `FLTMGR!FltReleaseContext` at `0x1400278ed`
- `FLTMGR!FltReleaseContext` at `0x140027914`
- `FLTMGR!FltReleaseContext` at `0x140027820`
- `FLTMGR!FltReleaseContext` at `0x140027879`
- `FLTMGR!FltReleaseContext` at `0x1400278ed`
- `FLTMGR!FltReleaseContext` at `0x140027914`

## pseudocode

```c

```
