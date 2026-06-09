# operator delete(void *)

- ea: `0x180001c30`
- end: `0x180001c45`
- name: `??3@YAXPEAX@Z`
- size: `21`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002594`
- `0x1800025a0`

## callees

- `0x180001c30`
- `0x180001c50`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    CWinHeap::Free((CWinHeap *)&g_heap, a1);
}

```

## disassembly

```asm
0x180001c30  test    rcx, rcx
0x180001c33  jz      short locret_180001C44
0x180001c35  mov     rdx, rcx; void *
0x180001c38  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180001c3f  jmp     ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180001c44  retn
```
