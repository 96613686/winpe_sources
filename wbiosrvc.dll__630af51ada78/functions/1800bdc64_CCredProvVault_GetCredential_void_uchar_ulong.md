# CCredProvVault::GetCredential(void *,uchar *,ulong *)

- ea: `0x1800bdc64`
- end: `0x1800bdd87`
- name: `?GetCredential@CCredProvVault@@QEAAKPEAXPEAEPEAK@Z`
- size: `291`
- prototype: `unsigned int(CCredProvVault *__hidden this, void *, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bc1d0`
- `0x1800bc4a0`

## callees

- `0x180060dc8`
- `0x18006b0b5`
- `0x1800bdc64`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bdcbf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bdcbf`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItem` at `0x1800bdd1a`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItem` at `0x1800bdd1a`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x1800bdd67`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x1800bdd67`

## pseudocode

```c

```
