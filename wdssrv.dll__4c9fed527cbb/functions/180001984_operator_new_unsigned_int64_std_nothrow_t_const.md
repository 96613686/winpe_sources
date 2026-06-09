# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180001984`
- end: `0x180001989`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c24`
- `0x180003680`
- `0x180004818`
- `0x180008c58`
- `0x18000b1ec`
- `0x180010048`
- `0x180011600`
- `0x180012084`
- `0x1800123d8`
- `0x1800124ac`
- `0x180012790`
- `0x180015b70`
- `0x180015c50`
- `0x180016b08`

## callees

- `0x18000195c`

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
0x180001984  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
