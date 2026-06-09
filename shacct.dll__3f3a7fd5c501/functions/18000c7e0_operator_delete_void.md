# operator delete(void *)

- ea: `0x18000c7e0`
- end: `0x18000c7e5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `16`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005e60`
- `0x180008ce0`
- `0x180008d30`
- `0x180009b20`
- `0x180009b70`
- `0x180009bc0`
- `0x18000b310`
- `0x18000c264`
- `0x18000e630`
- `0x18000f130`
- `0x180013c50`
- `0x180014780`
- `0x1800147c0`
- `0x180014d10`
- `0x180014d50`
- `0x180016e60`

## callees

- `0x18000cb54`

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
0x18000c7e0  jmp     free
```
