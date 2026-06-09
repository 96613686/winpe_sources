# __imp_load_NetpControlServices

- ea: `0x180021a1f`
- end: `0x180021a2b`
- name: `__imp_load_NetpControlServices`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18002196a`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpControlServices` at `0x180021a1f`

## pseudocode

```c
__int64 load_NetpControlServices()
{
  return _tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll();
}

```

## disassembly

```asm
0x180021a1f  lea     rax, __imp_NetpControlServices
0x180021a26  jmp     __tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll
```
