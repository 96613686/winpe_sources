# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::Shutdown(void)

- ea: `0x180027c10`
- end: `0x180027c78`
- name: `?Shutdown@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAAXXZ`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180027260`
- `0x180028260`

## callees

- `0x180027720`
- `0x180027c10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180027c38`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027c38`
- `KERNEL32!EnterCriticalSection` at `0x180027c19`
- `KERNEL32!EnterCriticalSection` at `0x180027c19`
- `KERNEL32!LeaveCriticalSection` at `0x180027c6c`
- `KERNEL32!CloseHandle` at `0x180027c53`
- `KERNEL32!CloseHandle` at `0x180027c53`

## pseudocode

```c

```
