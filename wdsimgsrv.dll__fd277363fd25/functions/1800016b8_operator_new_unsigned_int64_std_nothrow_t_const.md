# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x1800016b8`
- end: `0x1800016bd`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c70`
- `0x180008d2c`
- `0x18000d39c`
- `0x18000d754`
- `0x18000d8c4`
- `0x18000d980`
- `0x18000db14`
- `0x18000dda0`
- `0x18000e054`
- `0x18000eb10`
- `0x18000f9f8`
- `0x180010120`
- `0x180010150`
- `0x1800102a0`

## callees

- `0x1800015d8`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  return operator new(a1, a2);
}

```

## disassembly

```asm
0x1800016b8  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
