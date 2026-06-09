# I_DeleteUnauthAttrByOID(void *,char const *)

- ea: `0x180039dd8`
- end: `0x180039f00`
- name: `?I_DeleteUnauthAttrByOID@@YAJPEAXPEBD@Z`
- size: `296`
- prototype: `__int64 __fastcall(HCRYPTMSG hCryptMsg, LPCSTR pszObjId)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180039cdc`
- `0x18003f904`

## callees

- `0x18001b420`
- `0x180039dd8`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039ec8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039ec8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039ed6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ea3`
- `CRYPT32!CryptMsgControl` at `0x180039e95`
- `CRYPT32!CryptMsgControl` at `0x180039e95`
- `CRYPT32!CertFindAttribute` at `0x180039e55`
- `CRYPT32!CertFindAttribute` at `0x180039e55`

## pseudocode

```c

```
