# CWASAudioBurstRead::ThreadProcImpl(void *)

- ea: `0x1800bcd50`
- end: `0x1800bcf44`
- name: `?ThreadProcImpl@CWASAudioBurstRead@@EEAAJPEAX@Z`
- size: `500`
- prototype: `int(CWASAudioBurstRead *__hidden this, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180013ec0`
- `0x1800a1818`
- `0x1800a18c0`
- `0x1800bb960`
- `0x1800bbf90`
- `0x1800bc1d0`
- `0x1800bcd50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800bcea2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800bcea2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bcddf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bce78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bcec4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bcddf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bce78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bcec4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bcdf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bceec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bcdf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bceec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bce3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bce3b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800bce2a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800bce2a`

## string_xrefs

- `0x1800bcd76`: `[%s] Audio processing thread started.`
- `0x1800bcdbe`: `[%s] AttachThreadToMMCSS. %x, %x`
- `0x1800bcf05`: `[%s] DetachThreadFromMMCSS, bResult: %d`
- `0x1800bcf1a`: `[%s] Audio processing thread finished, hr: %x`
- `0x1800bcd6c`: `CWASAudioBurstRead::ThreadProcImpl`

## pseudocode

```c

```
