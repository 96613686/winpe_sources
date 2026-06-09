# __imp_load_NetpQueryService

- ea: `0x180021aaf`
- end: `0x180021abb`
- name: `__imp_load_NetpQueryService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18002196a`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpQueryService` at `0x180021aaf`

## pseudocode

```c
__int64 load_NetpQueryService()
{
  return _tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll();
}

```

## disassembly

```asm
0x180021aaf  lea     rax, __imp_NetpQueryService
0x180021ab6  jmp     __tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll
```
