# operator delete(void *)

- ea: `0x14000126c`
- end: `0x140001271`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001260`
- `0x140001fc0`
- `0x140002090`
- `0x140008950`

## callees

- `0x1400021f4`

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
0x14000126c  jmp     free
```
