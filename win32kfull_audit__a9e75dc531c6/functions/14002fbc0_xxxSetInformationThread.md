# xxxSetInformationThread

- ea: `0x14002fbc0`
- end: `0x140030212`
- name: `xxxSetInformationThread`
- size: `1618`
- prototype: `NTSTATUS __fastcall(void *, int, _QWORD *, int)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x14002fbc0`
- `0x1401fb6b0`

## callees

- `0x140004350`
- `0x140028788`
- `0x14002fa60`
- `0x14002fbc0`
- `0x14003061c`
- `0x140030760`
- `0x1400c8954`
- `0x1400e2cb0`
- `0x1400e8f88`
- `0x14020de80`
- `0x140281158`
- `0x140292cdc`
- `0x1402a71e8`
- `0x1402d43b4`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsThreadType` at `0x14002fbf9`
- `ntoskrnl!PsThreadType` at `0x14002fdc5`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002fe5f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002fe5f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002fc1c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002fdec`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002fc1c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002fdec`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fcab`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fe35`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fcab`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fe35`
- `win32kbase!SetCsrApiPortHandle` at `0x140030133`
- `win32kbase!SetCsrApiPortHandle` at `0x140030133`
- `win32kbase!EtwTraceConvertibleState` at `0x14003001d`
- `win32kbase!EtwTraceConvertibleState` at `0x14003001d`
- `win32kbase!EtwTraceDockState` at `0x140030201`
- `win32kbase!EtwTraceDockState` at `0x140030201`
- `win32kbase!RtlLoadStringOrError` at `0x14003000a`
- `win32kbase!RtlLoadStringOrError` at `0x1400301ee`
- `win32kbase!RtlLoadStringOrError` at `0x14003000a`
- `win32kbase!RtlLoadStringOrError` at `0x1400301ee`
- `win32kbase!PostWinlogonMessage` at `0x14002fecb`
- `win32kbase!PostWinlogonMessage` at `0x14002fecb`
- `win32kbase!ValidateHwnd` at `0x14002fe7f`
- `win32kbase!ValidateHwnd` at `0x14002fe7f`
- `WIN32K!W32GetUserSessionState` at `0x14002fce1`
- `WIN32K!W32GetUserSessionState` at `0x14002fcf6`
- `WIN32K!W32GetUserSessionState` at `0x14002fd4b`
- `WIN32K!W32GetUserSessionState` at `0x14002fd6c`
- `WIN32K!W32GetUserSessionState` at `0x14002fd7f`
- `WIN32K!W32GetUserSessionState` at `0x14002fda1`
- `WIN32K!W32GetUserSessionState` at `0x14002feb1`
- `WIN32K!W32GetUserSessionState` at `0x14002ff19`
- `WIN32K!W32GetUserSessionState` at `0x14002ff2c`
- `WIN32K!W32GetUserSessionState` at `0x14002ff38`
- `WIN32K!W32GetUserSessionState` at `0x14002ff56`
- `WIN32K!W32GetUserSessionState` at `0x14002ffe0`
- `WIN32K!W32GetUserSessionState` at `0x140030091`
- `WIN32K!W32GetUserSessionState` at `0x1400301a8`
- `WIN32K!W32GetUserSessionState` at `0x1400301c4`
- `WIN32K!W32GetUserSessionState` at `0x14002fce1`
- `WIN32K!W32GetUserSessionState` at `0x14002fcf6`
- `WIN32K!W32GetUserSessionState` at `0x14002fd4b`
- `WIN32K!W32GetUserSessionState` at `0x14002fd6c`
- `WIN32K!W32GetUserSessionState` at `0x14002fd7f`
- `WIN32K!W32GetUserSessionState` at `0x14002fda1`
- `WIN32K!W32GetUserSessionState` at `0x14002feb1`
- `WIN32K!W32GetUserSessionState` at `0x14002ff19`
- `WIN32K!W32GetUserSessionState` at `0x14002ff2c`
- `WIN32K!W32GetUserSessionState` at `0x14002ff38`
- `WIN32K!W32GetUserSessionState` at `0x14002ff56`
- `WIN32K!W32GetUserSessionState` at `0x14002ffe0`
- `WIN32K!W32GetUserSessionState` at `0x140030091`
- `WIN32K!W32GetUserSessionState` at `0x1400301a8`
- `WIN32K!W32GetUserSessionState` at `0x1400301c4`

## pseudocode

```c

```
