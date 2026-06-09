# __imp_load_WlanGetSecuritySettings

- ea: `0x1800025d7`
- end: `0x1800025e3`
- name: `__imp_load_WlanGetSecuritySettings`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002407`

## import_xrefs

- `wlanapi!WlanGetSecuritySettings` at `0x1800025d7`

## pseudocode

```c
__int64 load_WlanGetSecuritySettings()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x1800025d7  lea     rax, __imp_WlanGetSecuritySettings
0x1800025de  jmp     __tailMerge_wlanapi_dll
```
