# wil::details::FreeProcessHeap(void *)

- ea: `0x1800043e4`
- end: `0x180004407`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x1800025b4`
- `0x180003628`
- `0x1800039d4`
- `0x1800039fc`
- `0x180003ce0`
- `0x180003dcc`
- `0x180003e70`
- `0x180003ea4`
- `0x180003ff8`
- `0x180004154`
- `0x180004350`
- `0x1800043b0`
- `0x18000bd0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004400`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043ed`

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
0x1800043e4  push    rbx
0x1800043e6  sub     rsp, 20h
0x1800043ea  mov     rbx, rcx
0x1800043ed  call    cs:__imp_GetProcessHeap
0x1800043f3  mov     r8, rbx
0x1800043f6  xor     edx, edx
0x1800043f8  mov     rcx, rax
0x1800043fb  add     rsp, 20h
0x1800043ff  pop     rbx
0x180004400  jmp     cs:__imp_HeapFree
```
