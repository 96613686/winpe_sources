# __scrt_is_ucrt_dll_in_use

- ea: `0x1004272e0`
- end: `0x1004272ec`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x100426d04`
- `0x100426d44`
- `0x100426de8`
- `0x100426e50`
- `0x100426ef4`
- `0x100427028`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1004272e0  xor     eax, eax
0x1004272e2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1004272e8  setnz   al
0x1004272eb  retn
```
