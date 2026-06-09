# operator delete(void *,std::nothrow_t const &)

- ea: `0x18000ed64`
- end: `0x18000ed69`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `21`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800013d0`
- `0x1800017b0`
- `0x180001a60`
- `0x180002358`
- `0x180002650`
- `0x1800027e4`
- `0x1800030c0`
- `0x18000467c`
- `0x1800048a8`
- `0x180004af8`
- `0x180004c38`
- `0x180004d90`
- `0x18000509c`
- `0x1800051d0`
- `0x1800053a0`
- `0x1800053d4`
- `0x180005700`
- `0x1800078ac`
- `0x180007b40`
- `0x1800087b0`
- `0x180016193`

## callees

- `0x18000f704`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18000ed64  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
