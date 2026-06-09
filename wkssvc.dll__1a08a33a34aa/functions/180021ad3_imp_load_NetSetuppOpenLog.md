# __imp_load_NetSetuppOpenLog

- ea: `0x180021ad3`
- end: `0x180021adf`
- name: `__imp_load_NetSetuppOpenLog`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18002196a`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppOpenLog` at `0x180021ad3`

## pseudocode

```c
__int64 load_NetSetuppOpenLog()
{
  return _tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll();
}

```

## disassembly

```asm
0x180021ad3  lea     rax, __imp_NetSetuppOpenLog
0x180021ada  jmp     __tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll
```
