# CVersionManagerClient::IsVersionAllowed(ushort const *,ushort const *,ushort const *,int,int,ushort * *,ushort * *,int *,int *)

- ea: `0x180104c00`
- end: `0x18010500d`
- name: `?IsVersionAllowed@CVersionManagerClient@@UEAAJPEBG00HHPEAPEAG1PEAH2@Z`
- size: `1037`
- prototype: `__int64 __fastcall(CVersionManagerClient *this, WCHAR *, const unsigned __int16 *, unsigned __int16 *, int, int, unsigned __int16 **, unsigned __int16 **, int *, int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800606a0`
- `0x18008f4f8`
- `0x180103d88`
- `0x180104c00`
- `0x180105014`
- `0x1801051c4`
- `0x180105354`
- `0x180107680`
- `0x180118198`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180104df2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180104df2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180104db0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180104db0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180104c9d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180104c9d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180104ce7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180104ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104f71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104f71`
- `OLEAUT32!__imp_SysAllocString` at `0x180104e3c`
- `OLEAUT32!__imp_SysAllocString` at `0x180104e6e`
- `OLEAUT32!__imp_SysAllocString` at `0x180104e3c`
- `OLEAUT32!__imp_SysAllocString` at `0x180104e6e`
- `OLEAUT32!__imp_SysFreeString` at `0x180104fb6`
- `OLEAUT32!__imp_SysFreeString` at `0x180104fd0`
- `OLEAUT32!__imp_SysFreeString` at `0x180104fb6`
- `OLEAUT32!__imp_SysFreeString` at `0x180104fd0`

## pseudocode

```c

```
