# _invalid_parameter_noinfo

- ea: `0x140002f0e`
- end: `0x140002f14`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x14000dcc8`
- `0x14000e154`
- `0x140011480`
- `0x140012334`
- `0x140012970`
- `0x1400147e0`
- `0x140014d88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x140002f0e`

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
0x140002f0e  jmp     cs:__imp__invalid_parameter_noinfo
```
