# SpLoadFile(ushort *,ushort *,IStream * *,ISpeechResourceLoader *,ulong,ulong,SPGRAMMAROPTIONS,ushort * *,ushort * *)

- ea: `0x1800fc48c`
- end: `0x1800fc7de`
- name: `?SpLoadFile@@YAJPEAG0PEAPEAUIStream@@PEAUISpeechResourceLoader@@KKW4SPGRAMMAROPTIONS@@PEAPEAG4@Z`
- size: `850`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, struct IStream **@<r8>, struct ISpeechResourceLoader *@<r9>, DWORD, unsigned int, enum SPGRAMMAROPTIONS, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180073980`
- `0x1800dc794`
- `0x18019b92c`
- `0x1801aa930`

## callees

- `0x18000a590`
- `0x18000bec4`
- `0x18000cdb0`
- `0x18001ae00`
- `0x180021970`
- `0x18007d31c`
- `0x1800faf1c`
- `0x1800fb04c`
- `0x1800fb890`
- `0x1800fc48c`
- `0x18027b374`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fc7b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fc7b1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800fc4cc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800fc4cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fc735`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fc735`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fc793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fc793`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc602`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc60d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc618`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc602`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc60d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc618`
- `urlmon!URLOpenBlockingStreamW` at `0x1800fc76b`
- `urlmon!URLOpenBlockingStreamW` at `0x1800fc76b`
- `urlmon!CoInternetParseUrl` at `0x1800fc6a1`
- `urlmon!CoInternetParseUrl` at `0x1800fc6a1`

## pseudocode

```c

```
