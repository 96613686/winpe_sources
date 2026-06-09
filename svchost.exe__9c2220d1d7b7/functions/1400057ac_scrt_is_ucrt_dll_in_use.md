# __scrt_is_ucrt_dll_in_use

- ea: `0x1400057ac`
- end: `0x1400057b8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140004fb4`
- `0x140005034`
- `0x140005168`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1400057ac  xor     eax, eax
0x1400057ae  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1400057b4  setnz   al
0x1400057b7  retn
```
