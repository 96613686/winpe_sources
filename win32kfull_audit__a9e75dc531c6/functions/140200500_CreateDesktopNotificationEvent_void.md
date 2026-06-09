# CreateDesktopNotificationEvent(void *)

- ea: `0x140200500`
- end: `0x1402007a0`
- name: `?CreateDesktopNotificationEvent@@YAJPEAX@Z`
- size: `672`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1402b3930`

## callees

- `0x1400a4a38`
- `0x140200500`
- `0x140200e50`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!ZwOpenDirectoryObject` at `0x140200609`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x140200609`
- `ntoskrnl!KeDetachProcess` at `0x140200775`
- `ntoskrnl!KeDetachProcess` at `0x140200775`
- `ntoskrnl!KeAttachProcess` at `0x140200717`
- `ntoskrnl!KeAttachProcess` at `0x140200717`
- `ntoskrnl!ExEventObjectType` at `0x1402006b3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402006e9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402006e9`
- `ntoskrnl!ZwCreateEvent` at `0x140200680`
- `ntoskrnl!ZwCreateEvent` at `0x140200680`
- `ntoskrnl!ZwClose` at `0x140200693`
- `ntoskrnl!ZwClose` at `0x140200786`
- `ntoskrnl!ZwClose` at `0x140200693`
- `ntoskrnl!ZwClose` at `0x140200786`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402005c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14020062e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402005c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14020062e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140200767`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140200767`
- `WIN32K!W32GetUserGdiSessionState` at `0x140200707`
- `WIN32K!W32GetUserGdiSessionState` at `0x140200707`
- `WIN32K!W32GetUserSessionState` at `0x140200559`
- `WIN32K!W32GetUserSessionState` at `0x1402006a7`
- `WIN32K!W32GetUserSessionState` at `0x140200723`
- `WIN32K!W32GetUserSessionState` at `0x140200736`
- `WIN32K!W32GetUserSessionState` at `0x140200559`
- `WIN32K!W32GetUserSessionState` at `0x1402006a7`
- `WIN32K!W32GetUserSessionState` at `0x140200723`
- `WIN32K!W32GetUserSessionState` at `0x140200736`

## pseudocode

```c

```
