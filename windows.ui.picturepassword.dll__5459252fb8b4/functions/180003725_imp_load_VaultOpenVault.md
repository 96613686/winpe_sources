# __imp_load_VaultOpenVault

- ea: `0x180003725`
- end: `0x180003731`
- name: `__imp_load_VaultOpenVault`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800036a6`

## import_xrefs

- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x180003725`

## pseudocode

```c
__int64 load_VaultOpenVault()
{
  return _tailMerge_ext_ms_win_security_vaultcli_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003725  lea     rax, __imp_VaultOpenVault
0x18000372c  jmp     __tailMerge_ext_ms_win_security_vaultcli_l1_1_0_dll
```
