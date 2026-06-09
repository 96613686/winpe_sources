# cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(void)

- ea: `0x18001a5cc`
- end: `0x18001a5ee`
- name: `?IsCurrentThreadExecutingCallBack@WorkItem@tp2@cxl@@QEBA_NXZ`
- size: `34`
- prototype: `bool __fastcall(cxl::tp2::WorkItem *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a720`
- `0x18001b8b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a5d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a5d5`

## pseudocode

```c
bool __fastcall cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(cxl::tp2::WorkItem *this)
{
  return GetCurrentThreadId() == *((_DWORD *)this + 24);
}

```

## disassembly

```asm
0x18001a5cc  push    rbx
0x18001a5ce  sub     rsp, 20h
0x18001a5d2  mov     rbx, rcx
0x18001a5d5  call    cs:__imp_GetCurrentThreadId
0x18001a5dc  nop     dword ptr [rax+rax+00h]
0x18001a5e1  cmp     eax, [rbx+60h]
0x18001a5e4  setz    al
0x18001a5e7  add     rsp, 20h
0x18001a5eb  pop     rbx
0x18001a5ec  retn
```
