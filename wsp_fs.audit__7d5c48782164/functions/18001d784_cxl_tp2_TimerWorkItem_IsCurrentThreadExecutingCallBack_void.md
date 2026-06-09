# cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)

- ea: `0x18001d784`
- end: `0x18001d7a6`
- name: `?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ`
- size: `34`
- prototype: `bool __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001d7e0`
- `0x18001e980`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d78d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d78d`

## pseudocode

```c
bool __fastcall cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(cxl::tp2::TimerWorkItem *this)
{
  return GetCurrentThreadId() == *((_DWORD *)this + 16);
}

```

## disassembly

```asm
0x18001d784  push    rbx
0x18001d786  sub     rsp, 20h
0x18001d78a  mov     rbx, rcx
0x18001d78d  call    cs:__imp_GetCurrentThreadId
0x18001d794  nop     dword ptr [rax+rax+00h]
0x18001d799  cmp     eax, [rbx+40h]
0x18001d79c  setz    al
0x18001d79f  add     rsp, 20h
0x18001d7a3  pop     rbx
0x18001d7a4  retn
```
