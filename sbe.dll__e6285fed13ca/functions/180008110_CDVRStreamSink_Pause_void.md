# CDVRStreamSink::Pause(void)

- ea: `0x180008110`
- end: `0x180008266`
- name: `?Pause@CDVRStreamSink@@UEAAJXZ`
- size: `342`
- prototype: `__int64 __fastcall(CDVRStreamSink *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180007a98`
- `0x180007bf0`
- `0x180008110`
- `0x180008680`
- `0x180032a3c`
- `0x180032fe0`
- `0x180056650`
- `0x180057140`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800081d7`
- `KERNEL32!LeaveCriticalSection` at `0x18000820b`
- `KERNEL32!LeaveCriticalSection` at `0x1800081d7`
- `KERNEL32!LeaveCriticalSection` at `0x18000820b`
- `KERNEL32!EnterCriticalSection` at `0x18000815e`
- `KERNEL32!EnterCriticalSection` at `0x1800081bf`
- `KERNEL32!EnterCriticalSection` at `0x18000815e`
- `KERNEL32!EnterCriticalSection` at `0x1800081bf`

## string_xrefs

- `0x18000812a`: `* ENTER : DVRStreamSink::Pause [%p]`
- `0x18000821b`: `* SUCCEEDED : DVRStreamSink::Pause [%p]`
- `0x180008232`: `multimedia\dshow\filters\sbe\dvrfilters\dvrstreamsink\dvrstreamsink.cpp`
- `0x18000823e`: `ERROR: %s(%u); DVRStreamSink::Pause [%p] : returning error %08xh`

## pseudocode

```c

```
