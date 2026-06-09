# operator delete(void *,unsigned __int64)

- ea: `0x180004f18`
- end: `0x180004f1d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800021c0`
- `0x180007460`
- `0x1800074a0`
- `0x1800074e0`
- `0x180007520`
- `0x180011050`
- `0x180011c98`
- `0x180012344`
- `0x180014080`
- `0x180014a84`
- `0x180014ea0`

## callees

- `0x180004f24`

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
0x180004f18  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
