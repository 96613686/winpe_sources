# __scrt_is_ucrt_dll_in_use

- ea: `0x180010880`
- end: `0x18001088c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800101f4`
- `0x180010234`
- `0x1800102cc`
- `0x18001031c`
- `0x1800103b0`
- `0x1800104e4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180010880  xor     eax, eax
0x180010882  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180010888  setnz   al
0x18001088b  retn
```
