# xxxInitTerminal(tagTERMINAL *)

- ea: `0x14027821c`
- end: `0x1402785dc`
- name: `?xxxInitTerminal@@YAJPEAUtagTERMINAL@@@Z`
- size: `960`
- prototype: `NTSTATUS __fastcall(struct tagTERMINAL *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1402b3930`

## callees

- `0x14024d1a8`
- `0x14027821c`
- `0x1402aae2c`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `ntoskrnl!LpcRequestPort` at `0x1402784bd`
- `ntoskrnl!LpcRequestPort` at `0x1402784bd`
- `ntoskrnl!ExEventObjectType` at `0x14027831e`
- `ntoskrnl!ExEventObjectType` at `0x1402783b8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402782af`
- `ntoskrnl!KeWaitForSingleObject` at `0x14027854c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402782af`
- `ntoskrnl!KeWaitForSingleObject` at `0x14027854c`
- `ntoskrnl!LpcSendWaitReceivePort` at `0x140278503`
- `ntoskrnl!LpcSendWaitReceivePort` at `0x140278503`
- `ntoskrnl!ObfReferenceObject` at `0x140278285`
- `ntoskrnl!ObfReferenceObject` at `0x140278285`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140278346`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402783e0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140278346`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402783e0`
- `ntoskrnl!ZwCreateEvent` at `0x14027830a`
- `ntoskrnl!ZwCreateEvent` at `0x1402783a6`
- `ntoskrnl!ZwCreateEvent` at `0x14027830a`
- `ntoskrnl!ZwCreateEvent` at `0x1402783a6`
- `ntoskrnl!PsGetCurrentProcess` at `0x140278495`
- `ntoskrnl!PsGetCurrentProcess` at `0x140278523`
- `ntoskrnl!PsGetCurrentProcess` at `0x140278495`
- `ntoskrnl!PsGetCurrentProcess` at `0x140278523`
- `ntoskrnl!ZwClose` at `0x140278362`
- `ntoskrnl!ZwClose` at `0x1402783fc`
- `ntoskrnl!ZwClose` at `0x140278362`
- `ntoskrnl!ZwClose` at `0x1402783fc`
- `ntoskrnl!ObfDereferenceObject` at `0x140278410`
- `ntoskrnl!ObfDereferenceObject` at `0x140278449`
- `ntoskrnl!ObfDereferenceObject` at `0x140278458`
- `ntoskrnl!ObfDereferenceObject` at `0x140278578`
- `ntoskrnl!ObfDereferenceObject` at `0x1402785a4`
- `ntoskrnl!ObfDereferenceObject` at `0x140278410`
- `ntoskrnl!ObfDereferenceObject` at `0x140278449`
- `ntoskrnl!ObfDereferenceObject` at `0x140278458`
- `ntoskrnl!ObfDereferenceObject` at `0x140278578`
- `ntoskrnl!ObfDereferenceObject` at `0x1402785a4`
- `win32kbase!InitCreateSystemThreadsMsg` at `0x140278435`
- `win32kbase!InitCreateSystemThreadsMsg` at `0x140278435`
- `win32kbase!EnterCrit` at `0x1402782c0`
- `win32kbase!EnterCrit` at `0x140278560`
- `win32kbase!EnterCrit` at `0x1402782c0`
- `win32kbase!EnterCrit` at `0x140278560`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140278291`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140278479`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140278291`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140278479`
- `WIN32K!W32GetUserGdiSessionState` at `0x140278485`
- `WIN32K!W32GetUserGdiSessionState` at `0x140278513`
- `WIN32K!W32GetUserGdiSessionState` at `0x140278485`
- `WIN32K!W32GetUserGdiSessionState` at `0x140278513`
- `WIN32K!W32GetUserSessionState` at `0x1402784a6`
- `WIN32K!W32GetUserSessionState` at `0x1402784d4`
- `WIN32K!W32GetUserSessionState` at `0x1402784a6`
- `WIN32K!W32GetUserSessionState` at `0x1402784d4`

## pseudocode

```c

```
