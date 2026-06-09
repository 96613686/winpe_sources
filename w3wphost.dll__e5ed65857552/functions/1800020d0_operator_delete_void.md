# operator delete(void *)

- ea: `0x1800020d0`
- end: `0x1800020d5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `18`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001ba0`
- `0x180001be0`
- `0x180002ae0`
- `0x180002dbc`
- `0x18000315c`
- `0x180003188`
- `0x1800031b0`
- `0x180004b20`
- `0x180004ee4`
- `0x180006aa0`
- `0x180007398`
- `0x180009fc8`
- `0x18000ac90`
- `0x18000acd0`
- `0x18000ad10`
- `0x18000ad50`
- `0x18000b090`
- `0x18000bf60`

## callees

- `0x1800025bc`

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
0x1800020d0  jmp     free_0
```
