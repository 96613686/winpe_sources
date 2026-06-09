# CClientCallRecorder::BeginFindUpdates(wchar_t const *,ulong,_GUID,wchar_t const *,int,int,int,int,ulong,ulong *,tagProxySettings const *,ISusSearchCallback6 *,unsigned __int64,char const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,_GUID *)

- ea: `0x18003fc90`
- end: `0x180040547`
- name: `?BeginFindUpdates@CClientCallRecorder@@UEAAJPEB_WKU_GUID@@0HHHHKPEAKPEBUtagProxySettings@@PEAUISusSearchCallback6@@_KPEBD0000PEAU2@@Z`
- size: `2231`
- prototype: `__int64 __fastcall(CClientCallRecorder *this, wchar_t *, unsigned int, struct _GUID *, wchar_t *, int, int, int, int, unsigned int, unsigned int *, const struct tagProxySettings *, struct ISusSearchCallback6 *, unsigned __int64, char *, wchar_t *, wchar_t *, wchar_t *, wchar_t *, struct _GUID *)`
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000def4`
- `0x180031524`
- `0x18003ca84`
- `0x18003d95c`
- `0x18003efbc`
- `0x18003fc90`
- `0x18004a320`
- `0x18004a4a0`
- `0x18004e33c`
- `0x18004e75c`
- `0x180052a68`
- `0x180052c68`
- `0x1800c0140`
- `0x1800c05b4`
- `0x1800c0e80`
- `0x1800c0f1c`
- `0x1800c58f8`
- `0x1800c880c`
- `0x1800c887c`
- `0x180105194`
- `0x1801051cc`
- `0x180106214`
- `0x180106274`
- `0x1801062d4`
- `0x180106dec`
- `0x18011b63c`
- `0x18012b618`
- `0x18012bed4`
- `0x180238960`
- `0x180238984`
- `0x180239110`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004043f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004043f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004028f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004028f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004046e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004046e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003feeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004002d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800404ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003feeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004002d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800404ea`

## string_xrefs

- `0x18003ffdb`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x180040272`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003fd4d`: `CClientCallRecorder::BeginFindUpdates`
- `0x180040187`: `SkipSelfUpdateCheck search flag set for serverId: %ws`

## pseudocode

```c

```
