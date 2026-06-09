# _invalid_parameter_noinfo

- ea: `0x1400027fe`
- end: `0x140002804`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140006388`
- `0x140009838`
- `0x14000a158`
- `0x14000a2f8`
- `0x14000a4b8`
- `0x14000ac84`
- `0x14000b9b0`
- `0x14000bbb8`
- `0x14000c16c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1400027fe`

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
0x1400027fe  jmp     cs:__imp__invalid_parameter_noinfo
```
