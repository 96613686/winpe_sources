# CRingBufferStreamReader::RingBufferRead(void *,void *,ulong,ulong *)

- ea: `0x1800ca950`
- end: `0x1800cad05`
- name: `?RingBufferRead@CRingBufferStreamReader@@CAJPEAX0KPEAK@Z`
- size: `949`
- prototype: `__int64 __fastcall(CRingBufferStreamReader *this, void *, size_t Size, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180013ec0`
- `0x180046e6c`
- `0x180049bfc`
- `0x18007aae4`
- `0x1800c8174`
- `0x1800c9e80`
- `0x1800ca950`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cabc6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cabe9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cabc6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cabe9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ca9d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800caadd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cabff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ca9d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800caadd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cabff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800caab6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cabac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800caab6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cabac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800cabd3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800cabd3`

## string_xrefs

- `0x1800caca6`: `RingBufferStreamReader::RingBufferRead => SP_AUDIO_STOPPED (before ReadFromRing)`
- `0x1800caa46`: `RingBufferStreamReader::RingBufferRead => SP_AUDIO_PAUSED (before ReadFromRing)`
- `0x1800cac22`: `RingBufferStreamReader::RingBufferRead => SP_AUDIO_PAUSED (after ReadFromRing)`
- `0x1800cac81`: `RingBufferStreamReader::RingBufferRead => SPERR_AUDIO_STOPPED_UNEXPECTEDLY (after ReadFromRing)`
- `0x1800cac67`: `RingBufferStreamReader::RingBufferRead wait failed with timeout %d`
- `0x1800cac3a`: `RingBufferStreamReader::RingBufferRead => SP_AUDIO_STOPPED (after ReadFromRing)`
- `0x1800cacd8`: `RingBufferStreamReader::RingBufferRead returning ERROR => 0x%08x`

## pseudocode

```c

```
