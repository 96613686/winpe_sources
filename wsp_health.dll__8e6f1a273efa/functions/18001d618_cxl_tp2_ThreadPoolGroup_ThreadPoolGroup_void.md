# cxl::tp2::ThreadPoolGroup::~ThreadPoolGroup(void)

- ea: `0x18001d618`
- end: `0x18001d664`
- name: `??1ThreadPoolGroup@tp2@cxl@@UEAA@XZ`
- size: `76`
- prototype: `void __fastcall(PVOID pvCleanupContext)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001d720`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001d647`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001d647`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001d637`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001d637`

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
0x18001d618  push    rbx
0x18001d61a  sub     rsp, 20h
0x18001d61e  lea     rax, ??_7ThreadPoolGroup@tp2@cxl@@6B@; const cxl::tp2::ThreadPoolGroup::`vftable'
0x18001d625  mov     rbx, rcx
0x18001d628  mov     [rcx], rax
0x18001d62b  mov     r8, rcx; pvCleanupContext
0x18001d62e  mov     rcx, [rcx+18h]; ptpcg
0x18001d632  mov     edx, 1; fCancelPendingCallbacks
0x18001d637  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001d63e  nop     dword ptr [rax+rax+00h]
0x18001d643  mov     rcx, [rbx+18h]; ptpcg
0x18001d647  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001d64e  nop     dword ptr [rax+rax+00h]
0x18001d653  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001d65a  mov     [rbx], rax
0x18001d65d  add     rsp, 20h
0x18001d661  pop     rbx
0x18001d662  retn
```
