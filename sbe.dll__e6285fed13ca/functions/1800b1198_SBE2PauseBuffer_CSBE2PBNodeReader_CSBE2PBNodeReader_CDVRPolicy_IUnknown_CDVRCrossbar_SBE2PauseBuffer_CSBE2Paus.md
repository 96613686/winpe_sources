# SBE2PauseBuffer::CSBE2PBNodeReader::CSBE2PBNodeReader(CDVRPolicy *,IUnknown *,CDVRCrossbar *,SBE2PauseBuffer::CSBE2PauseBufferReader *,SBE2PauseBuffer::CNodeCtx *,void (*)(void *,ulong,__int64,__int64),void *,long *)

- ea: `0x1800b1198`
- end: `0x1800b1530`
- name: `??0CSBE2PBNodeReader@SBE2PauseBuffer@@IEAA@PEAVCDVRPolicy@@PEAUIUnknown@@PEAVCDVRCrossbar@@PEAVCSBE2PauseBufferReader@1@PEAVCNodeCtx@1@P6AXPEAXK_J6@Z5PEAJ@Z`
- size: `920`
- prototype: `__int64 __usercall@<rax>(SBE2PauseBuffer::CSBE2PBNodeReader *__hidden this@<rcx>, struct CDVRPolicy *@<rdx>, struct IUnknown *@<r8>, struct CDVRCrossbar *@<r9>, struct SBE2PauseBuffer::CSBE2PauseBufferReader *, struct SBE2PauseBuffer::CNodeCtx *, void (*)(void *, unsigned int, __int64, __int64), void *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800b1920`

## callees

- `0x1800017a0`
- `0x18002573c`
- `0x180048248`
- `0x180057140`
- `0x18006201c`
- `0x1800ade20`
- `0x1800b0504`
- `0x1800b1198`
- `0x1800b2070`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800b11f5`
- `KERNEL32!InitializeCriticalSection` at `0x1800b12a9`
- `KERNEL32!InitializeCriticalSection` at `0x1800b11f5`
- `KERNEL32!InitializeCriticalSection` at `0x1800b12a9`

## string_xrefs

- `0x1800b147e`: `ERROR: %s(%u); pbn Cv2ThunkReader::CreateInstance () %s  : error is %08xh`
- `0x1800b13f3`: `CSBE2PBNodeReader::CSBE2PBNodeReader [%I64d ms, first: %I64d ms, last: %I64d ms, %I64d ms) opening ("%s")`

## pseudocode

```c

```
