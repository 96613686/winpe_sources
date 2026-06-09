# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800100d4`
- end: `0x1800100d9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001dc0`
- `0x180002ea0`
- `0x180005970`
- `0x180005c20`
- `0x180006518`
- `0x180006810`
- `0x1800069a4`
- `0x1800072a0`
- `0x1800084c4`
- `0x1800085e8`
- `0x180008664`
- `0x180008928`
- `0x180008b78`
- `0x180008cb8`
- `0x180008e10`
- `0x1800092e0`
- `0x180009414`
- `0x1800095e0`
- `0x180009614`
- `0x180009940`
- `0x180009b70`
- `0x180009f10`
- `0x180016a9d`

## callees

- `0x180010ae8`

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
0x1800100d4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
