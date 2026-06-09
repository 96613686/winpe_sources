# CSpCommunicator::FreeQueue(CSpBasicQueue<CSpQueueNode<SPCALL>,1,0> *,ATL::CComAutoCriticalSection *)

- ea: `0x1800ea47c`
- end: `0x1800ea5c5`
- name: `?FreeQueue@CSpCommunicator@@AEAAXPEAV?$CSpBasicQueue@V?$CSpQueueNode@USPCALL@@@@$00$0A@@@PEAVCComAutoCriticalSection@ATL@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(CSpCommunicator *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ea5cc`

## callees

- `0x180013ec0`
- `0x18007a2dc`
- `0x1800ea47c`
- `0x1800eaae0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ea562`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ea562`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ea515`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ea553`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ea515`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ea553`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ea495`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ea495`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ea5be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea58a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea58a`

## pseudocode

```c

```
