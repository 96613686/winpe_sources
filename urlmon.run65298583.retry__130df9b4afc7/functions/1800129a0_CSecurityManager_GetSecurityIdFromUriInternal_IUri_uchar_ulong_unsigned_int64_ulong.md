# CSecurityManager::GetSecurityIdFromUriInternal(IUri *,uchar *,ulong *,unsigned __int64,ulong)

- ea: `0x1800129a0`
- end: `0x180012e19`
- name: `?GetSecurityIdFromUriInternal@CSecurityManager@@UEAAJPEAUIUri@@PEAEPEAK_KK@Z`
- size: `1145`
- prototype: `__int64 __fastcall(CSecurityManager *__hidden this, struct IUri *, unsigned __int8 *, unsigned int *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18008ddf0`

## callees

- `0x180012410`
- `0x1800128f0`
- `0x1800129a0`
- `0x180012e20`
- `0x180037284`
- `0x1800387d0`
- `0x1800573c0`
- `0x18011c010`

## import_xrefs

- `iertutil!GetIUriPriv` at `0x180012b7f`
- `iertutil!GetIUriPriv` at `0x180012b7f`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180012d22`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180012d47`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180012d72`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180012d22`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180012d47`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180012d72`
- `iertutil!__imp_GetWebPlatformSecurityManagerFactoryCallback` at `0x180012c90`
- `iertutil!__imp_GetWebPlatformSecurityManagerFactoryCallback` at `0x180012c90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012a7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012dcf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012a7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012dcf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a39`

## pseudocode

```c

```
