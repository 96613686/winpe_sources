# CDataSrc::CreateSession(IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x180092080`
- end: `0x1800923d8`
- name: `?CreateSession@CDataSrc@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAU2@@Z`
- size: `856`
- prototype: `__int64 __fastcall(CDataSrc *__hidden this, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x180038f08`
- `0x180091e08`
- `0x180092080`
- `0x1800923e0`
- `0x180092498`
- `0x18009260c`
- `0x180092e64`
- `0x1800938b0`
- `0x18015b194`
- `0x180188dc0`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800920ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800920ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092286`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092286`
- `ntdll!NtClose` at `0x18009227c`
- `ntdll!NtClose` at `0x18009227c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800920a9`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800920a9`

## pseudocode

```c

```
