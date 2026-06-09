# CConnectionEx::CRDPCallback::StopScreenUpdates(void)

- ea: `0x180084970`
- end: `0x180084ac6`
- name: `?StopScreenUpdates@CRDPCallback@CConnectionEx@@UEAAJXZ`
- size: `342`
- prototype: `__int64 __fastcall(CConnectionEx::CRDPCallback *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000a210`
- `0x180012480`
- `0x180013150`
- `0x1800148f0`
- `0x180084970`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008499d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008499d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800849e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800849eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800849e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800849eb`

## string_xrefs

- `0x1800849bb`: `CConnectionEx::CRDPCallback::StopScreenUpdates called after BrokenConnection was signaled. Returning ERROR_NOT_CONNECTED`
- `0x180084a11`: `Ignoring StopScreenUpdates in shadow state.`
- `0x180084a8f`: `CConnectionEx::CRDPCallback::StopScreenUpdates`
- `0x180084a88`: `Session->StopScreenUpdates failed: 0x%x in %s`

## pseudocode

```c

```
