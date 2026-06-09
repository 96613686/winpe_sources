# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x1800020f4`
- end: `0x1800020f9`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000145c`

## callees

- `0x180002160`

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
0x1800020f4  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
