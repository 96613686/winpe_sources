# SBF2::CComSBFFile::CreateFileW(IUnknown *,ushort *,ulong,ulong,ulong)

- ea: `0x18009c360`
- end: `0x18009c546`
- name: `?CreateFileW@CComSBFFile@SBF2@@UEAAJPEAUIUnknown@@PEAGKKK@Z`
- size: `486`
- prototype: `int(SBF2::CComSBFFile *__hidden this, struct IUnknown *, unsigned __int16 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001c00`
- `0x18000256c`
- `0x18000624c`
- `0x18000ca14`
- `0x18000ca64`
- `0x18009c360`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18009c51e`
- `KERNEL32!LeaveCriticalSection` at `0x18009c51e`
- `KERNEL32!EnterCriticalSection` at `0x18009c39d`
- `KERNEL32!EnterCriticalSection` at `0x18009c39d`

## string_xrefs

- `0x18009c47d`: `multimedia\dshow\filters\sbe\sbf\sbfcom.cpp`
- `0x18009c4ea`: `multimedia\dshow\filters\sbe\sbf\sbfcom.cpp`

## pseudocode

```c

```
