# CLocalDisconnectPlugin::GetLoginname(ushort * *)

- ea: `0x18005af20`
- end: `0x18005b003`
- name: `?GetLoginname@CLocalDisconnectPlugin@@UEAAJPEAPEAG@Z`
- size: `227`
- prototype: `int(CLocalDisconnectPlugin *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180026218`
- `0x18005af20`
- `0x180078010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18005af9a`
- `msvcrt!wcsrchr` at `0x18005af9a`
- `msvcrt!wcstoul` at `0x18005afb5`
- `msvcrt!wcstoul` at `0x18005afb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005afc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005afc7`
- `OLEAUT32!__imp_SysFreeString` at `0x18005afd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005afd9`

## pseudocode

```c

```
