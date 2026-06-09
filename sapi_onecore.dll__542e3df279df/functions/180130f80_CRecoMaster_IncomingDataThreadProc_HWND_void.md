# CRecoMaster::IncomingDataThreadProc(HWND__ *,void *)

- ea: `0x180130f80`
- end: `0x180131076`
- name: `?IncomingDataThreadProc@CRecoMaster@@QEAAJPEAUHWND__@@PEAX@Z`
- size: `246`
- prototype: `__int64 __fastcall(CRecoMaster *__hidden this, HWND, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180137ca0`

## callees

- `0x180013ec0`
- `0x180050d0c`
- `0x180130f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180131035`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180131035`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180131048`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180131048`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180130fbe`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180130fbe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18013100a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18013100a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x180130fef`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x180130fef`

## string_xrefs

- `0x180131056`: `Reco Master incoming data thread terminated with code %X`

## pseudocode

```c

```
