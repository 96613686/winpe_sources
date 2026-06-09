# wil::details::FreeProcessHeap(void *)

- ea: `0x1800046f4`
- end: `0x180004722`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `46`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180002718`
- `0x1800038e8`
- `0x180003cd4`
- `0x180003d00`
- `0x180003fe4`
- `0x1800040d0`
- `0x180004174`
- `0x1800041a8`
- `0x180004300`
- `0x18000445c`
- `0x180004658`
- `0x1800046b8`
- `0x18000c6a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004716`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046fd`

## pseudocode

```c
void __fastcall wil::details::FreeProcessHeap(wil::details *this, void *a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, this);
}

```

## disassembly

```asm
0x1800046f4  push    rbx
0x1800046f6  sub     rsp, 20h
0x1800046fa  mov     rbx, rcx
0x1800046fd  call    cs:__imp_GetProcessHeap
0x180004704  nop     dword ptr [rax+rax+00h]
0x180004709  mov     r8, rbx
0x18000470c  xor     edx, edx
0x18000470e  mov     rcx, rax
0x180004711  add     rsp, 20h
0x180004715  pop     rbx
0x180004716  jmp     cs:__imp_HeapFree
```
