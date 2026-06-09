# _invalid_parameter_noinfo

- ea: `0x18000313a`
- end: `0x180003140`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180006a98`
- `0x18000a594`
- `0x18000bddc`
- `0x18000c420`
- `0x18000c5c4`
- `0x18000cba8`
- `0x18000d9d8`
- `0x18000dea4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000313a`

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
0x18000313a  jmp     cs:__imp__invalid_parameter_noinfo
```
