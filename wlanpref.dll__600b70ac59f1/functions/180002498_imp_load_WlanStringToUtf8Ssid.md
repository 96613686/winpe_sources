# __imp_load_WlanStringToUtf8Ssid

- ea: `0x180002498`
- end: `0x1800024a4`
- name: `__imp_load_WlanStringToUtf8Ssid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002407`

## import_xrefs

- `wlanapi!WlanStringToUtf8Ssid` at `0x180002498`

## pseudocode

```c
__int64 load_WlanStringToUtf8Ssid()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x180002498  lea     rax, __imp_WlanStringToUtf8Ssid
0x18000249f  jmp     __tailMerge_wlanapi_dll
```
