# __imp_load_WlanOpenHandle

- ea: `0x18000257d`
- end: `0x180002589`
- name: `__imp_load_WlanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002407`

## import_xrefs

- `wlanapi!WlanOpenHandle` at `0x18000257d`

## pseudocode

```c
__int64 load_WlanOpenHandle()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x18000257d  lea     rax, __imp_WlanOpenHandle
0x180002584  jmp     __tailMerge_wlanapi_dll
```
