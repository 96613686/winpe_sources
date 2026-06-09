# _invalid_parameter_noinfo

- ea: `0x180002846`
- end: `0x18000284c`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180005fa0`
- `0x180007e68`
- `0x18000800c`
- `0x1800081cc`
- `0x180008a58`
- `0x18000b3d8`
- `0x18000b5e0`
- `0x18000c468`
- `0x18000d1bc`
- `0x180017a40`
- `0x180017c40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002846`

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
0x180002846  jmp     cs:__imp__invalid_parameter_noinfo
```
