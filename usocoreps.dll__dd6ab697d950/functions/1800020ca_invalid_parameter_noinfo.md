# _invalid_parameter_noinfo

- ea: `0x1800020ca`
- end: `0x1800020d0`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800043ec`
- `0x180004714`
- `0x180004a94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800020ca`

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
0x1800020ca  jmp     cs:__imp__invalid_parameter_noinfo
```
