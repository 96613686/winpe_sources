# PrivilegedEnsurePackageFamilyIsRegisteredForSessionUserBeforeActivationOfClass(CToken *,_GUID const &,ulong,ushort const *,ulong,int *)

- ea: `0x1800fe9a8`
- end: `0x1800fed78`
- name: `?PrivilegedEnsurePackageFamilyIsRegisteredForSessionUserBeforeActivationOfClass@@YAJPEAVCToken@@AEBU_GUID@@KPEBGKPEAH@Z`
- size: `976`
- prototype: `__int64 __fastcall(struct CToken *, const struct _GUID *, unsigned int, const unsigned __int16 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f7f40`

## callees

- `0x180003194`
- `0x18000b100`
- `0x18000ce5c`
- `0x1800155e0`
- `0x1800210f8`
- `0x180023090`
- `0x180024590`
- `0x180024fd0`
- `0x180025950`
- `0x1800535d0`
- `0x18005efe4`
- `0x180095c0c`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800fe9a8`
- `0x180114010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800fecb3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800fecb3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800fecf0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800fecf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800febe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800febe6`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x1800febfe`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x1800febfe`
- `AppXDeploymentClient!__imp_EnsurePackageFamilyIsRegisteredBeforeActivation` at `0x1800fece2`
- `AppXDeploymentClient!__imp_EnsurePackageFamilyIsRegisteredBeforeActivation` at `0x1800fece2`

## string_xrefs

- `0x1800fea06`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800fea75`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800feacb`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800feb4c`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800febae`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800fec12`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800fec93`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800fecc7`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`

## pseudocode

```c

```
