# SAL2::CSALCommitQueue::CheckPoint(SAL2::CSALCommitQueueClient *,SAL2::CSALPageList *)

- ea: `0x18009169c`
- end: `0x1800918cd`
- name: `?CheckPoint@CSALCommitQueue@SAL2@@QEAAJPEAVCSALCommitQueueClient@2@PEAVCSALPageList@2@@Z`
- size: `561`
- prototype: `__int64 __fastcall(SAL2::CSALCommitQueue *__hidden this, struct SAL2::CSALCommitQueueClient *, struct SAL2::CSALPageList *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180095dd0`

## callees

- `0x180008330`
- `0x180062710`
- `0x1800627f0`
- `0x180086014`
- `0x18009169c`
- `0x180092370`
- `0x180093528`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18009187f`
- `KERNEL32!LeaveCriticalSection` at `0x18009187f`
- `KERNEL32!EnterCriticalSection` at `0x1800916f6`
- `KERNEL32!EnterCriticalSection` at `0x1800916f6`

## string_xrefs

- `0x18009170e`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`
- `0x1800917e3`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`
- `0x180091862`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`

## pseudocode

```c

```
