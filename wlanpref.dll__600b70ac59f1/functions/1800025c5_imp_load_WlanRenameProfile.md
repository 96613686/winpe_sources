# __imp_load_WlanRenameProfile

- ea: `0x1800025c5`
- end: `0x1800025d1`
- name: `__imp_load_WlanRenameProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002407`

## import_xrefs

- `wlanapi!WlanRenameProfile` at `0x1800025c5`

## pseudocode

```c
__int64 load_WlanRenameProfile()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x1800025c5  lea     rax, __imp_WlanRenameProfile
0x1800025cc  jmp     __tailMerge_wlanapi_dll
```
