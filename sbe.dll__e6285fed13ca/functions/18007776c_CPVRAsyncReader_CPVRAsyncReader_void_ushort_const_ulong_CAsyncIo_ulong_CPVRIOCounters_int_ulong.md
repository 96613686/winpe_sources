# CPVRAsyncReader::CPVRAsyncReader(void *,ushort const *,ulong,CAsyncIo *,ulong,CPVRIOCounters *,int,ulong *)

- ea: `0x18007776c`
- end: `0x180077a44`
- name: `??0CPVRAsyncReader@@QEAA@PEAXPEBGKPEAVCAsyncIo@@KPEAVCPVRIOCounters@@HPEAK@Z`
- size: `728`
- prototype: `CPVRAsyncReader *(CPVRAsyncReader *__hidden this, void *, const unsigned __int16 *, unsigned int, struct CAsyncIo *, unsigned int, struct CPVRIOCounters *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007a580`

## callees

- `0x180001c00`
- `0x180064dd8`
- `0x18007759c`
- `0x18007776c`
- `0x180078dac`
- `0x180079dcc`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!VirtualAlloc` at `0x180077950`
- `KERNEL32!VirtualAlloc` at `0x180077950`
- `KERNEL32!DuplicateHandle` at `0x18007799f`
- `KERNEL32!DuplicateHandle` at `0x18007799f`
- `KERNEL32!InitializeCriticalSection` at `0x1800777e3`
- `KERNEL32!InitializeCriticalSection` at `0x1800778a7`
- `KERNEL32!InitializeCriticalSection` at `0x1800777e3`
- `KERNEL32!InitializeCriticalSection` at `0x1800778a7`
- `KERNEL32!GetLastError` at `0x180077a10`
- `KERNEL32!GetLastError` at `0x180077a10`
- `KERNEL32!GetCurrentProcess` at `0x180077974`
- `KERNEL32!GetCurrentProcess` at `0x18007797d`
- `KERNEL32!GetCurrentProcess` at `0x180077974`
- `KERNEL32!GetCurrentProcess` at `0x18007797d`
- `KERNEL32!GetFileInformationByHandle` at `0x1800779d7`
- `KERNEL32!GetFileInformationByHandle` at `0x1800779d7`

## pseudocode

```c

```
