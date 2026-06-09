# __imp_load_FWGetGlobalConfig

- ea: `0x180027d67`
- end: `0x180027d73`
- name: `__imp_load_FWGetGlobalConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180027cd6`

## import_xrefs

- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWGetGlobalConfig` at `0x180027d67`

## pseudocode

```c
__int64 load_FWGetGlobalConfig()
{
  return _tailMerge_ext_ms_win_firewallapi_webproxy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180027d67  lea     rax, __imp_FWGetGlobalConfig
0x180027d6e  jmp     __tailMerge_ext_ms_win_firewallapi_webproxy_l1_1_0_dll
```
