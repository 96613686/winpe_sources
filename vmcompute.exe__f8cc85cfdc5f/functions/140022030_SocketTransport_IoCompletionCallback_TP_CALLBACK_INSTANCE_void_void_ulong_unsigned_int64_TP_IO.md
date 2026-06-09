# SocketTransport::IoCompletionCallback(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x140022030`
- end: `0x140022351`
- name: `?IoCompletionCallback@SocketTransport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `801`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14001629c`
- `0x14002035c`
- `0x1400205a4`
- `0x140022030`
- `0x140022358`
- `0x140022ca0`
- `0x14002302c`
- `0x14005bcd8`
- `0x140087500`
- `0x1400de8cc`
- `0x1400de984`
- `0x1401332f0`
- `0x140134048`
- `0x14025730c`
- `0x140257780`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400221aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140022244`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400222b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400221aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140022244`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400222b9`

## string_xrefs

- `0x140022091`: `SocketTransport_IoComplete`
- `0x1400220ec`: `onecore\vm\compute\common\transport\sockettransport.cpp`

## pseudocode

```c

```
