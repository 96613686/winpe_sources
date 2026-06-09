# operator delete(void *)

- ea: `0x1400058a4`
- end: `0x1400058a9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004620`
- `0x1400057a0`

## callees

- `0x1400056d6`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x1400058a4  jmp     free
```
