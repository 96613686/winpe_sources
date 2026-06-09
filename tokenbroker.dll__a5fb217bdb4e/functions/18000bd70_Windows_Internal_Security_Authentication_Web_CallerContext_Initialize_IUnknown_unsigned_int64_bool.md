# Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)

- ea: `0x18000bd70`
- end: `0x18000d247`
- name: `?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z`
- size: `5335`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::Web::CallerContext *this, struct IUnknown *, __int64, char)`
- caller_count: `59`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008130`
- `0x180008730`
- `0x180009f40`
- `0x18001e9f8`
- `0x18001ef40`
- `0x180020840`
- `0x180020d90`
- `0x180021750`
- `0x1800232e8`
- `0x180024c88`
- `0x18002eb80`
- `0x18002f450`
- `0x18002fc10`
- `0x180033800`
- `0x180054240`
- `0x180057580`
- `0x1800586a8`
- `0x18005a26c`
- `0x18005aa84`
- `0x18005ed54`
- `0x180065dc0`
- `0x180069a40`
- `0x18006abe0`
- `0x18006b0c0`
- `0x1800803f0`
- `0x18008110c`
- `0x180081890`
- `0x180082e10`
- `0x180083f90`
- `0x1800845d0`
- `0x180084d40`
- `0x180085c40`
- `0x180086a40`
- `0x180087800`
- `0x180088620`
- `0x180089730`
- `0x1800899a0`
- `0x18008b9a0`
- `0x18008be40`
- `0x18008c150`
- `0x18008c410`
- `0x18008c7d0`
- `0x18008d0b0`
- `0x18008dc10`
- `0x1800a6a30`
- `0x1800a7600`
- `0x1800aef20`
- `0x1800bbcb0`
- `0x1800bd970`
- `0x1800bdfe4`

## callees

