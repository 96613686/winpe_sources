# wil::details::FreeProcessHeap(void *)

- ea: `0x18000e6bc`
- end: `0x18000e6df`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18000da18`
- `0x18000dabc`
- `0x18000db40`
- `0x18000db74`
- `0x18000dc3c`
- `0x18000fa94`
- `0x18000fbbc`
- `0x180010560`
- `0x180010840`
- `0x180010ebc`
- `0x180011678`
- `0x18001261c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e6d8`

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
0x18000e6bc  push    rbx
0x18000e6be  sub     rsp, 20h
0x18000e6c2  mov     rbx, rcx
0x18000e6c5  call    cs:__imp_GetProcessHeap
0x18000e6cb  mov     r8, rbx
0x18000e6ce  xor     edx, edx
0x18000e6d0  mov     rcx, rax
0x18000e6d3  add     rsp, 20h
0x18000e6d7  pop     rbx
0x18000e6d8  jmp     cs:__imp_HeapFree
```
