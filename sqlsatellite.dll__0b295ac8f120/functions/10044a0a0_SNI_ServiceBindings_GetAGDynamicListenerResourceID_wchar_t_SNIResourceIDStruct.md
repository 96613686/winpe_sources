# SNI_ServiceBindings::GetAGDynamicListenerResourceID(wchar_t *,SNIResourceIDStruct *)

- ea: `0x10044a0a0`
- end: `0x10044a42e`
- name: `?GetAGDynamicListenerResourceID@SNI_ServiceBindings@@SAKPEA_WPEAUSNIResourceIDStruct@@@Z`
- size: `910`
- prototype: `unsigned int __fastcall(LPWSTR AddressString, struct SNIResourceIDStruct *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1004269b0`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x10044a0a0`
- `0x10044a440`
- `0x100486af0`

## import_xrefs

- `WS2_32!WSAStringToAddressW` at `0x10044a16c`
- `WS2_32!WSAStringToAddressW` at `0x10044a267`
- `WS2_32!WSAStringToAddressW` at `0x10044a16c`
- `WS2_32!WSAStringToAddressW` at `0x10044a267`
- `WS2_32!__imp_WSAGetLastError` at `0x10044a20d`
- `WS2_32!__imp_WSAGetLastError` at `0x10044a321`
- `WS2_32!__imp_WSAGetLastError` at `0x10044a20d`
- `WS2_32!__imp_WSAGetLastError` at `0x10044a321`

## string_xrefs

- `0x10044a0db`: `sql\common\dk\sni\src\SNI_ServiceBindings.cpp`
- `0x10044a0e7`: `SNI_ServiceBindings::GetAGDynamicListenerResourceID`

## pseudocode

```c

```
