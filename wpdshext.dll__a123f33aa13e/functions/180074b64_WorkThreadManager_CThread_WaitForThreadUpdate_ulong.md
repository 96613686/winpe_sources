# WorkThreadManager::CThread::WaitForThreadUpdate(ulong)

- ea: `0x180074b64`
- end: `0x180074c5b`
- name: `?WaitForThreadUpdate@CThread@WorkThreadManager@@AEAAJK@Z`
- size: `247`
- prototype: `int(WorkThreadManager::CThread *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18002968c`
- `0x18002b504`

## callees

- `0x1800362d4`
- `0x180036c70`
- `0x180074b64`

## import_xrefs

- `USER32!MsgWaitForMultipleObjectsEx` at `0x180074ba9`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180074ba9`
- `ole32!CoWaitForMultipleHandles` at `0x180074c36`
- `ole32!CoWaitForMultipleHandles` at `0x180074c36`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x180074be1`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x180074be1`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x180074beb`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x180074beb`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x180074c09`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x180074c09`

## pseudocode

```c

```
