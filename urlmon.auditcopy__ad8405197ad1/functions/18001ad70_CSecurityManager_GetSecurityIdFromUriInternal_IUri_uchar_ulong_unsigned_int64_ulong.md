# CSecurityManager::GetSecurityIdFromUriInternal(IUri *,uchar *,ulong *,unsigned __int64,ulong)

- ea: `0x18001ad70`
- end: `0x18001b220`
- name: `?GetSecurityIdFromUriInternal@CSecurityManager@@UEAAJPEAUIUri@@PEAEPEAK_KK@Z`
- size: `1200`
- prototype: `__int64 __fastcall(CSecurityManager *this, struct IUri *, unsigned __int8 *, unsigned int *, const WCHAR *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180093de0`

## callees

- `0x18001a710`
- `0x18001acb0`
- `0x18001ad70`
- `0x18001b230`
- `0x180041188`
- `0x180042850`
- `0x18005cd30`
- `0x180129010`

## import_xrefs

- `iertutil!GetIUriPriv` at `0x18001af5c`
- `iertutil!GetIUriPriv` at `0x18001af5c`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001b111`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001b13c`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001b16d`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001b111`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001b13c`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001b16d`
- `iertutil!__imp_GetWebPlatformSecurityManagerFactoryCallback` at `0x18001b079`
- `iertutil!__imp_GetWebPlatformSecurityManagerFactoryCallback` at `0x18001b079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b054`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b054`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae09`

## pseudocode

```c

```
