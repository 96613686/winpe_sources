# CBlbVhdHelper::CompactVHD(CBlbImpersonationHelper *,ushort const *,uchar (*)(void *,__int64,__int64),void *)

- ea: `0x140108018`
- end: `0x14010854e`
- name: `?CompactVHD@CBlbVhdHelper@@SAJPEAVCBlbImpersonationHelper@@PEBGP6AEPEAX_J3@Z2@Z`
- size: `1334`
- prototype: `__int64 __fastcall(struct CBlbImpersonationHelper *this, PCWSTR Path, unsigned __int8 (*)(void *, __int64, __int64), void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140010efc`
- `0x14002e4e0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x14001d330`
- `0x1400f007c`
- `0x1400f07dc`
- `0x140108018`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CancelIoEx` at `0x140108355`
- `KERNEL32!CancelIoEx` at `0x140108355`
- `KERNEL32!Sleep` at `0x140108345`
- `KERNEL32!Sleep` at `0x140108345`
- `KERNEL32!CloseHandle` at `0x1401084c6`
- `KERNEL32!CloseHandle` at `0x1401084de`
- `KERNEL32!CloseHandle` at `0x1401084c6`
- `KERNEL32!CloseHandle` at `0x1401084de`
- `KERNEL32!CreateEventW` at `0x14010828f`
- `KERNEL32!CreateEventW` at `0x14010828f`
- `KERNEL32!GetLastError` at `0x1401081e4`
- `KERNEL32!GetLastError` at `0x1401081e4`
- `VirtDisk!GetVirtualDiskOperationProgress` at `0x140108314`
- `VirtDisk!GetVirtualDiskOperationProgress` at `0x140108314`
- `VirtDisk!AttachVirtualDisk` at `0x14010823e`
- `VirtDisk!AttachVirtualDisk` at `0x14010823e`
- `VirtDisk!OpenVirtualDisk` at `0x1401081c7`
- `VirtDisk!OpenVirtualDisk` at `0x1401081c7`
- `VirtDisk!CompactVirtualDisk` at `0x1401082ea`
- `VirtDisk!CompactVirtualDisk` at `0x1401082ea`

## string_xrefs

- `0x14010809a`: `wszVHDFilePath && *wszVHDFilePath`

## pseudocode

```c

```
