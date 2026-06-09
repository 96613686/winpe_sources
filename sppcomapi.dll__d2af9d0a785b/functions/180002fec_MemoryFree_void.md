# MemoryFree(void *)

- ea: `0x180002fec`
- end: `0x18000301a`
- name: `?MemoryFree@@YAXPEAX@Z`
- size: `46`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ff5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ff5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000300e`

## pseudocode

```c
void __fastcall MemoryFree(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180002fec  push    rbx
0x180002fee  sub     rsp, 20h
0x180002ff2  mov     rbx, rcx
0x180002ff5  call    cs:__imp_GetProcessHeap
0x180002ffc  nop     dword ptr [rax+rax+00h]
0x180003001  mov     r8, rbx
0x180003004  xor     edx, edx
0x180003006  mov     rcx, rax
0x180003009  add     rsp, 20h
0x18000300d  pop     rbx
0x18000300e  jmp     cs:__imp_HeapFree
```