- `0x18000bd40`
- `0x18000bd70`
- `0x18000d250`
- `0x18000d2b0`
- `0x18000e140`
- `0x18000e350`
- `0x18000e390`
- `0x180024000`
- `0x180040790`
- `0x1800565a0`
- `0x18007c0f0`
- `0x18007c220`
- `0x18008e674`
- `0x18008e690`
- `0x18008e6cc`
- `0x1800af930`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c01f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c0b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c4f4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c8e1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c01f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c0b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c4f4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c8e1`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000c277`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000c277`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000bed2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000bed2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bf9d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bf9d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000c2f7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000c2f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000be32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bf42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000be32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bf42`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c19f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c472`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c815`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c19f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c472`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c815`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000be48`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000bf58`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000be48`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000bf58`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000be87`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000be87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000be74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000be74`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000d1b3`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000d1b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cd58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cd58`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c6c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ceab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d01a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d09a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ceab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d01a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d09a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18000c087`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18000c087`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c7a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c7a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c16b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c18a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c3dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c3ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c5ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c678`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c7e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c939`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cbe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cc00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d05f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d0ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c16b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c18a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c3dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c3ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c5ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c678`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c7e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c939`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cbe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cc00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d05f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d0ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000c609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000c61c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000c9b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000c609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000c61c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000c9b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c11b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c6d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c11b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c6d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d225`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d23b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d225`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d23b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c17b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c45d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c5bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c669`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c70a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c949`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cfdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c17b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c45d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c5bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c669`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c70a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c949`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cfdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0e0`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18000c2d2`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18000c2d2`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000c2c0`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000c2c0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000c884`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000c884`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18000bdf6`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18000bdf6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d167`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d17a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d167`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d17a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c0d0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c54e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c0d0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c54e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000c32a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000c32a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000c8af`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000c8af`

## string_xrefs

- `0x18000c151`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000c5a0`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000c63f`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000c7ca`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000c91f`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000c9ed`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000cad1`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000cb33`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000cbce`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000ccb2`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000cd74`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000cdea`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000ce65`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000ced6`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000cf4d`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000cfc4`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000d045`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000d0c5`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000c863`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x18000c99c`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x18000ca64`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x18000cab2`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x18000cb17`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(
        Windows::Internal::Security::Authentication::Web::CallerContext *this,
        struct IUnknown *a2,
        __int64 a3,
        char a4)
{
  int v5; // eax
  int v6; // edi
  bool v7; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v11; // r9
  const char *v12; // r9
  HANDLE v13; // rcx
  HANDLE v14; // rax
  signed int v15; // eax
  signed int v16; // ebx
  signed int v17; // eax
  const char *v18; // r9
  PSRWLOCK v19; // rbx
  int v20; // eax
  HSTRING v21; // rdi
  unsigned __int64 v22; // rsi
  int v23; // r14d
  _OWORD *v24; // r13
  HSTRING v25; // rbx
  const char *v26; // r9
  void *v27; // rcx
  __int64 v29; // rsi
  void *v30; // r15
  __m128i *i; // rsi
  HANDLE v32; // rcx
  __int32 v33; // r14d
  PSID v34; // rsi
  PSID_IDENTIFIER_AUTHORITY v35; // rax
  int v36; // ecx
  bool v37; // cc
  HANDLE v38; // rcx
  int v39; // esi
  _OWORD *v40; // r14
  void **v41; // r12
  void *v42; // rbx
  char *v43; // rcx
  const char *v44; // r9
  _OWORD *v45; // rcx
  HANDLE v46; // rcx
  unsigned __int64 v47; // rdx
  HRESULT v48; // r15d
  HANDLE v49; // rcx
  PCWSTR StringRawBuffer; // rax
  const char *v51; // r9
  int v52; // eax
  signed int v53; // eax
  signed int v54; // eax
  signed int v55; // eax
  signed int v56; // eax
  signed int v57; // eax
  signed int v58; // eax
  unsigned int TokenType; // [rsp+20h] [rbp-E0h]
  int TokenTypea; // [rsp+20h] [rbp-E0h]
  int TokenTypeb; // [rsp+20h] [rbp-E0h]
  int TokenTypec; // [rsp+20h] [rbp-E0h]
  int TokenTyped; // [rsp+20h] [rbp-E0h]
  int TokenTypee; // [rsp+20h] [rbp-E0h]
  const char *phNewToken; // [rsp+28h] [rbp-D8h]
  int v66; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hExistingToken; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *v69; // [rsp+58h] [rbp-A8h] BYREF
  INT32 result[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v71; // [rsp+68h] [rbp-98h]
  HANDLE Token; // [rsp+70h] [rbp-90h] BYREF
  char v73; // [rsp+78h] [rbp-88h]
  LPWSTR StringSid; // [rsp+80h] [rbp-80h] BYREF
  DWORD ReturnLength; // [rsp+88h] [rbp-78h] BYREF
  int TokenInformation; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v77; // [rsp+90h] [rbp-70h] BYREF
  HANDLE v78; // [rsp+98h] [rbp-68h]
  HSTRING v79; // [rsp+A0h] [rbp-60h]
  __m128i si128; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v81[3]; // [rsp+B8h] [rbp-48h] BYREF
  char v82; // [rsp+D0h] [rbp-30h]
  HSTRING string; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  PSID v85[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v86; // [rsp+110h] [rbp+10h]
  __int128 v87; // [rsp+120h] [rbp+20h]
  _BYTE v88[28]; // [rsp+130h] [rbp+30h] BYREF
  PSID Sid[12]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v71 = a4;
  v69 = a2;
  v77 = a3;
  v66 = 0;
  TokenHandle = 0;
  v81[0] = &v66;
  v81[1] = &v69;
  v81[2] = &TokenHandle;
  v82 = 1;
  if ( !a2 )
  {
    v66 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
      (const char *)0x80070057LL,
      TokenType);
    if ( v66 < 0 )
      LogCallerInfo(v69, v66, TokenHandle);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
    return 2147942487LL;
  }
  result[0] = 0;
  v5 = CoImpersonateClientOfObject(a2, result);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v5,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v6,
      TokenTypee);
    v66 = v6;
    goto LABEL_214;
  }
  v7 = result[0] != 0;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    if ( !v7 )
      goto LABEL_15;
    goto LABEL_274;
  }
  LastError = GetLastError();
  if ( v7 || LastError != 1008 )
  {
    if ( LastError )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x188,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
             (const char *)LastError,
             TokenType);
      if ( v7 )
        CoRevertToSelf();
      goto LABEL_18;
    }
    if ( !v7 )
      goto LABEL_15;
LABEL_274:
    CoRevertToSelf();
    goto LABEL_15;
  }
  hExistingToken = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x2000Eu, &hExistingToken) )
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x182,
           (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
           v11);
    v13 = hExistingToken;
    if ( hExistingToken )
LABEL_17:
      CloseHandle(v13);
LABEL_18:
    v66 = v6;
    if ( v6 >= 0 )
      goto LABEL_19;
LABEL_214:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
      (const char *)(unsigned int)v6,
      TokenType);
    if ( v66 < 0 )
      LogCallerInfo(v69, v66, TokenHandle);
    goto LABEL_216;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle);
  TokenHandle = 0;
  if ( !DuplicateTokenEx(hExistingToken, 0x2000Cu, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x184,
           (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
           v12);
    v13 = hExistingToken;
    if ( !hExistingToken )
      goto LABEL_18;
    goto LABEL_17;
  }
  if ( !hExistingToken )
  {
LABEL_15:
    v66 = 0;
    goto LABEL_19;
  }
  CloseHandle(hExistingToken);
  v66 = 0;
LABEL_19:
  v73 = 0;
  Token = 0;
  v14 = GetCurrentThread();
  if ( OpenThreadToken(v14, 0xF01FFu, 1, &Token) )
    goto LABEL_23;
  v15 = GetLastError();
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  if ( v15 == -2147023888 )
  {
LABEL_23:
    v16 = 0;
  }
  else
  {
    v17 = GetLastError();
    v16 = v17;
    if ( v17 > 0 )
      v16 = (unsigned __int16)v17 | 0x80070000;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E5,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
        (const char *)(unsigned int)v16,
        TokenType);
      v66 = v16;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEE,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
        (const char *)(unsigned int)v16,
        TokenTyped);
      Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
      if ( v66 < 0 )
        LogCallerInfo(v69, v66, TokenHandle);
      goto LABEL_268;
    }
  }
  if ( !RevertToSelf() )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
      v18);
  v73 = 1;
  v66 = v16;
  v19 = `Windows::Internal::Security::Authentication::Web::Statics::GetInstance'::`2'::sInstance;
  if ( !`Windows::Internal::Security::Authentication::Web::Statics::GetInstance'::`2'::sInstance )
  {
    v19 = (PSRWLOCK)operator new(0x58u);
    v78 = v19;
    InitializeSRWLock(v19);
    v19[1].Ptr = 0;
    LOBYTE(v19[2].Ptr) = 0;
    BYTE5(v19[10].Ptr) = 0;
    `Windows::Internal::Security::Authentication::Web::Statics::GetInstance'::`2'::sInstance = v19;
  }
  if ( !LOBYTE(v19[2].Ptr) )
  {
    AcquireSRWLockExclusive(v19);
    v6 = Windows::Internal::String::Initialize((Windows::Internal::String *)&v19[1], L"NO_APPLICATION", 0xEu);
    LOBYTE(v19[2].Ptr) = v6 >= 0;
    ReleaseSRWLockExclusive(v19);
    v66 = v6;
    if ( v6 >= 0 )
      goto LABEL_32;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF0,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
      (const char *)(unsigned int)v6,
      TokenType);
    Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
    if ( v66 < 0 )
      LogCallerInfo(v69, v66, TokenHandle);
LABEL_216:
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
    return (unsigned int)v6;
  }
  v66 = 0;
