# CDlpTask::ProgressHandlerAction(IDlpAction *,ulong,ulong *)

- ea: `0x18006b8f4`
- end: `0x18006c00c`
- name: `?ProgressHandlerAction@CDlpTask@@AEAAJPEAVIDlpAction@@KPEAK@Z`
- size: `1816`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, struct IDlpAction *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180057498`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18006b8f4`
- `0x18007bd14`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006bd74`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006be2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006bf9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006bd74`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006be2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006bf9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bfc2`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bfc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b965`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006bd98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b965`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006bd98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bdbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bfdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bdbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bfdc`

## string_xrefs

- `0x18006ba10`: `CDlpTask::ProgressHandlerAction`
- `0x18006bd33`: `ProgressHandlerAction FinalUpdate: 0x%X, 0x%I64X / 0x%I64X, 0x%I64X`

## pseudocode

```c

```
