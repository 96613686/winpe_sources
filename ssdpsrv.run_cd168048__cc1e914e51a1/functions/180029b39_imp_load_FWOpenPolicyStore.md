# __imp_load_FWOpenPolicyStore

- ea: `0x180029b39`
- end: `0x180029b45`
- name: `__imp_load_FWOpenPolicyStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180029a96`

## import_xrefs

- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWOpenPolicyStore` at `0x180029b39`

## pseudocode

```c
__int64 load_FWOpenPolicyStore()
{
  return _tailMerge_ext_ms_win_firewallapi_webproxy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180029b39  lea     rax, __imp_FWOpenPolicyStore
0x180029b40  jmp     __tailMerge_ext_ms_win_firewallapi_webproxy_l1_1_0_dll
```
