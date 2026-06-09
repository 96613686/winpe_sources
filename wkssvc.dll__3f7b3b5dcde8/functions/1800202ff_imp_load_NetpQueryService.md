# __imp_load_NetpQueryService

- ea: `0x1800202ff`
- end: `0x18002030b`
- name: `__imp_load_NetpQueryService`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800201ba`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpQueryService` at `0x1800202ff`

## pseudocode

```c
__int64 load_NetpQueryService()
{
  return _tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800202ff  lea     rax, __imp_NetpQueryService
0x180020306  jmp     __tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll
```
