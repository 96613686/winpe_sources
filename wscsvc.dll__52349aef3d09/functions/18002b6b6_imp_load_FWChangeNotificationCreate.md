# __imp_load_FWChangeNotificationCreate

- ea: `0x18002b6b6`
- end: `0x18002b6c2`
- name: `__imp_load_FWChangeNotificationCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002b613`

## import_xrefs

- `FirewallAPI!FWChangeNotificationCreate` at `0x18002b6b6`

## pseudocode

```c
__int64 load_FWChangeNotificationCreate()
{
  return _tailMerge_firewallapi_dll();
}

```

## disassembly

```asm
0x18002b6b6  lea     rax, __imp_FWChangeNotificationCreate
0x18002b6bd  jmp     __tailMerge_firewallapi_dll
```
