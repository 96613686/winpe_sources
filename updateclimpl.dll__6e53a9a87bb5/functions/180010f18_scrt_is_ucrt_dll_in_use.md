# __scrt_is_ucrt_dll_in_use

- ea: `0x180010f18`
- end: `0x180010f24`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180010340`
- `0x180010380`
- `0x180010424`
- `0x18001048c`
- `0x180010520`
- `0x180010654`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180010f18  xor     eax, eax
0x180010f1a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180010f20  setnz   al
0x180010f23  retn
```
