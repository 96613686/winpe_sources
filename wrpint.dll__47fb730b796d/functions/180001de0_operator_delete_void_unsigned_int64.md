# operator delete(void *,unsigned __int64)

- ea: `0x180001de0`
- end: `0x180001de5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002694`
- `0x180002758`
- `0x180002a50`
- `0x1800048bc`
- `0x180004bfc`
- `0x180004fd0`
- `0x180005200`
- `0x180005260`
- `0x1800056a0`
- `0x180005920`
- `0x1800067ac`
- `0x180006e50`
- `0x180006f84`
- `0x1800070f0`
- `0x18000b720`
- `0x18000b760`
- `0x18001029c`
- `0x180010448`
- `0x180010750`
- `0x180010af0`
- `0x180010fe0`
- `0x180011cb0`
- `0x180011e10`
- `0x1800138a0`
- `0x180014054`
- `0x180014ce0`
- `0x180016930`

## callees

- `0x1800012f4`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001de0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
