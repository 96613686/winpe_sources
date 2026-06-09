# CEventNotifier::CreateEnumEventInfo(ushort *,IWiaItemInternal *,_GUID const *,IEnumWIA_DEV_CAPS * *)

- ea: `0x18003bea0`
- end: `0x18003c29c`
- name: `?CreateEnumEventInfo@CEventNotifier@@QEAAJPEAGPEAUIWiaItemInternal@@PEBU_GUID@@PEAPEAUIEnumWIA_DEV_CAPS@@@Z`
- size: `1020`
- prototype: `__int64 __fastcall(CEventNotifier *this, unsigned __int16 *, struct IWiaItemInternal *, const struct _GUID *, struct IEnumWIA_DEV_CAPS **)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting`

## callers

- `0x180062150`

## callees

- `0x1800045e0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x180025aec`
- `0x180025e4c`
- `0x180026380`
- `0x18002c868`
- `0x18002c8b0`
- `0x180033884`
- `0x180033cc0`
- `0x180034658`
- `0x18003b7d0`
- `0x18003bea0`
- `0x18003c610`
- `0x18005a490`
- `0x18005a59c`
- `0x1800775e4`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003c217`
- `KERNEL32!LocalFree` at `0x18003c217`
- `KERNEL32!LocalAlloc` at `0x18003c027`
- `KERNEL32!LocalAlloc` at `0x18003c027`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c123`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c134`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c145`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c174`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c123`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c134`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c145`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c174`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c1dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c1ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c201`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c1dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c1ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c201`

## string_xrefs

- `0x18003bed7`: `CEventNotifier::CreateEnumEventInfo`
- `0x18003bfa6`: `CreateEnumEventInfo() : No handler registered for this event`
- `0x18003bfcc`: `CreateEnumEventInfo() : No handler registered for this event`

## pseudocode

```c

```
