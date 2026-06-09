# CDVRReadManager::Read(IMediaSample2 * *,unsigned __int64 *,ulong *,ushort *)

- ea: `0x1800425a0`
- end: `0x180042793`
- name: `?Read@CDVRReadManager@@QEAAJPEAPEAUIMediaSample2@@PEA_KPEAKPEAG@Z`
- size: `499`
- prototype: `__int64 __usercall@<rax>(CDVRReadManager *__hidden this@<rcx>, struct IMediaSample2 **@<rdx>, unsigned __int64 *@<r8>, unsigned int *@<r9>, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180041bd0`
- `0x18004279c`

## callees

- `0x180001c00`
- `0x1800089b8`
- `0x18000ac84`
- `0x18003ed04`
- `0x18003f364`
- `0x1800425a0`
- `0x1800446cc`
- `0x180044e08`
- `0x18004ea54`
- `0x180061b70`
- `0x1800a2c38`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180042721`
- `KERNEL32!WaitForSingleObject` at `0x180042721`
- `WINMM!timeGetTime` at `0x1800425f1`
- `WINMM!timeGetTime` at `0x180042633`
- `WINMM!timeGetTime` at `0x1800425f1`
- `WINMM!timeGetTime` at `0x180042633`

## pseudocode

```c

```
