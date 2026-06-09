# CExec::ConnectStdDevicePipe(void *,bool,bool)

- ea: `0x1400fe710`
- end: `0x1400fe883`
- name: `?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z`
- size: `371`
- prototype: `__int64 __fastcall(LPHANDLE lpTargetHandle, HANDLE hSourceHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140080ed8`

## callees

- `0x140024f6c`
- `0x140080180`
- `0x1400fe710`
- `0x1401332f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400fe760`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400fe76f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400fe760`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400fe76f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400fe79f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400fe79f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400fe823`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400fe823`

## string_xrefs

- `0x1400fe7bb`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400fe850`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c

```
