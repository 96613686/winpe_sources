# __imp_load_WlanDeleteProfile

- ea: `0x1800025b3`
- end: `0x1800025bf`
- name: `__imp_load_WlanDeleteProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002407`

## import_xrefs

- `wlanapi!WlanDeleteProfile` at `0x1800025b3`

## pseudocode

```c
__int64 load_WlanDeleteProfile()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x1800025b3  lea     rax, __imp_WlanDeleteProfile
0x1800025ba  jmp     __tailMerge_wlanapi_dll
```
