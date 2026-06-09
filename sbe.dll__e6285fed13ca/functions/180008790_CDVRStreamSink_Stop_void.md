# CDVRStreamSink::Stop(void)

- ea: `0x180008790`
- end: `0x18000889f`
- name: `?Stop@CDVRStreamSink@@UEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(CDVRStreamSink *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180007a98`
- `0x180007bf0`
- `0x180008724`
- `0x180008790`
- `0x180056650`
- `0x180057140`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000883d`
- `KERNEL32!LeaveCriticalSection` at `0x180008846`
- `KERNEL32!LeaveCriticalSection` at `0x18000883d`
- `KERNEL32!LeaveCriticalSection` at `0x180008846`
- `KERNEL32!EnterCriticalSection` at `0x1800087cd`
- `KERNEL32!EnterCriticalSection` at `0x1800087d7`
- `KERNEL32!EnterCriticalSection` at `0x1800087cd`
- `KERNEL32!EnterCriticalSection` at `0x1800087d7`

## string_xrefs

- `0x18000886d`: `multimedia\dshow\filters\sbe\dvrfilters\dvrstreamsink\dvrstreamsink.cpp`
- `0x1800087a7`: `* ENTER : DVRStreamSink::Stop [%p]`
- `0x180008858`: `* SUCCEEDED : DVRStreamSink::Stop [%p]`
- `0x180008879`: `ERROR: %s(%u); DVRStreamSink::Stop [%p] : returning error %08xh`

## pseudocode

```c

```
