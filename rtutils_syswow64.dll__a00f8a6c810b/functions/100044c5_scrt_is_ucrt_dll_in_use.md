# ___scrt_is_ucrt_dll_in_use

- ea: `0x100044c5`
- end: `0x100044d1`
- name: `___scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x10003dbe`
- `0x10003df8`
- `0x10003e70`
- `0x10003eac`
- `0x10003f29`
- `0x10004055`

## pseudocode

```c
BOOL __scrt_is_ucrt_dll_in_use()
{
  return __scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x100044c5  xor     eax, eax
0x100044c7  cmp     ___scrt_ucrt_dll_is_in_use, eax
0x100044cd  setnz   al
0x100044d0  retn
```
