# _invalid_parameter_noinfo

- ea: `0x18000204a`
- end: `0x180002050`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003688`
- `0x1800049f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000204a`

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
0x18000204a  jmp     cs:__imp__invalid_parameter_noinfo
```
