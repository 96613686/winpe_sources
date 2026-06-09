# CUser::GetUserSidString(ushort *,ulong)

- ea: `0x14002f600`
- end: `0x14002f6ce`
- name: `?GetUserSidString@CUser@@QEAAKPEAGK@Z`
- size: `206`
- prototype: `unsigned int __fastcall(CUser *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140015a48`
- `0x1400619c0`
- `0x140062e20`
- `0x140064ce0`
- `0x140081b54`
- `0x14008ba7c`

## callees

- `0x1400057f4`
- `0x14002f600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f6a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f6c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f6a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f6c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002f674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002f674`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14002f61e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14002f61e`

## pseudocode

```c

```
