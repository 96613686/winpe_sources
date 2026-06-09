# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180001acc`
- end: `0x180001ad1`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800065b4`
- `0x18000abe4`
- `0x18000eecc`
- `0x18000f224`

## callees

- `0x180001ad8`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](size_t a1, const struct std::nothrow_t *a2)
{
  return operator new(a1, a2);
}

```

## disassembly

```asm
0x180001acc  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
