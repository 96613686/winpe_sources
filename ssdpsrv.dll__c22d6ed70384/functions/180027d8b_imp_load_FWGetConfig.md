# __imp_load_FWGetConfig

- ea: `0x180027d8b`
- end: `0x180027d97`
- name: `__imp_load_FWGetConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180027cd6`

## import_xrefs

- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWGetConfig` at `0x180027d8b`

## pseudocode

```c
__int64 load_FWGetConfig()
{
  return _tailMerge_ext_ms_win_firewallapi_webproxy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180027d8b  lea     rax, __imp_FWGetConfig
0x180027d92  jmp     __tailMerge_ext_ms_win_firewallapi_webproxy_l1_1_0_dll
```
