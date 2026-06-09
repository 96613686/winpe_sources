# CUHAppXHandler::GenerateDownloadRequest(tagSusDownloadData *,ISusHandlerNotification *,int *,int *,short *,long *,int *)

- ea: `0x180207a50`
- end: `0x1802085cc`
- name: `?GenerateDownloadRequest@CUHAppXHandler@@UEAAJPEAUtagSusDownloadData@@PEAUISusHandlerNotification@@PEAH2PEAFPEAJ2@Z`
- size: `2940`
- prototype: `__int64 __fastcall(struct CAppxStreamingDataSourceFactory **this, struct tagSusDownloadData *, struct ISusHandlerNotification *, int *, int *, __int16 *, int *, int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180113ae8`
- `0x18012b618`
- `0x18012bed4`
- `0x18012bf80`
- `0x180136ea4`
- `0x1802023ac`
- `0x180203a94`
- `0x180205fb4`
- `0x180206528`
- `0x180207700`
- `0x180207a50`
- `0x180209ddc`
- `0x180217e80`
- `0x180219a18`
- `0x18021d3a8`
- `0x18021f25c`
- `0x180238960`
- `0x180238984`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180208093`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802082c4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180208093`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802082c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180207c93`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180207c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180207cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020819d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180207cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020819d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180207c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18020856c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180207c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18020856c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180208115`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180208115`
- `OLEAUT32!__imp_SysStringLen` at `0x180207b2b`
- `OLEAUT32!__imp_SysStringLen` at `0x180207b2b`

## string_xrefs

- `0x180207e96`: `AppX GDR: GenerateUri requested not to call stage package.`
- `0x1802080de`: `AppX GDR: Waiting %lu ms for download execute or completion event.`
- `0x18020833b`: `AppX GDR: Successfully generated a download request. Update Id: %ws, cFiles=%lu`
- `0x18020840d`: `AppX GDR for update %ws`
- `0x18020821f`: `AppX GDR: EventCompletion seen. Run is complete.`
- `0x18020846d`: `Appx GDR: Marking download size calculation for update %ws as complete.`

## pseudocode

```c

```
