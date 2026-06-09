# cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)

- ea: `0x180019b94`
- end: `0x180019baf`
- name: `?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ`
- size: `27`
- prototype: `bool __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180019be0`
- `0x18001acd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019b9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019b9d`

## pseudocode

```c
bool __fastcall cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(cxl::tp2::TimerWorkItem *this)
{
  return GetCurrentThreadId() == *((_DWORD *)this + 16);
}

```

## disassembly

```asm
0x180019b94  push    rbx
0x180019b96  sub     rsp, 20h
0x180019b9a  mov     rbx, rcx
0x180019b9d  call    cs:__imp_GetCurrentThreadId
0x180019ba3  cmp     eax, [rbx+40h]
0x180019ba6  setz    al
0x180019ba9  add     rsp, 20h
0x180019bad  pop     rbx
0x180019bae  retn
```
