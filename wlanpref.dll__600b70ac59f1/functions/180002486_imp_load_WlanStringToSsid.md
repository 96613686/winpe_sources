# __imp_load_WlanStringToSsid

- ea: `0x180002486`
- end: `0x180002492`
- name: `__imp_load_WlanStringToSsid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002407`

## import_xrefs

- `wlanapi!WlanStringToSsid` at `0x180002486`

## pseudocode

```c
__int64 load_WlanStringToSsid()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x180002486  lea     rax, __imp_WlanStringToSsid
0x18000248d  jmp     __tailMerge_wlanapi_dll
```
