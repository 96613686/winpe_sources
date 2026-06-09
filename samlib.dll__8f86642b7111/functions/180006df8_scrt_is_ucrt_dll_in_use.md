# __scrt_is_ucrt_dll_in_use

- ea: `0x180006df8`
- end: `0x180006e04`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000674c`
- `0x18000678c`
- `0x180006824`
- `0x180006874`
- `0x180006908`
- `0x180006a3c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180006df8  xor     eax, eax
0x180006dfa  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180006e00  setnz   al
0x180006e03  retn
```
