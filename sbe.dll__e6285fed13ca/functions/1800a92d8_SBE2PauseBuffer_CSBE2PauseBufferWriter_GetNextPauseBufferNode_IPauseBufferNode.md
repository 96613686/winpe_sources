# SBE2PauseBuffer::CSBE2PauseBufferWriter::GetNextPauseBufferNode(IPauseBufferNode * *)

- ea: `0x1800a92d8`
- end: `0x1800a936a`
- name: `?GetNextPauseBufferNode@CSBE2PauseBufferWriter@SBE2PauseBuffer@@AEAAJPEAPEAUIPauseBufferNode@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(SBE2PauseBuffer::CSBE2PauseBufferWriter *__hidden this, struct IPauseBufferNode **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a8ac8`
- `0x1800a8e30`

## callees

- `0x1800612b4`
- `0x1800627f0`
- `0x1800a8f08`
- `0x1800a92d8`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800a9358`
- `KERNEL32!SetEvent` at `0x1800a9358`
- `KERNEL32!LeaveCriticalSection` at `0x1800a931a`
- `KERNEL32!LeaveCriticalSection` at `0x1800a931a`
- `KERNEL32!EnterCriticalSection` at `0x1800a92f4`
- `KERNEL32!EnterCriticalSection` at `0x1800a92f4`

## string_xrefs

- `0x1800a9343`: `multimedia\dshow\filters\sbe\pausebuffer\pbwriter.cpp`

## pseudocode

```c

```
