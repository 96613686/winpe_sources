# CreateDesktopNotificationEvent(void *)

- ea: `0x1401ffb00`
- end: `0x1401ffda0`
- name: `?CreateDesktopNotificationEvent@@YAJPEAX@Z`
- size: `672`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1402b1f80`

## callees

- `0x140077cc8`
- `0x1401ffb00`
- `0x140200450`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!ZwOpenDirectoryObject` at `0x1401ffc09`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x1401ffc09`
- `ntoskrnl!KeDetachProcess` at `0x1401ffd75`
- `ntoskrnl!KeDetachProcess` at `0x1401ffd75`
- `ntoskrnl!KeAttachProcess` at `0x1401ffd17`
- `ntoskrnl!KeAttachProcess` at `0x1401ffd17`
- `ntoskrnl!ExEventObjectType` at `0x1401ffcb3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401ffce9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401ffce9`
- `ntoskrnl!ZwCreateEvent` at `0x1401ffc80`
- `ntoskrnl!ZwCreateEvent` at `0x1401ffc80`
- `ntoskrnl!ZwClose` at `0x1401ffc93`
- `ntoskrnl!ZwClose` at `0x1401ffd86`
- `ntoskrnl!ZwClose` at `0x1401ffc93`
- `ntoskrnl!ZwClose` at `0x1401ffd86`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401ffbc4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401ffc2e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401ffbc4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401ffc2e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401ffd67`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401ffd67`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401ffd07`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401ffd07`
- `WIN32K!W32GetUserSessionState` at `0x1401ffb59`
- `WIN32K!W32GetUserSessionState` at `0x1401ffca7`
- `WIN32K!W32GetUserSessionState` at `0x1401ffd23`
- `WIN32K!W32GetUserSessionState` at `0x1401ffd36`
- `WIN32K!W32GetUserSessionState` at `0x1401ffb59`
- `WIN32K!W32GetUserSessionState` at `0x1401ffca7`
- `WIN32K!W32GetUserSessionState` at `0x1401ffd23`
- `WIN32K!W32GetUserSessionState` at `0x1401ffd36`

## pseudocode

```c

```
