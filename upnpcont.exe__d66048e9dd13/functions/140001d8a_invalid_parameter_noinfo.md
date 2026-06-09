# _invalid_parameter_noinfo

- ea: `0x140001d8a`
- end: `0x140001d90`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000550c`
- `0x140005834`
- `0x140005bb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x140001d8a`

## pseudocode

```c
// attributes: thunk
void __cdecl invalid_parameter_noinfo()
{
  _invalid_parameter_noinfo();
}

```

## disassembly

```asm
0x140001d8a  jmp     cs:__imp__invalid_parameter_noinfo
```
