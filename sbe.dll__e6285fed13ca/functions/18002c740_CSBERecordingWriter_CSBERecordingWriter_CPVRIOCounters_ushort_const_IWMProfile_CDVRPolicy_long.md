# CSBERecordingWriter::CSBERecordingWriter(CPVRIOCounters *,ushort const *,IWMProfile *,CDVRPolicy *,long *)

- ea: `0x18002c740`
- end: `0x18002c9d5`
- name: `??0CSBERecordingWriter@@QEAA@PEAVCPVRIOCounters@@PEBGPEAUIWMProfile@@PEAVCDVRPolicy@@PEAJ@Z`
- size: `661`
- prototype: `CSBERecordingWriter *__fastcall(CSBERecordingWriter *__hidden this, struct CPVRIOCounters *, LPCWSTR lpFileName, struct IWMProfile *, struct CDVRPolicy *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180027ddc`

## callees

- `0x180001c00`
- `0x180009ad4`
- `0x18002bf70`
- `0x18002c740`
- `0x18002d050`
- `0x18005059c`
- `0x180057150`
- `0x180070608`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18002c922`
- `KERNEL32!GetSystemInfo` at `0x18002c922`
- `KERNEL32!InitializeCriticalSection` at `0x18002c7b2`
- `KERNEL32!InitializeCriticalSection` at `0x18002c7b2`

## string_xrefs

- `0x18002c8b3`: `AsyncIoWriterBufferPoolCount`

## pseudocode

```c

```
