# WdcTraceControl::GetImageName(unsigned __int64,ushort * *,int)

- ea: `0x18000ff88`
- end: `0x18001019a`
- name: `?GetImageName@WdcTraceControl@@QEAAJ_KPEAPEAGH@Z`
- size: `530`
- prototype: `__int64 __fastcall(WdcTraceControl *__hidden this, unsigned __int64, unsigned __int16 **, int)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180002ad0`
- `0x1800076e0`
- `0x18000b9e0`
- `0x18000e400`
- `0x1800158c0`
- `0x180021820`
- `0x18002375c`
- `0x180029a78`
- `0x18002d2c8`
- `0x18002fda8`
- `0x180038024`
- `0x1800792a8`

## callees

- `0x18000b854`
- `0x18000ff88`
- `0x180086010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800100fd`
- `KERNEL32!LeaveCriticalSection` at `0x1800100fd`
- `KERNEL32!EnterCriticalSection` at `0x18000ffd6`
- `KERNEL32!EnterCriticalSection` at `0x18000ffd6`
- `KERNEL32!TryEnterCriticalSection` at `0x1800100dc`
- `KERNEL32!TryEnterCriticalSection` at `0x1800100dc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800100b9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800100b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001013c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001013c`

## pseudocode

```c

```
