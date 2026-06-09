# __imp_load_RegWinStationSetSecurityW

- ea: `0x18000730f`
- end: `0x18000731b`
- name: `__imp_load_RegWinStationSetSecurityW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007200`

## import_xrefs

- `REGAPI!RegWinStationSetSecurityW` at `0x18000730f`

## pseudocode

```c
__int64 load_RegWinStationSetSecurityW()
{
  return _tailMerge_regapi_dll();
}

```

## disassembly

```asm
0x18000730f  lea     rax, __imp_RegWinStationSetSecurityW
0x180007316  jmp     __tailMerge_regapi_dll
```
