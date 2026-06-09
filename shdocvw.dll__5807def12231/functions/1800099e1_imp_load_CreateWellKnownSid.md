# __imp_load_CreateWellKnownSid

- ea: `0x1800099e1`
- end: `0x1800099ed`
- name: `__imp_load_CreateWellKnownSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000992c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800099e1`

## pseudocode

```c
__int64 load_CreateWellKnownSid()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800099e1  lea     rax, __imp_CreateWellKnownSid
0x1800099e8  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
