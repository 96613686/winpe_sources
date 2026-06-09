# Windows::Logger::Logger(std::vector<_GUID,std::allocator<_GUID>> const &,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::filesystem::path,bool,uint)

- ea: `0x180066684`
- end: `0x180066b3f`
- name: `??0Logger@Windows@@QEAA@AEBV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@V?$basic_zstring_view@_W@wil@@1Vpath@filesystem@3@_NI@Z`
- size: `1211`
- prototype: `Windows::Logger *__fastcall(Windows::Logger *this, __int64, __int128 *, LPCWSTR *, void *, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18003224c`

## callees

- `0x18000f248`
- `0x18000fde8`
- `0x180010e80`
- `0x1800112d0`
- `0x180011320`
- `0x180011534`
- `0x180011680`
- `0x1800388c4`
- `0x180066684`
- `0x180066bf4`
- `0x180066c88`
- `0x1800dd930`
- `0x1800dff58`
- `0x1800e4a70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066a87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066a87`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18006678e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18006678e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800667a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800667a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006682f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006682f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066a2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066a59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066a2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066a59`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800669a6`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800669a6`
- `api-ms-win-eventing-legacy-l1-1-0!QueryTraceW` at `0x1800669c3`
- `api-ms-win-eventing-legacy-l1-1-0!QueryTraceW` at `0x1800669c3`

## string_xrefs

- `0x180066b1a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Logger.cpp`
- `0x180066b2c`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Logger.cpp`

## pseudocode

```c

```
