# _invalid_parameter_noinfo

- ea: `0x140001e22`
- end: `0x140001e28`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x14000491c`
- `0x140004d0c`
- `0x140005034`
- `0x1400055c8`
- `0x140007258`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x140001e22`

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
0x140001e22  jmp     cs:__imp__invalid_parameter_noinfo
```