LABEL_32:
  v20 = Windows::Internal::Security::Authentication::Web::CallerContext::_CaptureCallerIdentity(this, v69, TokenHandle);
  v16 = v20;
  v66 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
      (const char *)(unsigned int)v20,
      TokenType);
    Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
    if ( v66 < 0 )
      LogCallerInfo(v69, v66, TokenHandle);
    goto LABEL_268;
  }
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    v54 = GetLastError();
    v16 = v54;
    if ( v54 > 0 )
      v16 = (unsigned __int16)v54 | 0x80070000;
    v66 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
        (const char *)(unsigned int)v16,
        TokenTypea);
      Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
      if ( v66 < 0 )
        LogCallerInfo(v69, v66, TokenHandle);
      goto LABEL_268;
    }
  }
  v21 = 0;
  v79 = 0;
  v22 = -1;
  v23 = -2147024362;
  if ( !*((_BYTE *)this + 1) )
    goto LABEL_280;
  if ( WindowsCreateStringReference(L"NO_APPLICATION", 0xEu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  result[0] = 0;
  WindowsCompareStringOrdinal(string, *((HSTRING *)this + 9), result);
  if ( result[0] )
  {
LABEL_280:
    *(_OWORD *)v85 = 0;
    v86 = 0;
    v87 = 0;
    memset(v88, 0, sizeof(v88));
    if ( !GetTokenInformation(TokenHandle, TokenAppContainerSid, v85, 0x4Cu, &ReturnLength) )
    {
      v55 = GetLastError();
      v16 = v55;
      if ( v55 > 0 )
        v16 = (unsigned __int16)v55 | 0x80070000;
      v66 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x111,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
          (const char *)(unsigned int)v16,
          TokenTypec);
        Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
        if ( v66 < 0 )
          LogCallerInfo(v69, v66, TokenHandle);
        goto LABEL_268;
      }
    }
    v45 = v85[0];
    if ( v85[0] )
    {
      *((_OWORD *)this + 5) = *(_OWORD *)v85[0];
      *((_OWORD *)this + 6) = v45[1];
      *((_OWORD *)this + 7) = v45[2];
      *((_OWORD *)this + 8) = v45[3];
      *((_DWORD *)this + 36) = *((_DWORD *)v45 + 16);
      hExistingToken = 0;
      if ( !ConvertSidToStringSidW(v45, (LPWSTR *)&hExistingToken) )
      {
        v56 = GetLastError();
        v16 = v56;
        if ( v56 > 0 )
          v16 = (unsigned __int16)v56 | 0x80070000;
        v66 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11E,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
            (const char *)(unsigned int)v16,
            TokenTypec);
          if ( hExistingToken )
            LocalFree(hExistingToken);
          Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
          if ( v66 < 0 )
            LogCallerInfo(v69, v66, TokenHandle);
          goto LABEL_268;
        }
      }
      v46 = hExistingToken;
      if ( hExistingToken )
      {
        *(_QWORD *)result = 0;
        v47 = -1;
        do
          ++v47;
        while ( *((_WORD *)hExistingToken + v47) );
        if ( v47 <= 0xFFFFFFFF )
        {
          v48 = WindowsCreateString((PCNZWCH)hExistingToken, v47, (HSTRING *)result);
          if ( v48 >= 0 )
          {
            v21 = *(HSTRING *)result;
            v79 = *(HSTRING *)result;
            WindowsDeleteString(0);
          }
          v46 = hExistingToken;
        }
        else
        {
          v48 = -2147024362;
        }
        v66 = v48;
        if ( v48 >= 0 )
        {
          if ( v46 )
            LocalFree(v46);
          goto LABEL_38;
        }
      }
      else
      {
        v48 = -2147467261;
        v66 = -2147467261;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
        (const char *)(unsigned int)v48,
        TokenTypec);
      if ( hExistingToken )
        LocalFree(hExistingToken);
      if ( v21 )
        WindowsDeleteString(v21);
      Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
      if ( v66 < 0 )
        LogCallerInfo(v69, v66, TokenHandle);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
      return (unsigned int)v48;
    }
  }
LABEL_38:
  if ( !GetTokenInformation(TokenHandle, TokenUser, Sid, 0x54u, &ReturnLength) )
  {
    v57 = GetLastError();
    v16 = v57;
    if ( v57 > 0 )
      v16 = (unsigned __int16)v57 | 0x80070000;
    v66 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
        (const char *)(unsigned int)v16,
        TokenTypeb);
      if ( v21 )
        WindowsDeleteString(v21);
      Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
      if ( v66 < 0 )
        LogCallerInfo(v69, v66, TokenHandle);
      goto LABEL_268;
    }
  }
  v24 = Sid[0];
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid[0], &StringSid) )
  {
    v58 = GetLastError();
    v16 = v58;
    if ( v58 > 0 )
      v16 = (unsigned __int16)v58 | 0x80070000;
    v66 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
        (const char *)(unsigned int)v16,
        TokenTypeb);
      if ( StringSid )
        LocalFree(StringSid);
      if ( v21 )
        WindowsDeleteString(v21);
      Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
      if ( v66 < 0 )
        LogCallerInfo(v69, v66, TokenHandle);
