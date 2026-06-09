# WinSAT::StorageDevice::SetFileLocation(unsigned __int64,unsigned __int64 &,bool,void *,unsigned __int64 &)

- ea: `0x14006237c`
- end: `0x1400628e8`
- name: `?SetFileLocation@StorageDevice@WinSAT@@AEBA_N_KAEA_K_NPEAX1@Z`
- size: `1388`
- prototype: `bool __usercall@<al>(WinSAT::StorageDevice *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned __int64 *@<r8>, bool@<r9b>, void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x140061600`

## callees

- `0x140001abc`
- `0x140003164`
- `0x140003611`
- `0x140004348`
- `0x140005f10`
- `0x140016d04`
- `0x140017af0`
- `0x14004fce4`
- `0x14006046c`
- `0x1400605cc`
- `0x140060c14`
- `0x140060eb4`
- `0x14006106c`
- `0x140061ab4`
- `0x1400622d8`
- `0x14006237c`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1400626f9`
- `KERNEL32!DeviceIoControl` at `0x140062801`
- `KERNEL32!DeviceIoControl` at `0x1400626f9`
- `KERNEL32!DeviceIoControl` at `0x140062801`
- `KERNEL32!GetLastError` at `0x14006270f`
- `KERNEL32!GetLastError` at `0x14006270f`
- `KERNEL32!WaitForSingleObject` at `0x1400625f6`
- `KERNEL32!WaitForSingleObject` at `0x1400625f6`

## pseudocode

```c

```
