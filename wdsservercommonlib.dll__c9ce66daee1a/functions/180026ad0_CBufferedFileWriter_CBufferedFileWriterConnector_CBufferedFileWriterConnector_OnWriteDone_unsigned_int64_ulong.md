# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::Shutdown(void)

- ea: `0x180026ad0`
- end: `0x180026b31`
- name: `?Shutdown@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAAXXZ`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180026140`
- `0x180027120`

## callees

- `0x180026600`
- `0x180026ad0`
- `0x18002e468`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180026ad9`
- `KERNEL32!EnterCriticalSection` at `0x180026ad9`
- `KERNEL32!LeaveCriticalSection` at `0x180026b25`
- `KERNEL32!CloseHandle` at `0x180026b0c`
- `KERNEL32!CloseHandle` at `0x180026b0c`

## pseudocode

```c

```
