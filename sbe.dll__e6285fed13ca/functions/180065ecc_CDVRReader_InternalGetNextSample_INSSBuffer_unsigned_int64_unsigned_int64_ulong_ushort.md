# CDVRReader::InternalGetNextSample(INSSBuffer * *,unsigned __int64 *,unsigned __int64 *,ulong *,ushort *)

- ea: `0x180065ecc`
- end: `0x180066649`
- name: `?InternalGetNextSample@CDVRReader@@IEAAJPEAPEAUINSSBuffer@@PEA_K1PEAKPEAG@Z`
- size: `1917`
- prototype: `__int64 __usercall@<rax>(CDVRReader *__hidden this@<rcx>, struct INSSBuffer **@<rdx>, unsigned __int64 *@<r8>, unsigned __int64 *@<r9>, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180065900`

## callees

- `0x180001c00`
- `0x18006497c`
- `0x180065380`
- `0x180065ecc`
- `0x180066664`
- `0x180067b1c`
- `0x180067bb8`
- `0x180074500`
- `0x180074668`
- `0x1800747f8`
- `0x180074aa0`
- `0x180074ec4`
- `0x180076948`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180065fe5`
- `KERNEL32!WaitForSingleObject` at `0x180065fe5`
- `KERNEL32!LeaveCriticalSection` at `0x18006661e`
- `KERNEL32!LeaveCriticalSection` at `0x1800b3a1f`
- `KERNEL32!LeaveCriticalSection` at `0x18006661e`
- `KERNEL32!LeaveCriticalSection` at `0x1800b3a1f`
- `KERNEL32!EnterCriticalSection` at `0x180065f5e`
- `KERNEL32!EnterCriticalSection` at `0x180065f5e`
- `KERNEL32!GetLastError` at `0x180066595`
- `KERNEL32!GetLastError` at `0x180066595`
- `KERNEL32!Sleep` at `0x180066411`
- `KERNEL32!Sleep` at `0x180066411`

## pseudocode

```c

```
