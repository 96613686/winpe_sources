# __scrt_is_ucrt_dll_in_use

- ea: `0x180013120`
- end: `0x18001312c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800128a4`
- `0x1800128e4`
- `0x18001297c`
- `0x1800129cc`
- `0x180012a60`
- `0x180012b94`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180013120  xor     eax, eax
0x180013122  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180013128  setnz   al
0x18001312b  retn
```
