# CProcess::AddLocalPotentialProxyOidIfNeeded(unsigned __int64,bool,bool *)

- ea: `0x180029108`
- end: `0x1800293e8`
- name: `?AddLocalPotentialProxyOidIfNeeded@CProcess@@QEAAJ_K_NPEA_N@Z`
- size: `736`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, __int64, char, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180064460`

## callees

- `0x18002809c`
- `0x1800286e8`
- `0x1800289e0`
- `0x180029108`
- `0x180029a8c`
- `0x18002ba28`
- `0x18005ba08`
- `0x18009f430`
- `0x1800b27e0`
- `0x1800b37ec`

## import_xrefs

- `ntdll!RtlQueryPackageIdentity` at `0x18002936c`
- `ntdll!RtlQueryPackageIdentity` at `0x18002936c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029250`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029250`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180029148`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180029148`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800291c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029206`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029305`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800291c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029206`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029305`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029213`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029213`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029298`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029298`
- `ext-ms-win-core-winrt-remote-l1-1-0!IsPackagedAppExemptFromSuspend` at `0x18002937f`
- `ext-ms-win-core-winrt-remote-l1-1-0!IsPackagedAppExemptFromSuspend` at `0x18002937f`

## string_xrefs

- `0x1800292cc`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x1800292e9`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180029319`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x1800292ac`: `onecore\com\combase\rpcss\objex\potentialproxyoidtracker.cpp`

## pseudocode

```c

```
