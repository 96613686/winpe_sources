# CConnectionEx::CRDPCallback::StopScreenUpdates(void)

- ea: `0x180088210`
- end: `0x180088379`
- name: `?StopScreenUpdates@CRDPCallback@CConnectionEx@@UEAAJXZ`
- size: `361`
- prototype: `__int64 __fastcall(CConnectionEx::CRDPCallback *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180009940`
- `0x180012c90`
- `0x1800139c0`
- `0x180015310`
- `0x180088210`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008823d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008823d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088286`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088297`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088286`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088297`

## string_xrefs

- `0x180088261`: `CConnectionEx::CRDPCallback::StopScreenUpdates called after BrokenConnection was signaled. Returning ERROR_NOT_CONNECTED`
- `0x1800882c3`: `Ignoring StopScreenUpdates in shadow state.`
- `0x180088341`: `CConnectionEx::CRDPCallback::StopScreenUpdates`
- `0x18008833a`: `Session->StopScreenUpdates failed: 0x%x in %s`

## pseudocode

```c

```
