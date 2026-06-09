# CUserProfile::UsernameToSID(ushort const *,ushort const *)

- ea: `0x1800348dc`
- end: `0x180034a69`
- name: `?UsernameToSID@CUserProfile@@CAPEAXPEBG0@Z`
- size: `397`
- prototype: `void *__fastcall(LPCWSTR lpAccountName, LPCWSTR DomainName)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034620`

## callees

- `0x1800348dc`
- `0x1800772c0`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x180034a3d`
- `netutils!NetApiBufferFree` at `0x180034a3d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800349b5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180034a08`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800349b5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180034a08`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800349c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800349d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800349c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800349d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a2e`
- `logoncli!DsGetDcNameW` at `0x180034972`
- `logoncli!DsGetDcNameW` at `0x180034972`
- `KERNEL32!lstrcmpiW` at `0x180034950`
- `KERNEL32!lstrcmpiW` at `0x180034950`
- `KERNEL32!GetComputerNameW` at `0x180034934`
- `KERNEL32!GetComputerNameW` at `0x180034934`

## pseudocode

```c

```
