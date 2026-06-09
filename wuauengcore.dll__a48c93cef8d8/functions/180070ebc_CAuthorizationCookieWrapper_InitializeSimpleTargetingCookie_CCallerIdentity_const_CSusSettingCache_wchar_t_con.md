# CAuthorizationCookieWrapper::InitializeSimpleTargetingCookie(CCallerIdentity const *,CSusSettingCache *,wchar_t const *,wchar_t const *,ulong,bool,char const *,bool,bool)

- ea: `0x180070ebc`
- end: `0x1800714ec`
- name: `?InitializeSimpleTargetingCookie@CAuthorizationCookieWrapper@@QEAAJPEBVCCallerIdentity@@PEAVCSusSettingCache@@PEB_W2K_NPEBD33@Z`
- size: `1584`
- prototype: `__int64 __fastcall(CAuthorizationCookieWrapper *__hidden this, const struct CCallerIdentity *, struct CSusSettingCache *, const wchar_t *, const wchar_t *, unsigned int, bool, const char *, bool, bool)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006fc3c`

## callees

- `0x18000def4`
- `0x180036560`
- `0x180070ebc`
- `0x1800714f4`
- `0x1800bd2bc`
- `0x1800d9e30`
- `0x18010696c`
- `0x180106d28`
- `0x180106dec`
- `0x180109994`
- `0x180110d60`
- `0x180113ae8`
- `0x180121c5c`
- `0x180121ec8`
- `0x18012b618`
- `0x1801abc2c`
- `0x1801acb38`
- `0x1801acc98`
- `0x1801acd4c`
- `0x1801acd90`
- `0x1801acf64`
- `0x1801af544`
- `0x1801afcdc`
- `0x1801c0108`
- `0x1801c8b80`
- `0x180238960`
- `0x180238984`
- `0x180239110`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180071184`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180071184`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800711a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800711a9`
- `OLEAUT32!__imp_SysAllocString` at `0x180071138`
- `OLEAUT32!__imp_SysAllocString` at `0x1800711f1`
- `OLEAUT32!__imp_SysAllocString` at `0x180071138`
- `OLEAUT32!__imp_SysAllocString` at `0x1800711f1`
- `OLEAUT32!__imp_SysFreeString` at `0x180071158`
- `OLEAUT32!__imp_SysFreeString` at `0x180071451`
- `OLEAUT32!__imp_SysFreeString` at `0x18007145e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800714b3`
- `OLEAUT32!__imp_SysFreeString` at `0x180071158`
- `OLEAUT32!__imp_SysFreeString` at `0x180071451`
- `OLEAUT32!__imp_SysFreeString` at `0x18007145e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800714b3`

## string_xrefs

- `0x180071119`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x1800711d1`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x180071431`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x1800713df`: `::CopyBstr(&dest->PlugInId, PlugInId)`
- `0x180071402`: `CookieData.Copy(&dest->CookieData)`

## pseudocode

```c

```
