# wil::is_default_system_managed_account(ushort const *)

- ea: `0x140013a10`
- end: `0x140013b43`
- name: `?is_default_system_managed_account@wil@@YA_NPEBG@Z`
- size: `307`
- prototype: `bool __fastcall(LPCWCH lpString1, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013b50`
- `0x14007c988`

## callees

- `0x140013a10`
- `0x140053720`
- `0x1400544e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140013b00`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140013b00`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013a9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013a9a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140013b2d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140013b2d`
- `SspiCli!GetUserNameExW` at `0x140013ae5`
- `SspiCli!GetUserNameExW` at `0x140013ae5`

## pseudocode

```c

```
