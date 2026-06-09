# CFilePicker::_FailIfCallerInAppContainer(void)

- ea: `0x18005aacc`
- end: `0x18005ab35`
- name: `?_FailIfCallerInAppContainer@CFilePicker@@AEAAJXZ`
- size: `105`
- prototype: `__int64 __fastcall(CFilePicker *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180052df0`
- `0x180054780`
- `0x180057700`
- `0x180057760`
- `0x1800577c0`
- `0x180057840`

## callees

- `0x18005aacc`
- `0x18007435c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18005ab10`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18005ab10`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18005aae0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18005aae0`

## pseudocode

```c

```
