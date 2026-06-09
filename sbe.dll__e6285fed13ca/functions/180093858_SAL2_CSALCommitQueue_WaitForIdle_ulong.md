# SAL2::CSALCommitQueue::WaitForIdle(ulong)

- ea: `0x180093858`
- end: `0x180093a9a`
- name: `?WaitForIdle@CSALCommitQueue@SAL2@@QEAAKK@Z`
- size: `578`
- prototype: `unsigned int __fastcall(SAL2::CSALCommitQueue *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180080f9c`

## callees

- `0x180001c00`
- `0x180008330`
- `0x1800622a0`
- `0x180062710`
- `0x180086014`
- `0x1800913d0`
- `0x180091ed8`
- `0x180093858`
- `0x180093aa0`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800939f7`
- `KERNEL32!WaitForSingleObject` at `0x1800939f7`
- `KERNEL32!ResetEvent` at `0x18009397d`
- `KERNEL32!ResetEvent` at `0x18009397d`
- `KERNEL32!LeaveCriticalSection` at `0x1800939b9`
- `KERNEL32!LeaveCriticalSection` at `0x180093a2e`
- `KERNEL32!LeaveCriticalSection` at `0x1800939b9`
- `KERNEL32!LeaveCriticalSection` at `0x180093a2e`
- `KERNEL32!EnterCriticalSection` at `0x180093941`
- `KERNEL32!EnterCriticalSection` at `0x180093941`

## string_xrefs

- `0x18009399f`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`
- `0x180093a14`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`

## pseudocode

```c

```