LABEL_268:
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
      return (unsigned int)v16;
    }
  }
  v25 = 0;
  v78 = 0;
  if ( !StringSid )
  {
    v23 = -2147467261;
    v66 = -2147467261;
    goto LABEL_47;
  }
  hExistingToken = 0;
  do
    ++v22;
  while ( StringSid[v22] );
  if ( v22 <= 0xFFFFFFFF )
  {
    v23 = WindowsCreateString(StringSid, v22, (HSTRING *)&hExistingToken);
    if ( v23 >= 0 )
    {
      v25 = (HSTRING)hExistingToken;
      v78 = hExistingToken;
      WindowsDeleteString(0);
    }
  }
  v66 = v23;
  if ( v23 < 0 )
  {
LABEL_47:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
      (const char *)(unsigned int)v23,
      TokenTypeb);
    if ( v25 )
      WindowsDeleteString(v25);
    if ( StringSid )
      LocalFree(StringSid);
    if ( v21 )
      WindowsDeleteString(v21);
    if ( v73 && !SetThreadToken(0, Token) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
        v26);
    if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Token);
    if ( v66 < 0 )
      LogCallerInfo(v69, v66, TokenHandle);
    v27 = TokenHandle;
    if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return (unsigned int)v23;
    goto LABEL_199;
  }
  v29 = v77;
  if ( v77 )
  {
    result[0] = 0;
    RtlGetDeviceFamilyInfoEnum(0, result, 0);
    v66 = 0;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle);
    TokenHandle = 0;
    v52 = UMgrQueryUserToken(v29, &TokenHandle);
    v23 = v52;
    v66 = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x164,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
        (const char *)(unsigned int)v52,
        TokenTypeb);
      if ( v25 )
        WindowsDeleteString(v25);
      if ( StringSid )
        LocalFree(StringSid);
      if ( v21 )
        WindowsDeleteString(v21);
      Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
      if ( v66 < 0 )
        LogCallerInfo(v69, v66, TokenHandle);
      v27 = TokenHandle;
      if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        return (unsigned int)v23;
LABEL_199:
      CloseHandle(v27);
      return (unsigned int)v23;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, Sid, 0x54u, &ReturnLength) )
    {
      v53 = GetLastError();
      v23 = v53;
      if ( v53 > 0 )
        v23 = (unsigned __int16)v53 | 0x80070000;
      v66 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16D,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
          (const char *)(unsigned int)v23,
          TokenTypeb);
        if ( v25 )
          WindowsDeleteString(v25);
        if ( StringSid )
          LocalFree(StringSid);
        if ( v21 )
          WindowsDeleteString(v21);
        Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
        if ( v66 < 0 )
          LogCallerInfo(v69, v66, TokenHandle);
        Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
        return (unsigned int)v23;
      }
    }
