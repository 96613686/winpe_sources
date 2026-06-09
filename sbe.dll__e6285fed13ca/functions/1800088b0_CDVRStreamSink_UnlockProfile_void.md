# CDVRStreamSink::UnlockProfile(void)

- ea: `0x1800088b0`
- end: `0x18000896a`
- name: `?UnlockProfile@CDVRStreamSink@@UEAAJXZ`
- size: `186`
- prototype: `__int64 __fastcall(CDVRStreamSink *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800088b0`
- `0x180057140`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000890c`
- `KERNEL32!LeaveCriticalSection` at `0x18000890c`
- `KERNEL32!EnterCriticalSection` at `0x1800088ca`
- `KERNEL32!EnterCriticalSection` at `0x1800088ca`

## string_xrefs

- `0x180008933`: `multimedia\dshow\filters\sbe\dvrfilters\dvrstreamsink\dvrstreamsink.cpp`
- `0x18000891e`: `* SUCCEEDED : DVRStreamSink::UnlockProfile [%p]`
- `0x18000893f`: `ERROR: %s(%u); DVRStreamSink::UnlockProfile [%p] : returning error %08xh`

## pseudocode

```c

```
