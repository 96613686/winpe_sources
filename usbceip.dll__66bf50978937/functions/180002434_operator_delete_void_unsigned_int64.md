# operator delete(void *,unsigned __int64)

- ea: `0x180002434`
- end: `0x180002439`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003060`
- `0x1800030a0`
- `0x180003cc4`
- `0x180003fec`
- `0x180004060`
- `0x1800040e4`
- `0x180004210`
- `0x180005210`
- `0x180007264`
- `0x1800097ec`
- `0x1800099cc`
- `0x180009e50`
- `0x18000c1d8`
- `0x18000c228`
- `0x18000c7a8`
- `0x18001048e`
- `0x180010553`
- `0x1800106ad`
- `0x1800106d0`
- `0x1800106f3`
- `0x180010716`
- `0x18001074b`
- `0x18001076e`
- `0x1800107db`

## callees

- `0x1800023f4`

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
0x180002434  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
