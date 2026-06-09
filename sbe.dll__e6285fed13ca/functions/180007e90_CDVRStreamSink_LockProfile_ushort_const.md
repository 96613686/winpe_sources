# CDVRStreamSink::LockProfile(ushort const *)

- ea: `0x180007e90`
- end: `0x180008003`
- name: `?LockProfile@CDVRStreamSink@@UEAAJPEBG@Z`
- size: `371`
- prototype: `int(CDVRStreamSink *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180007d10`
- `0x180007e90`
- `0x180030838`
- `0x180032a3c`
- `0x180032afc`
- `0x180057140`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180007f92`
- `KERNEL32!LeaveCriticalSection` at `0x180007f92`
- `KERNEL32!EnterCriticalSection` at `0x180007eb4`
- `KERNEL32!EnterCriticalSection` at `0x180007eb4`
- `KERNEL32!lstrcmpiW` at `0x180007f74`
- `KERNEL32!lstrcmpiW` at `0x180007f74`

## string_xrefs

- `0x180007fca`: `multimedia\dshow\filters\sbe\dvrfilters\dvrstreamsink\dvrstreamsink.cpp`
- `0x180007fa9`: `* SUCCEEDED : DVRStreamSink::LockProfile(%s) [%p]`
- `0x180007fd6`: `ERROR: %s(%u); DVRStreamSink::LockProfile(%s) [%p] : returning error %08xh`

## pseudocode

```c

```
