# __imp_load_VaultRemoveItem

- ea: `0x180003791`
- end: `0x18000379d`
- name: `__imp_load_VaultRemoveItem`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800036a6`

## import_xrefs

- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x180003791`

## pseudocode

```c
__int64 load_VaultRemoveItem()
{
  return _tailMerge_ext_ms_win_security_vaultcli_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003791  lea     rax, __imp_VaultRemoveItem
0x180003798  jmp     __tailMerge_ext_ms_win_security_vaultcli_l1_1_0_dll
```
