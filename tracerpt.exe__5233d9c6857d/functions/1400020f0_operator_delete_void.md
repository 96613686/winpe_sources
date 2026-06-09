# operator delete(void *)

- ea: `0x1400020f0`
- end: `0x1400020f5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400020e4`
- `0x140016ae0`
- `0x140017398`
- `0x140028030`
- `0x1400281b0`
- `0x140029fd8`
- `0x140030980`
- `0x1400318f0`
- `0x140032230`
- `0x14003252c`
- `0x140032660`
- `0x1400328a4`
- `0x140035300`
- `0x140035880`
- `0x140036258`
- `0x140037364`
- `0x140037698`

## callees

- `0x140002784`

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
0x1400020f0  jmp     free_0
```
