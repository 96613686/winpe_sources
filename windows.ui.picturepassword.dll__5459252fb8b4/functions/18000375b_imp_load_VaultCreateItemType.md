# __imp_load_VaultCreateItemType

- ea: `0x18000375b`
- end: `0x180003767`
- name: `__imp_load_VaultCreateItemType`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800036a6`

## import_xrefs

- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x18000375b`

## pseudocode

```c
__int64 load_VaultCreateItemType()
{
  return _tailMerge_ext_ms_win_security_vaultcli_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000375b  lea     rax, __imp_VaultCreateItemType
0x180003762  jmp     __tailMerge_ext_ms_win_security_vaultcli_l1_1_0_dll
```
