# _invalid_parameter_noinfo

- ea: `0x18000218a`
- end: `0x180002190`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180003a28`
- `0x180006d4c`
- `0x180008aac`
- `0x180008c50`
- `0x180008e0c`
- `0x180009638`
- `0x18000a780`
- `0x18000a988`
- `0x18000b298`
- `0x18000c7fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000218a`

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
0x18000218a  jmp     cs:__imp__invalid_parameter_noinfo
```
