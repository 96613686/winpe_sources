# WLFreeProfileXml

- ea: `0x180006850`
- end: `0x180006857`
- name: `WLFreeProfileXml`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `wlanapi!WpFreeMemory` at `0x180006850`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall WLFreeProfileXml(__int64 a1)
{
  return WpFreeMemory(a1);
}

```

## disassembly

```asm
0x180006850  jmp     cs:__imp_WpFreeMemory
```
