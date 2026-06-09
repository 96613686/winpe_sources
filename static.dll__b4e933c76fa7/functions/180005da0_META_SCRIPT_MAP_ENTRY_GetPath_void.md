# META_SCRIPT_MAP_ENTRY::GetPath(void)

- ea: `0x180005da0`
- end: `0x180005dab`
- name: `?GetPath@META_SCRIPT_MAP_ENTRY@@UEBAPEBGXZ`
- size: `11`
- prototype: `const unsigned __int16 *__fastcall(META_SCRIPT_MAP_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180005da4`

## pseudocode

```c
const unsigned __int16 *__fastcall META_SCRIPT_MAP_ENTRY::GetPath(META_SCRIPT_MAP_ENTRY *this)
{
  return STRU::QueryStr((META_SCRIPT_MAP_ENTRY *)((char *)this + 80));
}

```

## disassembly

```asm
0x180005da0  add     rcx, 50h ; 'P'
0x180005da4  jmp     cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
```
