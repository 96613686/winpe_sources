# operator delete(void *)

- ea: `0x1800012d4`
- end: `0x1800012d9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800012e0`
- `0x1800029d8`
- `0x180002e9c`
- `0x1800044ac`
- `0x1800071d0`
- `0x180007230`
- `0x180007270`
- `0x1800081c0`
- `0x180009820`
- `0x180009968`
- `0x18000a70c`
- `0x18000a790`
- `0x18000ab80`
- `0x18000af70`
- `0x180010760`

## callees

- `0x18000181e`

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
0x1800012d4  jmp     free_0
```
