# CXxxJobImpl::SetResultCodeIfHigher(tagOperationResultCode,long,int)

- ea: `0x18007f6a0`
- end: `0x18007f7a1`
- name: `?SetResultCodeIfHigher@CXxxJobImpl@@IEAAXW4tagOperationResultCode@@JH@Z`
- size: `257`
- prototype: `void(CXxxJobImpl *__hidden this, enum tagOperationResultCode, int, int)`
- caller_count: `17`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000aaf0`
- `0x18000ab20`
- `0x18000b66c`
- `0x1800162f0`
- `0x18001af30`
- `0x18001d254`
- `0x18001f420`
- `0x180025550`
- `0x180032070`
- `0x1800320b0`
- `0x180032294`
- `0x180033aac`
- `0x18003f920`
- `0x18007f52c`
- `0x18007fbb0`
- `0x1800804c0`
- `0x1800808f0`

## callees

- `0x18007f150`
- `0x18007f6a0`
- `0x180090bc8`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f787`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f6d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f6d5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007f729`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007f729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f733`

## string_xrefs

- `0x18007f74c`: `completion event signalled. ResultCode = %ws; HR = 0x%08lX.`

## pseudocode

```c

```
