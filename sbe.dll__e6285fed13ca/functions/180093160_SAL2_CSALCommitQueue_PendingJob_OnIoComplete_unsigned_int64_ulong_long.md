# SAL2::CSALCommitQueue::PendingJob::OnIoComplete(unsigned __int64,ulong,long)

- ea: `0x180093160`
- end: `0x180093264`
- name: `?OnIoComplete@PendingJob@CSALCommitQueue@SAL2@@EEAAX_KKJ@Z`
- size: `260`
- prototype: `void __fastcall(SAL2::CSALCommitQueue::PendingJob *__hidden this, unsigned __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180008330`
- `0x180062710`
- `0x180086014`
- `0x180093160`
- `0x1800935b0`
- `0x1800937b8`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180093227`
- `KERNEL32!LeaveCriticalSection` at `0x180093227`
- `KERNEL32!EnterCriticalSection` at `0x1800931c9`
- `KERNEL32!EnterCriticalSection` at `0x1800931c9`

## string_xrefs

- `0x18009320d`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`

## pseudocode

```c

```
