# operator delete(void *)

- ea: `0x180004f24`
- end: `0x180004f29`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004f18`
- `0x1800056f0`
- `0x1800127d0`
- `0x180013238`
- `0x180013260`
- `0x1800132a0`
- `0x180013bd4`

## callees

- `0x180005c94`

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
0x180004f24  jmp     free
```
