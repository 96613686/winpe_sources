# __imp_load_WlanQueryCreateAllUserProfileRestricted

- ea: `0x1800024aa`
- end: `0x1800024b6`
- name: `__imp_load_WlanQueryCreateAllUserProfileRestricted`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002407`

## import_xrefs

- `wlanapi!WlanQueryCreateAllUserProfileRestricted` at `0x1800024aa`

## pseudocode

```c
__int64 load_WlanQueryCreateAllUserProfileRestricted()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x1800024aa  lea     rax, __imp_WlanQueryCreateAllUserProfileRestricted
0x1800024b1  jmp     __tailMerge_wlanapi_dll
```
