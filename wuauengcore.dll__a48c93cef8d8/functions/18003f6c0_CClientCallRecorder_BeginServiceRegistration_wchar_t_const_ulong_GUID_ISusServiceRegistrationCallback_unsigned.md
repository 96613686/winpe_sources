# CClientCallRecorder::BeginServiceRegistration(wchar_t const *,ulong,_GUID,ISusServiceRegistrationCallback *,unsigned __int64,char const *,_GUID *)

- ea: `0x18003f6c0`
- end: `0x18003fc89`
- name: `?BeginServiceRegistration@CClientCallRecorder@@UEAAJPEB_WKU_GUID@@PEAUISusServiceRegistrationCallback@@_KPEBDPEAU2@@Z`
- size: `1481`
- prototype: `__int64 __fastcall(CClientCallRecorder *this, wchar_t *, unsigned int, struct _GUID *, struct IUnknown *, void *, char *, struct _GUID *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000def4`
- `0x18001898c`
- `0x18003ca84`
- `0x18003d95c`
- `0x18003efbc`
- `0x18003f6c0`
- `0x18004a320`
- `0x18004a4a0`
- `0x1800c8030`
- `0x1800c880c`
- `0x1800c9054`
- `0x180105108`
- `0x180105194`
- `0x1801051cc`
- `0x180106dec`
- `0x18011b63c`
- `0x180238960`
- `0x180238984`
- `0x180239110`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fb37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fb37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003fb82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003fb82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f805`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f931`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fbe3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f805`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f931`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fbe3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003fbb4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003fbb4`

## string_xrefs

- `0x18003f914`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003fb0e`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003fbce`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003f73b`: `CClientCallRecorder::BeginServiceRegistration`

## pseudocode

```c

```
