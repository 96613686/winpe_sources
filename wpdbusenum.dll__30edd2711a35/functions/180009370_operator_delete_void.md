# operator delete(void *)

- ea: `0x180009370`
- end: `0x180009375`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000937c`
- `0x180009ba0`
- `0x180012130`
- `0x180012160`

## callees

- `0x18000a156`

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
0x180009370  jmp     free
```
