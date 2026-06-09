# NotificationDispatcher::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180036050`
- end: `0x180036206`
- name: `?WndProc@NotificationDispatcher@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `438`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800134f8`
- `0x180036050`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800360bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800360bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180036134`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180036134`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036101`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036101`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800361bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800361bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003616a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003616a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18003606d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18003606d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18003614f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18003614f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x1800361c3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x1800361c3`

## pseudocode

```c

```
