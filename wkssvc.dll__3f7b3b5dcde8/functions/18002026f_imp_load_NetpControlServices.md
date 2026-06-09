# __imp_load_NetpControlServices

- ea: `0x18002026f`
- end: `0x18002027b`
- name: `__imp_load_NetpControlServices`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800201ba`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpControlServices` at `0x18002026f`

## pseudocode

```c
__int64 load_NetpControlServices()
{
  return _tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll();
}

```

## disassembly

```asm
0x18002026f  lea     rax, __imp_NetpControlServices
0x180020276  jmp     __tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll
```
