# CExplorerBrowser::_SwitchView(IShellFolder *,_ITEMIDLIST_ABSOLUTE const *,int,TelemetryCorrelationVectorServiceProvider *)

- ea: `0x1800584c4`
- end: `0x180058b91`
- name: `?_SwitchView@CExplorerBrowser@@AEAAJPEAUIShellFolder@@PEBU_ITEMIDLIST_ABSOLUTE@@HPEAVTelemetryCorrelationVectorServiceProvider@@@Z`
- size: `1741`
- prototype: `__int64 __usercall@<rax>(CExplorerBrowser *__hidden this@<rcx>, IUnknown *punk@<rdx>, const struct _ITEMIDLIST_ABSOLUTE *@<r8>, int@<r9d>, struct TelemetryCorrelationVectorServiceProvider *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018e10`

## callees

- `0x18000d4b0`
- `0x18000d4c0`
- `0x18000f5a4`
- `0x18001aeb8`
- `0x18001afe8`
- `0x180026dc4`
- `0x1800584c4`
- `0x180058b98`
- `0x180058bec`
- `0x180093790`
- `0x18011977c`
- `0x18013cd2c`
- `0x18015a4d4`
- `0x1801654c8`
- `0x18016f60c`
- `0x180185848`
- `0x180233280`
- `0x1802b79cc`
- `0x180571010`

## import_xrefs

- `USER32!MapWindowPoints` at `0x1800589ef`
- `USER32!MapWindowPoints` at `0x1800589ef`
- `USER32!GetFocus` at `0x180058aaf`
- `USER32!GetFocus` at `0x180058aaf`
- `USER32!SetFocus` at `0x18005886b`
- `USER32!SetFocus` at `0x18005886b`
- `USER32!GetWindowRect` at `0x1800589cd`
- `USER32!GetWindowRect` at `0x1800589cd`
- `USER32!GetParent` at `0x180058aa5`
- `USER32!GetParent` at `0x180058abb`
- `USER32!GetParent` at `0x180058aa5`
- `USER32!GetParent` at `0x180058abb`
- `USER32!SendMessageW` at `0x180058b56`
- `USER32!SendMessageW` at `0x180058b56`
- `USER32!SetWindowPos` at `0x180058b41`
- `USER32!SetWindowPos` at `0x180058b41`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x180058570`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800585ae`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18005860d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x180058570`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800585ae`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18005860d`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x180058600`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x180058600`
- `Windows.Storage!ILFree` at `0x18005878a`
- `Windows.Storage!ILFree` at `0x18005878a`

## pseudocode

```c

```
