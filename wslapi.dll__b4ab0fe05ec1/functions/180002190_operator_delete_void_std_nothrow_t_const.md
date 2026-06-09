# operator delete(void *,std::nothrow_t const &)

- ea: `0x180002190`
- end: `0x180002195`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800035b0`
- `0x1800035f0`
- `0x1800060e0`
- `0x180006830`
- `0x180006870`
- `0x180006900`
- `0x18000692c`
- `0x180006bd4`
- `0x180006f40`
- `0x180006f80`
- `0x180007030`
- `0x180007094`
- `0x1800070c0`
- `0x180007900`
- `0x180007940`
- `0x180007974`
- `0x1800079a0`
- `0x1800085ac`
- `0x1800088d0`
- `0x180008910`
- `0x180009be8`
- `0x18000a4d4`
- `0x18000c14f`

## callees

- `0x18000293c`

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
0x180002190  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
