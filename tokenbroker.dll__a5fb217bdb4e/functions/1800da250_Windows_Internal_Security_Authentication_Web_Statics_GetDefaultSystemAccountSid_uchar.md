# Windows::Internal::Security::Authentication::Web::Statics::GetDefaultSystemAccountSid(uchar *)

- ea: `0x1800da250`
- end: `0x1800da3d4`
- name: `?GetDefaultSystemAccountSid@Statics@Web@Authentication@Security@Internal@Windows@@QEAAJPEAE@Z`
- size: `388`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::Web::Statics *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006d630`

## callees

- `0x18000bd40`
- `0x180024000`
- `0x1800349d0`
- `0x180056ea4`
- `0x18008e690`
- `0x1800da250`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800da30a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800da30a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800da2db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800da357`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800da3ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800da2db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800da357`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800da3ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da3a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da3a3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x1800da2a5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x1800da2a5`

## string_xrefs

- `0x1800da2b5`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`

## pseudocode

```c

```
