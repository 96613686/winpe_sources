# operator delete(void *)

- ea: `0x1400039a0`
- end: `0x1400039c3`
- name: `??3@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(void *)`
- caller_count: `20`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140001738`
- `0x1400039cc`
- `0x140006008`
- `0x140006a30`
- `0x1400076b4`
- `0x14000cc80`
- `0x140015898`
- `0x140015cac`
- `0x1400196d8`
- `0x140019818`
- `0x14001b3f8`
- `0x14001c318`
- `0x140021b24`
- `0x140021b30`
- `0x14002b9ac`
- `0x14002f384`
- `0x14002fac4`
- `0x14002fc94`
- `0x140032a1a`
- `0x140032a99`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400039bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400039a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400039a9`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x1400039a0  push    rbx
0x1400039a2  sub     rsp, 20h
0x1400039a6  mov     rbx, rcx
0x1400039a9  call    cs:__imp_GetProcessHeap
0x1400039af  mov     r8, rbx
0x1400039b2  xor     edx, edx
0x1400039b4  mov     rcx, rax
0x1400039b7  add     rsp, 20h
0x1400039bb  pop     rbx
0x1400039bc  jmp     cs:__imp_HeapFree
```
