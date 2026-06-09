# Windows::System::Internal::Implementation::SignOutTracker::WaitForSignOutToComplete(uint,ulong)

- ea: `0x1800bfbc0`
- end: `0x1800bfcee`
- name: `?WaitForSignOutToComplete@SignOutTracker@Implementation@Internal@System@Windows@@QEAAJIK@Z`
- size: `302`
- prototype: `__int64 __fastcall(Windows::System::Internal::Implementation::SignOutTracker *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009a4ec`
- `0x1800a1b2c`

## callees

- `0x1800088e8`
- `0x1800179c0`
- `0x18003e290`
- `0x180071434`
- `0x1800bf6e0`
- `0x1800bfbc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800bfc9f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800bfc9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bfbeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bfbeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfcac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfcac`

## string_xrefs

- `0x1800bfc52`: `onecore\ds\security\umstartup\usermgr\lib\signouttracker.cpp`
- `0x1800bfc89`: `onecore\ds\security\umstartup\usermgr\lib\signouttracker.cpp`

## pseudocode

```c

```