LABEL_77:
    v40 = Sid[0];
    if ( v71 )
    {
      if ( WindowsIsStringEmpty(v21) )
      {
        if ( WindowsIsStringEmpty(*((HSTRING *)this + 7)) )
        {
          v66 = -2147024846;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x18D,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
            (const char *)0x80070032LL,
            TokenTypeb);
          if ( v25 )
            WindowsDeleteString(v25);
          if ( StringSid )
            LocalFree(StringSid);
          if ( v21 )
            WindowsDeleteString(v21);
          Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
          if ( v66 < 0 )
            LogCallerInfo(v69, v66, TokenHandle);
          Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
          return 2147942450LL;
        }
      }
      else
      {
        if ( WindowsIsStringEmpty(*((HSTRING *)this + 9)) )
        {
          v66 = -2147024846;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17F,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
            (const char *)0x80070032LL,
            TokenTypeb);
          if ( v25 )
            WindowsDeleteString(v25);
          if ( StringSid )
            LocalFree(StringSid);
          if ( v21 )
            WindowsDeleteString(v21);
          Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
          if ( v66 < 0 )
            LogCallerInfo(v69, v66, TokenHandle);
          if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(TokenHandle);
          return 2147942450LL;
        }
        if ( ((*((_QWORD *)this + 39) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          v66 = -2147024891;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x185,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
            (const char *)0x80070005LL,
            TokenTypeb);
          if ( v25 )
            WindowsDeleteString(v25);
          if ( StringSid )
            LocalFree(StringSid);
          if ( v21 )
            WindowsDeleteString(v21);
          Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
          if ( v66 < 0 )
            LogCallerInfo(v69, v66, TokenHandle);
          Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
          return 2147942405LL;
        }
      }
    }
    *(_OWORD *)((char *)this + 148) = *v24;
    *(_OWORD *)((char *)this + 164) = v24[1];
    *(_OWORD *)((char *)this + 180) = v24[2];
    *(_OWORD *)((char *)this + 196) = v24[3];
    *((_DWORD *)this + 53) = *((_DWORD *)v24 + 16);
    *(_OWORD *)((char *)this + 216) = *v40;
    *(_OWORD *)((char *)this + 232) = v40[1];
    *(_OWORD *)((char *)this + 248) = v40[2];
    *(_OWORD *)((char *)this + 264) = v40[3];
    *((_DWORD *)this + 70) = *((_DWORD *)v40 + 16);
    WindowsDeleteString(*((HSTRING *)this + 6));
    *((_QWORD *)this + 6) = v25;
    WindowsDeleteString(*((HSTRING *)this + 5));
    *((_QWORD *)this + 5) = v21;
    *((_DWORD *)this + 6) = TokenInformation;
    *((_QWORD *)this + 1) = v77;
    *((_QWORD *)this + 2) = v29;
    *(_BYTE *)this = 1;
    v41 = (void **)((char *)this + 296);
    v42 = *v41;
    *v41 = 0;
    if ( v41 == &TokenHandle )
    {
      v43 = (char *)TokenHandle;
    }
    else
    {
      *v41 = TokenHandle;
      v43 = 0;
      TokenHandle = 0;
    }
    if ( (unsigned __int64)(v43 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v43);
    TokenHandle = v42;
    if ( StringSid )
      LocalFree(StringSid);
    if ( v73 && !SetThreadToken(0, Token) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
        v44);
    if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Token);
    if ( v66 < 0 )
      LogCallerInfo(v69, v66, TokenHandle);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return 0;
  }
  v30 = TokenHandle;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&hExistingToken, TokenHandle);
  for ( i = &si128; ; i = (__m128i *)((char *)i + 4) )
  {
    v32 = hExistingToken;
    if ( i == (__m128i *)v81 )
      break;
    v33 = i->m128i_i32[0];
    if ( IsWellKnownSid(*(PSID *)hExistingToken, (WELL_KNOWN_SID_TYPE)i->m128i_i32[0]) )
    {
      v49 = hExistingToken;
      hExistingToken = 0;
      if ( v49 )
        operator delete(v49);
      if ( (unsigned int)(v33 - 22) <= 2 )
      {
LABEL_130:
        if ( v25 )
          WindowsDeleteString(v25);
        if ( StringSid )
          LocalFree(StringSid);
        if ( v21 )
          WindowsDeleteString(v21);
        Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&Token);
        if ( v66 < 0 )
          LogCallerInfo(v69, v66, TokenHandle);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        return 2147943712LL;
      }
      goto LABEL_75;
    }
  }
  hExistingToken = 0;
  if ( v32 )
    operator delete(v32);
  result[0] = 0;
  LOWORD(result[1]) = 1280;
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&hExistingToken, v30);
  v34 = *(PSID *)hExistingToken;
  if ( !*RtlSubAuthorityCountSid(*(PSID *)hExistingToken) )
  {
    v38 = hExistingToken;
    hExistingToken = 0;
    if ( !v38 )
      goto LABEL_75;
    goto LABEL_212;
  }
  v35 = RtlIdentifierAuthoritySid(v34);
  v36 = *(_DWORD *)v35->Value;
  if ( !*(_DWORD *)v35->Value )
    v36 = *(unsigned __int16 *)&v35->Value[4] - LOWORD(result[1]);
  if ( v36 )
  {
    v38 = hExistingToken;
    hExistingToken = 0;
    if ( !v38 )
      goto LABEL_75;
    goto LABEL_212;
  }
  v37 = *GetSidSubAuthority(v34, 0) - 80 <= 0x1F;
  v38 = hExistingToken;
  if ( v37 )
  {
    hExistingToken = 0;
    if ( v38 )
      operator delete(v38);
    goto LABEL_130;
  }
  hExistingToken = 0;
  if ( v38 )
LABEL_212:
    operator delete(v38);
LABEL_75:
  v39 = UMgrQueryUserContext(TokenHandle, &v77);
  v66 = v39;
  if ( v39 >= 0 )
  {
    v29 = v77;
    goto LABEL_77;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v25, 0);
  LODWORD(phNewToken) = TokenInformation;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x14C,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
    (const char *)(unsigned int)v39,
    (int)"%d, %ws",
    phNewToken,
    StringRawBuffer);
  if ( v25 )
    WindowsDeleteString(v25);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v21 )
    WindowsDeleteString(v21);
  if ( v73 && !SetThreadToken(0, Token) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
      v51);
  if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(Token);
  if ( v66 < 0 )
    LogCallerInfo(v69, v66, TokenHandle);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v39;
}

