# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180002570`
- end: `0x180002575`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d68`
- `0x180004008`
- `0x18000422c`
- `0x1800043f4`
- `0x1800045d0`
- `0x180004a70`

## callees

- `0x180002548`

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
0x180002570  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
