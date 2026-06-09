# CNativeWebServiceBase::ParseSoapFault(long,_WS_ERROR *)

- ea: `0x1801aecd0`
- end: `0x1801af1f7`
- name: `?ParseSoapFault@CNativeWebServiceBase@@MEAAJJPEAU_WS_ERROR@@@Z`
- size: `1319`
- prototype: `__int64 __fastcall(CNativeWebServiceBase *__hidden this, int, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180113ae8`
- `0x18012b618`
- `0x1801aaf50`
- `0x1801ab260`
- `0x1801aecd0`
- `0x1801afcdc`
- `0x1801cb9ec`
- `0x1801f3538`
- `0x1801f35c0`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1801af1ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af1b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af1bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af1c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af1ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af1b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af1bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1801af1c8`
- `OLEAUT32!__imp_SysStringLen` at `0x1801af092`
- `OLEAUT32!__imp_SysStringLen` at `0x1801af0c6`
- `OLEAUT32!__imp_SysStringLen` at `0x1801af10f`
- `OLEAUT32!__imp_SysStringLen` at `0x1801af15b`
- `OLEAUT32!__imp_SysStringLen` at `0x1801af092`
- `OLEAUT32!__imp_SysStringLen` at `0x1801af0c6`
- `OLEAUT32!__imp_SysStringLen` at `0x1801af10f`
- `OLEAUT32!__imp_SysStringLen` at `0x1801af15b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1801aee61`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1801aee61`

## string_xrefs

- `0x1801aef4e`: `CNwsHelper::WsStringCopy(&bstrErrorCode, faultDetail.errorCode)`
- `0x1801af012`: `CNwsHelper::WsStringCopy(&bstrMethod, faultDetail.method)`
- `0x1801af060`: `Soap fault detail: errorCode='%ls', message='%ls', id='%ls', method='%ls', RecommendedRetryIntervalInMins=%d`
- `0x1801aefac`: `CNwsHelper::WsStringCopy(&bstrMessage, faultDetail.message)`
- `0x1801aefdd`: `CNwsHelper::WsStringCopy(&bstrId, faultDetail.id)`

## pseudocode

```c

```
