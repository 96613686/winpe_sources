# CChangeNotify::PendingCallbacks(HWND__ *,int)

- ea: `0x1800ab664`
- end: `0x1800ab8e7`
- name: `?PendingCallbacks@CChangeNotify@@QEAAXPEAUHWND__@@H@Z`
- size: `643`
- prototype: `void(CChangeNotify *__hidden this, HWND, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800ab030`
- `0x18020aca0`

## callees

- `0x1800ab664`
- `0x1800cb754`
- `0x1800ccbd0`
- `0x18010d030`
- `0x1803a4cb0`
- `0x1803a57e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab87e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab87e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800ab801`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800ab801`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ab86a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ab86a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab6b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab6b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab6a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab6a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab7c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab7c9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800ab784`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800ab784`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ab743`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ab743`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ab76e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ab76e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800ab7df`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800ab7df`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1800ab8c0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1800ab8c0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1800ab731`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1800ab731`

## pseudocode

```c

```
