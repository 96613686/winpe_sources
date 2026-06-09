# __scrt_is_ucrt_dll_in_use

- ea: `0x180036a40`
- end: `0x180036a4c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180035eb8`
- `0x180035ef8`
- `0x180035f90`
- `0x180035fe0`
- `0x180036074`
- `0x1800361a8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180036a40  xor     eax, eax
0x180036a42  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180036a48  setnz   al
0x180036a4b  retn
```
