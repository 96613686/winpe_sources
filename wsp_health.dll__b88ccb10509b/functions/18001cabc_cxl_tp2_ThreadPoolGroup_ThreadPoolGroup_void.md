# cxl::tp2::ThreadPoolGroup::~ThreadPoolGroup(void)

- ea: `0x18001cabc`
- end: `0x18001cafb`
- name: `??1ThreadPoolGroup@tp2@cxl@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(PVOID pvCleanupContext)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001cbb0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001cae5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001cae5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001cadb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001cadb`

## pseudocode

```c
void __fastcall cxl::tp2::ThreadPoolGroup::~ThreadPoolGroup(PTP_CLEANUP_GROUP *pvCleanupContext)
{
  *pvCleanupContext = (PTP_CLEANUP_GROUP)&cxl::tp2::ThreadPoolGroup::`vftable';
  CloseThreadpoolCleanupGroupMembers(pvCleanupContext[3], 1, pvCleanupContext);
  CloseThreadpoolCleanupGroup(pvCleanupContext[3]);
  *pvCleanupContext = (PTP_CLEANUP_GROUP)&cxl::RefCounted::`vftable';
}

```

## disassembly

```asm
0x18001cabc  push    rbx
0x18001cabe  sub     rsp, 20h
0x18001cac2  lea     rax, ??_7ThreadPoolGroup@tp2@cxl@@6B@; const cxl::tp2::ThreadPoolGroup::`vftable'
0x18001cac9  mov     rbx, rcx
0x18001cacc  mov     [rcx], rax
0x18001cacf  mov     r8, rcx; pvCleanupContext
0x18001cad2  mov     rcx, [rcx+18h]; ptpcg
0x18001cad6  mov     edx, 1; fCancelPendingCallbacks
0x18001cadb  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001cae1  mov     rcx, [rbx+18h]; ptpcg
0x18001cae5  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001caeb  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001caf2  mov     [rbx], rax
0x18001caf5  add     rsp, 20h
0x18001caf9  pop     rbx
0x18001cafa  retn
```
