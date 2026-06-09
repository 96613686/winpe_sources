# operator delete(void *,unsigned __int64)

- ea: `0x180001968`
- end: `0x18000196d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002bf0`
- `0x180002c30`
- `0x180003210`
- `0x180004fe0`
- `0x1800064a0`
- `0x180008680`
- `0x1800089b0`
- `0x1800095d0`
- `0x180009ce0`
- `0x18000e500`
- `0x18000e690`
- `0x180011830`
- `0x180011ab0`
- `0x180012e30`

## callees

- `0x1800019c0`

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
0x180001968  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
