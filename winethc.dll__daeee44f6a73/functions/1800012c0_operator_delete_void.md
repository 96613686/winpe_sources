# operator delete(void *)

- ea: `0x1800012c0`
- end: `0x1800012c5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800012cc`
- `0x180002f7c`
- `0x180003490`
- `0x180003510`
- `0x1800045b0`
- `0x18000bff0`
- `0x18000d160`
- `0x18000dfe8`
- `0x18001098c`
- `0x180010a40`
- `0x180011b70`
- `0x180011ba0`

## callees

- `0x18000180e`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x1800012c0  jmp     free_0
```
