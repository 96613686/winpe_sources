# __scrt_is_ucrt_dll_in_use

- ea: `0x180002dd4`
- end: `0x180002de0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800025f0`
- `0x180002630`
- `0x1800026c8`
- `0x180002718`
- `0x1800027ac`
- `0x1800028e0`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002dd4  xor     eax, eax
0x180002dd6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002ddc  setnz   al
0x180002ddf  retn
```