```

## disassembly

```asm
0x18000bd70  mov     [rsp-8+arg_18], rbx
0x18000bd75  push    rbp
0x18000bd76  push    rsi
0x18000bd77  push    rdi
0x18000bd78  push    r12
0x18000bd7a  push    r13
0x18000bd7c  push    r14
0x18000bd7e  push    r15
0x18000bd80  lea     rbp, [rsp-0C0h]
0x18000bd88  sub     rsp, 1C0h
0x18000bd8f  mov     rax, cs:__security_cookie
0x18000bd96  xor     rax, rsp
0x18000bd99  mov     [rbp+0F0h+var_40], rax
0x18000bda0  mov     [rsp+1F0h+var_188], r9b
0x18000bda5  mov     rax, rdx
0x18000bda8  mov     r12, rcx
0x18000bdab  mov     [rsp+1F0h+var_198], rdx
0x18000bdb0  mov     [rbp+0F0h+var_160], r8
0x18000bdb4  xor     r15d, r15d
0x18000bdb7  mov     [rsp+1F0h+var_1B0], r15d
0x18000bdbc  mov     [rsp+1F0h+TokenHandle], r15
0x18000bdc1  lea     rcx, [rsp+1F0h+var_1B0]
0x18000bdc6  mov     [rbp+0F0h+var_138], rcx
0x18000bdca  lea     rcx, [rsp+1F0h+var_198]
0x18000bdcf  mov     [rbp+0F0h+var_130], rcx
0x18000bdd3  lea     rcx, [rsp+1F0h+TokenHandle]
0x18000bdd8  mov     [rbp+0F0h+var_128], rcx
0x18000bddc  mov     [rbp+0F0h+var_120], 1
0x18000bde0  test    rdx, rdx
0x18000bde3  jz      loc_18000CDD5
0x18000bde9  mov     [rsp+1F0h+result], r15d
0x18000bdee  lea     rdx, [rsp+1F0h+result]
0x18000bdf3  mov     rcx, rax
0x18000bdf6  call    cs:__imp_CoImpersonateClientOfObject
0x18000bdfc  mov     edi, eax
0x18000bdfe  test    eax, eax
0x18000be00  js      loc_18000CC6E
0x18000be06  xor     al, al
0x18000be08  movzx   ebx, al
0x18000be0b  mov     r13d, 1
0x18000be11  cmp     [rsp+1F0h+result], r15d
0x18000be16  cmovnz  ebx, r13d
0x18000be1a  mov     rcx, [rsp+1F0h+TokenHandle]; hObject
0x18000be1f  lea     rax, [rcx-1]
0x18000be23  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000be27  jbe     loc_18000D185
0x18000be2d  mov     [rsp+1F0h+TokenHandle], r15
0x18000be32  call    cs:__imp_GetCurrentThread
0x18000be38  lea     r9, [rsp+1F0h+TokenHandle]; TokenHandle
0x18000be3d  mov     r8d, r13d; OpenAsSelf
0x18000be40  mov     edx, 2000Ch; DesiredAccess
0x18000be45  mov     rcx, rax; ThreadHandle
0x18000be48  call    cs:__imp_OpenThreadToken
0x18000be4e  test    eax, eax
0x18000be50  jnz     loc_18000BEF3
0x18000be56  call    cs:__imp_GetLastError
0x18000be5c  test    bl, bl
0x18000be5e  jnz     loc_18000D199
0x18000be64  cmp     eax, 3F0h
0x18000be69  jnz     loc_18000D199
0x18000be6f  mov     [rsp+1F0h+hExistingToken], r15
0x18000be74  call    cs:__imp_GetCurrentProcess
0x18000be7a  lea     r8, [rsp+1F0h+hExistingToken]; TokenHandle
0x18000be7f  mov     edx, 2000Eh; DesiredAccess
0x18000be84  mov     rcx, rax; ProcessHandle
0x18000be87  call    cs:__imp_OpenProcessToken
0x18000be8d  test    eax, eax
0x18000be8f  jz      loc_18000CE28
0x18000be95  mov     rcx, [rsp+1F0h+TokenHandle]; hObject
0x18000be9a  lea     rax, [rcx-1]
0x18000be9e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bea2  jbe     loc_18000D18F
0x18000bea8  mov     [rsp+1F0h+TokenHandle], r15
0x18000bead  lea     rax, [rsp+1F0h+TokenHandle]
0x18000beb2  mov     [rsp+1F0h+phNewToken], rax; phNewToken
0x18000beb7  mov     [rsp+1F0h+TokenType], 2; int
0x18000bebf  mov     r9d, 2; ImpersonationLevel
0x18000bec5  xor     r8d, r8d; lpTokenAttributes
0x18000bec8  mov     edx, 2000Ch; dwDesiredAccess
0x18000becd  mov     rcx, [rsp+1F0h+hExistingToken]; hExistingToken
0x18000bed2  call    cs:__imp_DuplicateTokenEx
0x18000bed8  test    eax, eax
0x18000beda  jz      short loc_18000BF02
0x18000bedc  mov     rcx, [rsp+1F0h+hExistingToken]; hObject
0x18000bee1  test    rcx, rcx
0x18000bee4  jz      short loc_18000BEFB
0x18000bee6  call    cs:__imp_CloseHandle
0x18000beec  mov     [rsp+1F0h+var_1B0], r15d
0x18000bef1  jmp     short loc_18000BF38
0x18000bef3  test    bl, bl
0x18000bef5  jnz     loc_18000D17A
0x18000befb  mov     [rsp+1F0h+var_1B0], r15d
0x18000bf00  jmp     short loc_18000BF38
0x18000bf02  mov     rcx, [rbp+0F8h]; this
0x18000bf09  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18000bf10  mov     edx, 184h; void *
0x18000bf15  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bf1a  mov     edi, eax
0x18000bf1c  mov     rcx, [rsp+1F0h+hExistingToken]; hObject
0x18000bf21  test    rcx, rcx
0x18000bf24  jz      short loc_18000BF2C
0x18000bf26  call    cs:__imp_CloseHandle
0x18000bf2c  mov     [rsp+1F0h+var_1B0], edi
0x18000bf30  test    edi, edi
0x18000bf32  js      loc_18000CCA8
0x18000bf38  mov     [rsp+1F0h+var_178], 0
0x18000bf3d  mov     [rsp+1F0h+Token], r15
0x18000bf42  call    cs:__imp_GetCurrentThread
0x18000bf48  mov     rcx, rax; ThreadHandle
0x18000bf4b  lea     r9, [rsp+1F0h+Token]; TokenHandle
0x18000bf50  mov     r8d, r13d; OpenAsSelf
0x18000bf53  mov     edx, 0F01FFh; DesiredAccess
0x18000bf58  call    cs:__imp_OpenThreadToken
0x18000bf5e  test    eax, eax
0x18000bf60  jnz     short loc_18000BF7B
0x18000bf62  call    cs:__imp_GetLastError
0x18000bf68  test    eax, eax
0x18000bf6a  jle     short loc_18000BF74
0x18000bf6c  movzx   eax, ax
0x18000bf6f  or      eax, 80070000h
0x18000bf74  cmp     eax, 800703F0h
0x18000bf79  jnz     short loc_18000BF80
0x18000bf7b  mov     ebx, r15d
0x18000bf7e  jmp     short loc_18000BF9D
0x18000bf80  call    cs:__imp_GetLastError
0x18000bf86  mov     ebx, eax
0x18000bf88  test    eax, eax
0x18000bf8a  jle     short loc_18000BF95
0x18000bf8c  movzx   ebx, ax
0x18000bf8f  or      ebx, 80070000h
0x18000bf95  test    ebx, ebx
0x18000bf97  js      loc_18000CAA8
0x18000bf9d  call    cs:__imp_RevertToSelf
0x18000bfa3  mov     rcx, [rbp+0F8h]; this
0x18000bfaa  test    eax, eax
0x18000bfac  jz      loc_18000C863
0x18000bfb2  mov     [rsp+1F0h+var_178], 1
0x18000bfb7  mov     [rsp+1F0h+var_1B0], ebx
0x18000bfbb  mov     rbx, cs:?sInstance@?1??GetInstance@Statics@Web@Authentication@Security@Internal@Windows@@SAPEAV234567@XZ@4PEAV234567@EA; Windows::Internal::Security::Authentication::Web::Statics * `Windows::Internal::Security::Authentication::Web::Statics::GetInstance(void)'::`2'::sInstance
0x18000bfc2  test    rbx, rbx
0x18000bfc5  jz      loc_18000D19F
0x18000bfcb  cmp     byte ptr [rbx+10h], 0
0x18000bfcf  jz      loc_18000CD29
0x18000bfd5  mov     [rsp+1F0h+var_1B0], r15d
0x18000bfda  mov     r8, [rsp+1F0h+TokenHandle]; void *
0x18000bfdf  mov     rdx, [rsp+1F0h+var_198]; struct IUnknown *
0x18000bfe4  mov     rcx, r12; this
0x18000bfe7  call    ?_CaptureCallerIdentity@CallerContext@Web@Authentication@Security@Internal@Windows@@AEAAJPEAUIUnknown@@PEAX@Z; Windows::Internal::Security::Authentication::Web::CallerContext::_CaptureCallerIdentity(IUnknown *,void *)
0x18000bfec  mov     ebx, eax
0x18000bfee  mov     [rsp+1F0h+var_1B0], eax
0x18000bff2  test    eax, eax
0x18000bff4  js      loc_18000CE5B
0x18000bffa  mov     [rbp+0F0h+TokenInformation], r15d
0x18000bffe  mov     [rbp+0F0h+ReturnLength], r15d
0x18000c002  lea     rax, [rbp+0F0h+ReturnLength]
0x18000c006  mov     qword ptr [rsp+1F0h+TokenType], rax; int
0x18000c00b  mov     r9d, 4; TokenInformationLength
0x18000c011  lea     r8, [rbp+0F0h+TokenInformation]; TokenInformation
0x18000c015  mov     edx, 0Ch; TokenInformationClass
0x18000c01a  mov     rcx, [rsp+1F0h+TokenHandle]; TokenHandle
0x18000c01f  call    cs:__imp_GetTokenInformation
0x18000c025  test    eax, eax
0x18000c027  jz      loc_18000CEAB
0x18000c02d  mov     rdi, r15
0x18000c030  mov     [rbp+0F0h+var_150], r15
0x18000c034  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000c03b  mov     ebx, 0FFFFFFFFh
0x18000c040  mov     r14d, 80070216h
0x18000c046  cmp     byte ptr [r12+1], 0
0x18000c04c  jz      loc_18000C4C0
0x18000c052  lea     r9, [rbp+0F0h+string]; string
0x18000c056  lea     r8, [rbp+0F0h+hstringHeader]; hstringHeader
0x18000c05a  mov     edx, 0Eh; length
0x18000c05f  lea     rcx, aNoApplication; "NO_APPLICATION"
0x18000c066  call    cs:__imp_WindowsCreateStringReference
0x18000c06c  test    eax, eax
0x18000c06e  js      loc_18000C6B6
0x18000c074  mov     [rsp+1F0h+result], r15d
0x18000c079  lea     r8, [rsp+1F0h+result]; result
0x18000c07e  mov     rdx, [r12+48h]; string2
0x18000c083  mov     rcx, [rbp+0F0h+string]; string1
0x18000c087  call    cs:__imp_WindowsCompareStringOrdinal
0x18000c08d  cmp     [rsp+1F0h+result], 0
0x18000c092  jnz     loc_18000C4C0
0x18000c098  lea     rax, [rbp+0F0h+ReturnLength]
0x18000c09c  mov     qword ptr [rsp+1F0h+TokenType], rax; int
0x18000c0a1  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000c0a7  lea     r8, [rbp+0F0h+Sid]; TokenInformation
0x18000c0ab  mov     edx, r13d; TokenInformationClass
0x18000c0ae  mov     rcx, [rsp+1F0h+TokenHandle]; TokenHandle
0x18000c0b3  call    cs:__imp_GetTokenInformation
0x18000c0b9  test    eax, eax
0x18000c0bb  jz      loc_18000D01A
0x18000c0c1  mov     r13, [rbp+0F0h+Sid]
0x18000c0c5  mov     [rbp+0F0h+StringSid], r15
0x18000c0c9  lea     rdx, [rbp+0F0h+StringSid]; StringSid
0x18000c0cd  mov     rcx, r13; Sid
0x18000c0d0  call    cs:__imp_ConvertSidToStringSidW
0x18000c0d6  test    eax, eax
0x18000c0d8  jz      loc_18000D09A
0x18000c0de  mov     rbx, r15
0x18000c0e1  mov     [rbp+0F0h+var_158], rbx
0x18000c0e5  mov     rcx, [rbp+0F0h+StringSid]; sourceString
0x18000c0e9  test    rcx, rcx
0x18000c0ec  jz      loc_18000C213
0x18000c0f2  mov     [rsp+1F0h+hExistingToken], r15
0x18000c0f7  nop     word ptr [rax+rax+00000000h]
0x18000c100  inc     rsi
0x18000c103  cmp     word ptr [rcx+rsi*2], 0
0x18000c108  jnz     short loc_18000C100
0x18000c10a  mov     eax, 0FFFFFFFFh
0x18000c10f  cmp     rsi, rax
0x18000c112  ja      short loc_18000C139
0x18000c114  mov     edx, esi; length
0x18000c116  lea     r8, [rsp+1F0h+hExistingToken]; string
0x18000c11b  call    cs:__imp_WindowsCreateString
0x18000c121  mov     r14d, eax
0x18000c124  test    eax, eax
0x18000c126  js      short loc_18000C139
0x18000c128  mov     rbx, [rsp+1F0h+hExistingToken]
0x18000c12d  mov     [rbp+0F0h+var_158], rbx
0x18000c131  xor     ecx, ecx; string
0x18000c133  call    cs:__imp_WindowsDeleteString
0x18000c139  mov     [rsp+1F0h+var_1B0], r14d
0x18000c13e  test    r14d, r14d
0x18000c141  jns     loc_18000C226
0x18000c147  mov     rcx, [rbp+0F8h]; this
0x18000c14e  mov     r9d, r14d; char *
0x18000c151  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\tokenbroker\\cal"...
0x18000c158  mov     edx, 139h; void *
0x18000c15d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c162  nop
0x18000c163  test    rbx, rbx
0x18000c166  jz      short loc_18000C172
0x18000c168  mov     rcx, rbx; string
0x18000c16b  call    cs:__imp_WindowsDeleteString
0x18000c171  nop
0x18000c172  mov     rcx, [rbp+0F0h+StringSid]; hMem
0x18000c176  test    rcx, rcx
0x18000c179  jz      short loc_18000C182
0x18000c17b  call    cs:__imp_LocalFree
0x18000c181  nop
0x18000c182  test    rdi, rdi
0x18000c185  jz      short loc_18000C191
0x18000c187  mov     rcx, rdi; string
0x18000c18a  call    cs:__imp_WindowsDeleteString
0x18000c190  nop
0x18000c191  cmp     [rsp+1F0h+var_178], 0
0x18000c196  jz      short loc_18000C1B4
0x18000c198  mov     rdx, [rsp+1F0h+Token]; Token
0x18000c19d  xor     ecx, ecx; Thread
0x18000c19f  call    cs:__imp_SetThreadToken
0x18000c1a5  mov     rcx, [rbp+0F8h]; this
0x18000c1ac  test    eax, eax
0x18000c1ae  jz      loc_18000C99C
0x18000c1b4  mov     rcx, [rsp+1F0h+Token]; hObject
0x18000c1b9  lea     rax, [rcx-1]
0x18000c1bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c1c1  jbe     loc_18000D23B
0x18000c1c7  mov     edx, [rsp+1F0h+var_1B0]; int
0x18000c1cb  test    edx, edx
0x18000c1cd  js      loc_18000CA76
0x18000c1d3  mov     rcx, [rsp+1F0h+TokenHandle]
0x18000c1d8  lea     rdx, [rcx-1]
0x18000c1dc  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000c1e0  jbe     loc_18000CB9A
0x18000c1e6  mov     eax, r14d
0x18000c1e9  mov     rcx, [rbp+0F0h+var_40]
0x18000c1f0  xor     rcx, rsp; StackCookie
0x18000c1f3  call    __security_check_cookie
0x18000c1f8  mov     rbx, [rsp+1F0h+arg_18]
0x18000c200  add     rsp, 1C0h
0x18000c207  pop     r15
0x18000c209  pop     r14
0x18000c20b  pop     r13
0x18000c20d  pop     r12
0x18000c20f  pop     rdi
0x18000c210  pop     rsi
0x18000c211  pop     rbp
0x18000c212  retn
0x18000c213  mov     r15d, 80004003h
0x18000c219  mov     r14d, r15d
0x18000c21c  mov     [rsp+1F0h+var_1B0], r15d
0x18000c221  jmp     loc_18000C147
0x18000c226  mov     rsi, [rbp+0F0h+var_160]
0x18000c22a  test    rsi, rsi
0x18000c22d  jnz     loc_18000C875
0x18000c233  mov     r15, [rsp+1F0h+TokenHandle]
0x18000c238  movdqa  xmm0, cs:__xmm@0000006e000000180000001700000016
0x18000c240  movdqu  [rbp+0F0h+var_148], xmm0
0x18000c245  mov     rdx, r15
0x18000c248  lea     rcx, [rsp+1F0h+hExistingToken]
0x18000c24d  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18000c252  lea     rsi, [rbp+0F0h+var_148]
0x18000c256  nop     word ptr [rax+rax+00000000h]
0x18000c260  lea     rax, [rbp+0F0h+var_138]
0x18000c264  mov     rcx, [rsp+1F0h+hExistingToken]; Block
0x18000c269  cmp     rsi, rax
0x18000c26c  jz      short loc_18000C28B
0x18000c26e  mov     r14d, [rsi]
  ... truncated ...
```
