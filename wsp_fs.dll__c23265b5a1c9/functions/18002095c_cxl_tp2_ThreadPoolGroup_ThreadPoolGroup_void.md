# cxl::tp2::ThreadPoolGroup::~ThreadPoolGroup(void)

- ea: `0x18002095c`
- end: `0x1800209a8`
- name: `??1ThreadPoolGroup@tp2@cxl@@UEAA@XZ`
- size: `76`
- prototype: `void __fastcall(PVOID pvCleanupContext)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180020a60`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002098b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002098b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002097b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002097b`

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
0x18002095c  push    rbx
0x18002095e  sub     rsp, 20h
0x180020962  lea     rax, ??_7ThreadPoolGroup@tp2@cxl@@6B@; const cxl::tp2::ThreadPoolGroup::`vftable'
0x180020969  mov     rbx, rcx
0x18002096c  mov     [rcx], rax
0x18002096f  mov     r8, rcx; pvCleanupContext
0x180020972  mov     rcx, [rcx+18h]; ptpcg
0x180020976  mov     edx, 1; fCancelPendingCallbacks
0x18002097b  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180020982  nop     dword ptr [rax+rax+00h]
0x180020987  mov     rcx, [rbx+18h]; ptpcg
0x18002098b  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180020992  nop     dword ptr [rax+rax+00h]
0x180020997  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18002099e  mov     [rbx], rax
0x1800209a1  add     rsp, 20h
0x1800209a5  pop     rbx
0x1800209a6  retn
```
