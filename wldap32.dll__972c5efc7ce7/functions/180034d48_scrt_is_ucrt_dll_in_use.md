# __scrt_is_ucrt_dll_in_use

- ea: `0x180034d48`
- end: `0x180034d54`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180034534`
- `0x180034574`
- `0x18003460c`
- `0x18003465c`
- `0x1800346f0`
- `0x180034824`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180034d48  xor     eax, eax
0x180034d4a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180034d50  setnz   al
0x180034d53  retn
```
