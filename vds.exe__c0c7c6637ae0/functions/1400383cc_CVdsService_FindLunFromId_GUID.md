# CVdsService::FindLunFromId(_GUID &)

- ea: `0x1400383cc`
- end: `0x140038540`
- name: `?FindLunFromId@CVdsService@@CAPEAGAEAU_GUID@@@Z`
- size: `372`
- prototype: `unsigned __int16 *__fastcall(struct _GUID *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001980`
- `0x140037320`
- `0x140038a70`

## callees

- `0x1400383cc`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003850e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003850e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003843a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003843a`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140038458`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140038458`
- `vdsutil!VdsTraceEx` at `0x1400384d8`
- `vdsutil!VdsTraceEx` at `0x140038500`
- `vdsutil!VdsTraceEx` at `0x1400384d8`
- `vdsutil!VdsTraceEx` at `0x140038500`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400383ff`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400383ff`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003851a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003851a`

## string_xrefs

- `0x1400383ee`: `CVdsService::FindLunFromId()`
- `0x1400384c7`: `CVdsService::FindLunFromId, 1 LunId:{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}`
- `0x1400384f4`: `CVdsService::FindLunFromId, 2 disk path %ws`

## pseudocode

```c

```
