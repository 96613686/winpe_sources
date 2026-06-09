# CDVRRecorderWriter::CDVRRecorderWriter(CPVRIOCounters *,ushort const *,IWMProfile *,ulong,ulong,int,ulong,ulong,ulong,ulong,HKEY__ *,long *)

- ea: `0x180068e48`
- end: `0x180068fc7`
- name: `??0CDVRRecorderWriter@@QEAA@PEAVCPVRIOCounters@@PEBGPEAUIWMProfile@@KKHKKKKPEAUHKEY__@@PEAJ@Z`
- size: `383`
- prototype: `CDVRRecorderWriter *__fastcall(CDVRRecorderWriter *__hidden this, struct CPVRIOCounters *, LPCWSTR lpFileName, struct IWMProfile *, unsigned int, unsigned int, int, unsigned int, unsigned int, unsigned int, unsigned int, HKEY, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180070608`

## callees

- `0x1800017a0`
- `0x180068e48`
- `0x18006d028`
- `0x18006d3a8`
- `0x180077638`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180068eec`
- `KERNEL32!InitializeCriticalSection` at `0x180068eec`
- `KERNEL32!GetLastError` at `0x180068f04`
- `KERNEL32!GetLastError` at `0x180068f04`
- `KERNEL32!GetFileAttributesW` at `0x180068ef5`
- `KERNEL32!GetFileAttributesW` at `0x180068ef5`

## pseudocode

```c

```
