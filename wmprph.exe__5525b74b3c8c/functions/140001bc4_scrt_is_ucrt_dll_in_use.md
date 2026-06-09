# __scrt_is_ucrt_dll_in_use

- ea: `0x140001bc4`
- end: `0x140001bd0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400013e0`
- `0x140001460`
- `0x140001594`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140001bc4  xor     eax, eax
0x140001bc6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140001bcc  setnz   al
0x140001bcf  retn
```
