# SAL2::CSALCommitQueue::NonLogAsyncCommit(SAL2::CSALCommitQueueClient *,SAL2::CSALPageList *)

- ea: `0x180092e24`
- end: `0x18009315a`
- name: `?NonLogAsyncCommit@CSALCommitQueue@SAL2@@QEAAJPEAVCSALCommitQueueClient@2@PEAVCSALPageList@2@@Z`
- size: `822`
- prototype: `int(SAL2::CSALCommitQueue *__hidden this, struct SAL2::CSALCommitQueueClient *, struct SAL2::CSALPageList *)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18008f740`
- `0x180095dd0`
- `0x180096efc`

## callees

- `0x1800017a0`
- `0x180008330`
- `0x180062710`
- `0x1800627f0`
- `0x180086014`
- `0x180090f8c`
- `0x180091b14`
- `0x180091dc0`
- `0x180092e24`
- `0x180093528`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18009310c`
- `KERNEL32!LeaveCriticalSection` at `0x18009310c`
- `KERNEL32!EnterCriticalSection` at `0x180092e87`
- `KERNEL32!EnterCriticalSection` at `0x180092e87`

## string_xrefs

- `0x180092e9c`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`
- `0x1800930c7`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`
- `0x1800930f3`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`

## pseudocode

```c

```
