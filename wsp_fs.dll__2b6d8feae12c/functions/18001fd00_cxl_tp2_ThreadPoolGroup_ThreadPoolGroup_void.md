# cxl::tp2::ThreadPoolGroup::~ThreadPoolGroup(void)

- ea: `0x18001fd00`
- end: `0x18001fd3f`
- name: `??1ThreadPoolGroup@tp2@cxl@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(PVOID pvCleanupContext)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001fe00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001fd29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001fd29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001fd1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001fd1f`

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
0x18001fd00  push    rbx
0x18001fd02  sub     rsp, 20h
0x18001fd06  lea     rax, ??_7ThreadPoolGroup@tp2@cxl@@6B@; const cxl::tp2::ThreadPoolGroup::`vftable'
0x18001fd0d  mov     rbx, rcx
0x18001fd10  mov     [rcx], rax
0x18001fd13  mov     r8, rcx; pvCleanupContext
0x18001fd16  mov     rcx, [rcx+18h]; ptpcg
0x18001fd1a  mov     edx, 1; fCancelPendingCallbacks
0x18001fd1f  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001fd25  mov     rcx, [rbx+18h]; ptpcg
0x18001fd29  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001fd2f  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001fd36  mov     [rbx], rax
0x18001fd39  add     rsp, 20h
0x18001fd3d  pop     rbx
0x18001fd3e  retn
```
