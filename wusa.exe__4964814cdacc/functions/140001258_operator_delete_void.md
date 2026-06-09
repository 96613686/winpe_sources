# operator delete(void *)

- ea: `0x140001258`
- end: `0x14000125d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140005370`
- `0x14000ab54`
- `0x14000afc0`
- `0x14000f674`
- `0x1400108dc`
- `0x1400117c0`
- `0x14001181c`
- `0x140011c10`
- `0x140011d18`
- `0x140011dcc`
- `0x140012320`
- `0x14001259c`
- `0x140012b00`
- `0x140013020`

## callees

- `0x140001758`

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
0x140001258  jmp     free_0
```
