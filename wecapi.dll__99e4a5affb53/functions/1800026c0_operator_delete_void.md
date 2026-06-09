# operator delete(void *)

- ea: `0x1800026c0`
- end: `0x1800026e3`
- name: `??3@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(void *)`
- caller_count: `48`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001260`
- `0x1800012a0`
- `0x180001a30`
- `0x180001f00`
- `0x180001f2c`
- `0x180002024`
- `0x1800026f0`
- `0x180002fdc`
- `0x180003140`
- `0x180003178`
- `0x18000330c`
- `0x1800033ac`
- `0x1800033e4`
- `0x18000346c`
- `0x1800034d4`
- `0x180003590`
- `0x1800035c0`
- `0x180003c98`
- `0x180003ce4`
- `0x180003d68`
- `0x180003d78`
- `0x180003ee4`
- `0x180003f60`
- `0x180004004`
- `0x180006224`
- `0x18000625c`
- `0x1800062b0`
- `0x180006818`
- `0x180006fb8`
- `0x180007720`
- `0x18000908c`
- `0x180009ba0`
- `0x180009cb8`
- `0x180009d3c`
- `0x180009de0`
- `0x18000a380`
- `0x18000a44c`
- `0x18000a640`
- `0x18000a6b0`
- `0x18000a72c`
- `0x18000aaa0`
- `0x18000aea4`
- `0x18000b2b0`
- `0x18000b514`
- `0x18000b6b8`
- `0x18000c24f`
- `0x18000c2db`
- `0x18000c4bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026dc`

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
0x1800026c0  push    rbx
0x1800026c2  sub     rsp, 20h
0x1800026c6  mov     rbx, rcx
0x1800026c9  call    cs:__imp_GetProcessHeap
0x1800026cf  mov     r8, rbx
0x1800026d2  xor     edx, edx
0x1800026d4  mov     rcx, rax
0x1800026d7  add     rsp, 20h
0x1800026db  pop     rbx
0x1800026dc  jmp     cs:__imp_HeapFree
```
