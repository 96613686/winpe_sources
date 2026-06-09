# CSLSEndpointProvider::GetWUClientData(void *,_GUID const &,bool,CCallerIdentity const *,bool,ulong *,char * *,char const *)

- ea: `0x1801cede4`
- end: `0x1801cf200`
- name: `?GetWUClientData@CSLSEndpointProvider@@AEAAJPEAXAEBU_GUID@@_NPEBVCCallerIdentity@@_NPEAKPEAPEADPEBD@Z`
- size: `1052`
- prototype: `int(CSLSEndpointProvider *__hidden this, void *, const struct _GUID *, bool, const struct CCallerIdentity *, bool, unsigned int *, char **, const char *)`
- caller_count: `9`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1801cdd70`
- `0x1801cde90`
- `0x1801cdfc0`
- `0x1801ce100`
- `0x1801ce220`
- `0x1801ce41c`
- `0x1801cf210`
- `0x1801cf330`
- `0x1801cf4a0`

## callees

- `0x18000def4`
- `0x180014964`
- `0x180038d00`
- `0x180113ae8`
- `0x1801167bc`
- `0x18012dd74`
- `0x1801b0b0c`
- `0x1801b0c08`
- `0x1801b0e54`
- `0x1801b2650`
- `0x1801b28d8`
- `0x1801cede4`
- `0x180238960`
- `0x180240d40`
- `0x180241100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801cf002`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801cf002`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf053`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf07f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf053`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf07f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801cef88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801cef88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801cf1ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801cf1ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1801cee95`
- `OLEAUT32!__imp_SysFreeString` at `0x1801cefc6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801cefe4`
- `OLEAUT32!__imp_SysFreeString` at `0x1801cee95`
- `OLEAUT32!__imp_SysFreeString` at `0x1801cefc6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801cefe4`

## string_xrefs

- `0x1801cef3d`: `ResponsePayloadFilePath`
- `0x1801ceea4`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\SLS`

## pseudocode

```c

```
