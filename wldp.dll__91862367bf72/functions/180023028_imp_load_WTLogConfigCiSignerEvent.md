# __imp_load_WTLogConfigCiSignerEvent

- ea: `0x180023028`
- end: `0x180023034`
- name: `__imp_load_WTLogConfigCiSignerEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180022ef5`

## import_xrefs

- `WINTRUST!WTLogConfigCiSignerEvent` at `0x180023028`

## pseudocode

```c
__int64 load_WTLogConfigCiSignerEvent()
{
  return _tailMerge_wintrust_dll();
}

```

## disassembly

```asm
0x180023028  lea     rax, __imp_WTLogConfigCiSignerEvent
0x18002302f  jmp     __tailMerge_wintrust_dll
```
