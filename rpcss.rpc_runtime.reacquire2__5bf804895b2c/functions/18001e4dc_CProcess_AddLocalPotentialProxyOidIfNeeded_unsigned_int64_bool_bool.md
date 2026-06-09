# CProcess::AddLocalPotentialProxyOidIfNeeded(unsigned __int64,bool,bool *)

- ea: `0x18001e4dc`
- end: `0x18001e7a7`
- name: `?AddLocalPotentialProxyOidIfNeeded@CProcess@@QEAAJ_K_NPEA_N@Z`
- size: `715`
- prototype: `__int64 __fastcall(CProcess *__hidden this, unsigned __int64, bool, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180069a90`

## callees

- `0x18001e4dc`
- `0x18001f018`
- `0x1800210f8`
- `0x180036b80`
- `0x180036f0c`
- `0x18006016c`
- `0x1800a4648`
- `0x1800b7ac0`
- `0x1800b8aec`

## import_xrefs

- `ntdll!RtlQueryPackageIdentity` at `0x18001e681`
- `ntdll!RtlQueryPackageIdentity` at `0x18001e681`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e51c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e51c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e5a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e6b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e70c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e5a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e6b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e70c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e5ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e5ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e631`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e631`
- `ext-ms-win-core-winrt-remote-l1-1-0!IsPackagedAppExemptFromSuspend` at `0x18001e69a`
- `ext-ms-win-core-winrt-remote-l1-1-0!IsPackagedAppExemptFromSuspend` at `0x18001e69a`

## string_xrefs

- `0x18001e6d0`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18001e6f0`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18001e726`: `onecore\com\combase\rpcss\objex\process.cxx`

## pseudocode

```c

```
