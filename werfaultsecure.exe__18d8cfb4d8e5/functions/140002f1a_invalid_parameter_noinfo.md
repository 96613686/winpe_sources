# _invalid_parameter_noinfo

- ea: `0x140002f1a`
- end: `0x140002f20`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140004978`
- `0x14000a0dc`
- `0x14000acb4`
- `0x14000ae58`
- `0x14000b430`
- `0x14000c67c`
- `0x14000da44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x140002f1a`

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
0x140002f1a  jmp     cs:__imp__invalid_parameter_noinfo
```
