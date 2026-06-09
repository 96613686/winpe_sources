# __imp_load_WTLogConfigCiScriptEvent2

- ea: `0x180023004`
- end: `0x180023010`
- name: `__imp_load_WTLogConfigCiScriptEvent2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180022ef5`

## import_xrefs

- `WINTRUST!WTLogConfigCiScriptEvent2` at `0x180023004`

## pseudocode

```c
__int64 load_WTLogConfigCiScriptEvent2()
{
  return _tailMerge_wintrust_dll();
}

```

## disassembly

```asm
0x180023004  lea     rax, __imp_WTLogConfigCiScriptEvent2
0x18002300b  jmp     __tailMerge_wintrust_dll
```
