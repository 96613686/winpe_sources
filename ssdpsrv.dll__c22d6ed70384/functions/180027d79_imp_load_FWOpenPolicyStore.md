# __imp_load_FWOpenPolicyStore

- ea: `0x180027d79`
- end: `0x180027d85`
- name: `__imp_load_FWOpenPolicyStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180027cd6`

## import_xrefs

- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWOpenPolicyStore` at `0x180027d79`

## pseudocode

```c
__int64 load_FWOpenPolicyStore()
{
  return _tailMerge_ext_ms_win_firewallapi_webproxy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180027d79  lea     rax, __imp_FWOpenPolicyStore
0x180027d80  jmp     __tailMerge_ext_ms_win_firewallapi_webproxy_l1_1_0_dll
```
