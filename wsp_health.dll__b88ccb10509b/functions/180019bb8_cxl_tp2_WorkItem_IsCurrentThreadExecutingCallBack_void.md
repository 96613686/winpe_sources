# cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(void)

- ea: `0x180019bb8`
- end: `0x180019bd3`
- name: `?IsCurrentThreadExecutingCallBack@WorkItem@tp2@cxl@@QEBA_NXZ`
- size: `27`
- prototype: `bool __fastcall(cxl::tp2::WorkItem *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180019ce0`
- `0x18001add0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019bc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019bc1`

## pseudocode

```c
bool __fastcall cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(cxl::tp2::WorkItem *this)
{
  return GetCurrentThreadId() == *((_DWORD *)this + 24);
}

```

## disassembly

```asm
0x180019bb8  push    rbx
0x180019bba  sub     rsp, 20h
0x180019bbe  mov     rbx, rcx
0x180019bc1  call    cs:__imp_GetCurrentThreadId
0x180019bc7  cmp     eax, [rbx+60h]
0x180019bca  setz    al
0x180019bcd  add     rsp, 20h
0x180019bd1  pop     rbx
0x180019bd2  retn
```
