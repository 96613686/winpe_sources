# __scrt_is_ucrt_dll_in_use

- ea: `0x140002334`
- end: `0x140002340`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001974`
- `0x1400019f4`
- `0x140001b28`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002334  xor     eax, eax
0x140002336  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x14000233c  setnz   al
0x14000233f  retn
```
