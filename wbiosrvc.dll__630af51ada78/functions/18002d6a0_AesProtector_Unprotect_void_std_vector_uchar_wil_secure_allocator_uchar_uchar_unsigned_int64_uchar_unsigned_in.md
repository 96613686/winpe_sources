# AesProtector::Unprotect(void *,std::vector<uchar,wil::secure_allocator<uchar>> &&,uchar *,unsigned __int64,uchar * *,unsigned __int64 *)

- ea: `0x18002d6a0`
- end: `0x18002d7a8`
- name: `?Unprotect@AesProtector@@UEAAJPEAX$$QEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAE_KPEAPEAEPEA_K@Z`
- size: `264`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, void *, __int64, unsigned __int8 *, RTL_SRWLOCK *, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002d6a0`
- `0x18002d7b0`
- `0x18002da38`
- `0x180060dc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d753`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002d727`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002d727`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002d6d1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002d6d1`
- `bcrypt!BCryptDestroyKey` at `0x18002d78f`
- `bcrypt!BCryptDestroyKey` at `0x18002d78f`

## pseudocode

```c

```
