# cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)

- ea: `0x18001a5a4`
- end: `0x18001a5c6`
- name: `?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ`
- size: `34`
- prototype: `bool __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a600`
- `0x18001b7a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a5ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a5ad`

## pseudocode

```c
bool __fastcall cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(cxl::tp2::TimerWorkItem *this)
{
  return GetCurrentThreadId() == *((_DWORD *)this + 16);
}

```

## disassembly

```asm
0x18001a5a4  push    rbx
0x18001a5a6  sub     rsp, 20h
0x18001a5aa  mov     rbx, rcx
0x18001a5ad  call    cs:__imp_GetCurrentThreadId
0x18001a5b4  nop     dword ptr [rax+rax+00h]
0x18001a5b9  cmp     eax, [rbx+40h]
0x18001a5bc  setz    al
0x18001a5bf  add     rsp, 20h
0x18001a5c3  pop     rbx
0x18001a5c4  retn
```
