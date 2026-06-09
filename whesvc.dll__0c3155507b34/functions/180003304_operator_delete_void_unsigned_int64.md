# operator delete(void *,unsigned __int64)

- ea: `0x180003304`
- end: `0x180003309`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `87`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001f30`
- `0x180005360`
- `0x1800053a0`
- `0x180006c98`
- `0x180007770`
- `0x1800077d0`
- `0x180007810`
- `0x180008e00`
- `0x18000999c`
- `0x18000a4f0`
- `0x18000a750`
- `0x18000a7b0`
- `0x18000a80c`
- `0x18000c550`
- `0x18000c590`
- `0x18000fc50`
- `0x18000fd74`
- `0x18000ff00`
- `0x1800103f8`
- `0x1800113e8`
- `0x18001140c`
- `0x18001147c`
- `0x180011508`
- `0x180011578`
- `0x1800115e0`
- `0x18001164c`
- `0x18001176c`
- `0x18001180c`
- `0x180011904`
- `0x180011984`
- `0x1800119e8`
- `0x180011a6c`
- `0x180011bf8`
- `0x180011c90`
- `0x180011df8`
- `0x180011fd0`
- `0x180012010`
- `0x180012050`
- `0x180014a14`
- `0x180014ccc`
- `0x180014f94`
- `0x1800152f8`
- `0x180015d70`
- `0x180016208`
- `0x180016754`
- `0x180016b28`
- `0x180016c54`
- `0x180016d44`
- `0x180017180`
- `0x180017864`

## callees

- `0x180003920`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180003304  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
