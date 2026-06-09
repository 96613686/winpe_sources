# operator delete(void *)

- ea: `0x180005f98`
- end: `0x180005fab`
- name: `??3@YAXPEAX@Z`
- size: `19`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fa4`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  HeapFree(s_hHeapToUse, 0, a1);
}

```

## disassembly

```asm
0x180005f98  mov     r8, rcx
0x180005f9b  xor     edx, edx
0x180005f9d  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; void * s_hHeapToUse
0x180005fa4  jmp     cs:__imp_HeapFree
```
