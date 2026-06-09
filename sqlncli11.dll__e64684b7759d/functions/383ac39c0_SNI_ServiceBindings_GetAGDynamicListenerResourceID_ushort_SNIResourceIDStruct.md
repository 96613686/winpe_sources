# SNI_ServiceBindings::GetAGDynamicListenerResourceID(ushort *,SNIResourceIDStruct *)

- ea: `0x383ac39c0`
- end: `0x383ac3da7`
- name: `?GetAGDynamicListenerResourceID@SNI_ServiceBindings@@SAKPEAGPEAUSNIResourceIDStruct@@@Z`
- size: `999`
- prototype: `unsigned int __fastcall(LPWSTR AddressString, struct SNIResourceIDStruct *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x383ab35b0`

## callees

- `0x3838434c0`
- `0x383846430`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0c30`
- `0x383ac39c0`
- `0x383ac3db0`

## import_xrefs

- `WS2_32!WSAStringToAddressW` at `0x383ac3a73`
- `WS2_32!WSAStringToAddressW` at `0x383ac3b8b`
- `WS2_32!WSAStringToAddressW` at `0x383ac3a73`
- `WS2_32!WSAStringToAddressW` at `0x383ac3b8b`
- `WS2_32!__imp_WSAGetLastError` at `0x383ac3b21`
- `WS2_32!__imp_WSAGetLastError` at `0x383ac3c52`
- `WS2_32!__imp_WSAGetLastError` at `0x383ac3b21`
- `WS2_32!__imp_WSAGetLastError` at `0x383ac3c52`

## pseudocode

```c

```
