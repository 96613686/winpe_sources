# HrUpdateFolderInfo(AddressBook *,_SBinary *,ulong,int,ushort *)

- ea: `0x180036c54`
- end: `0x180036e47`
- name: `?HrUpdateFolderInfo@@YAJPEAVAddressBook@@PEAU_SBinary@@KHPEAG@Z`
- size: `499`
- prototype: `__int64 __usercall@<rax>(struct AddressBook *@<rcx>, struct _SBinary *@<rdx>, unsigned int@<r8d>, int@<r9d>, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18003719c`

## callees

- `0x1800045e4`
- `0x180036b10`
- `0x180036c54`
- `0x180037230`
- `0x180093010`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180036d0c`
- `KERNEL32!lstrcmpiW` at `0x180036d0c`
- `KERNEL32!LocalAlloc` at `0x180036d6e`
- `KERNEL32!LocalAlloc` at `0x180036d6e`
- `KERNEL32!LocalFree` at `0x180036d3e`
- `KERNEL32!LocalFree` at `0x180036d3e`
- `KERNEL32!lstrcmpW` at `0x180036d22`
- `KERNEL32!lstrcmpW` at `0x180036d22`

## pseudocode

```c

```
