# VhdmpiCtCreateEnableTrackingRequest(_VHD_HANDLE_CONTEXT *,_STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST *,_STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST * *)

- ea: `0x1400a41d0`
- end: `0x1400a4428`
- name: `?VhdmpiCtCreateEnableTrackingRequest@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST@@PEAPEAU2@@Z`
- size: `600`
- prototype: `__int64 __fastcall(struct _VHD_HANDLE_CONTEXT *, struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST *, struct _STORAGE_ENABLE_TRACKING_VIRTUAL_DISK_V2_REQUEST **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400295e4`

## callees

- `0x140020874`
- `0x140023560`
- `0x140035e94`
- `0x14005da00`
- `0x1400a41d0`
- `0x1400a4430`
- `0x1400c7d8c`
- `0x1400ebd40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400a43c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a43f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a43c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a43f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400a4282`
- `ntoskrnl!ExAllocatePool2` at `0x1400a4346`
- `ntoskrnl!ExAllocatePool2` at `0x1400a4282`
- `ntoskrnl!ExAllocatePool2` at `0x1400a4346`

## string_xrefs

- `0x1400a4315`: `VhdmpiCtCreateEnableTrackingRequest`
- `0x1400a430e`: `VhdmpiCtCreateEnableTrackingRequest: VhdSet LogFile not returned. Context = %p RequiredLength = %d`

## pseudocode

```c

```
