# __imp_load_WlanGenerateProfileXmlBasicSettings

- ea: `0x1800024e0`
- end: `0x1800024ec`
- name: `__imp_load_WlanGenerateProfileXmlBasicSettings`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002407`

## import_xrefs

- `wlanapi!WlanGenerateProfileXmlBasicSettings` at `0x1800024e0`

## pseudocode

```c
__int64 load_WlanGenerateProfileXmlBasicSettings()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x1800024e0  lea     rax, __imp_WlanGenerateProfileXmlBasicSettings
0x1800024e7  jmp     __tailMerge_wlanapi_dll
```
