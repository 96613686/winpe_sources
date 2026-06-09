# RetrieveSegmentedBlob(_DEVICE_OBJECT *,_FILE_OBJECT *,char * *,char * *,_HIDP_CAPS *,_HIDP_PREPARSED_DATA *,_HIDP_VALUE_CAPS)

- ea: `0x1400b4abc`
- end: `0x1400b4ffb`
- name: `?RetrieveSegmentedBlob@@YAJPEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@PEAPEAD2PEAU_HIDP_CAPS@@PEAU_HIDP_PREPARSED_DATA@@U_HIDP_VALUE_CAPS@@@Z`
- size: `1343`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, struct _FILE_OBJECT *@<rdx>, char **@<r8>, char **@<r9>, struct _HIDP_CAPS *, struct _HIDP_PREPARSED_DATA *, struct _HIDP_VALUE_CAPS *__struct_ptr)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400b47e8`

## callees

- `0x140049ec0`
- `0x1400a5ba0`
- `0x1400b4abc`
- `0x1400b642c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400b4b49`
- `ntoskrnl!KeInitializeEvent` at `0x1400b4cc8`
- `ntoskrnl!KeInitializeEvent` at `0x1400b4b49`
- `ntoskrnl!KeInitializeEvent` at `0x1400b4cc8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b4ca0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b4de4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b4ca0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b4de4`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400b4bc1`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400b4d07`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400b4bc1`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400b4d07`
- `ntoskrnl!IofCallDriver` at `0x1400b4beb`
- `ntoskrnl!IofCallDriver` at `0x1400b4d2d`
- `ntoskrnl!IofCallDriver` at `0x1400b4beb`
- `ntoskrnl!IofCallDriver` at `0x1400b4d2d`
- `WIN32K!W32GetUserSessionState` at `0x1400b4c43`
- `WIN32K!W32GetUserSessionState` at `0x1400b4d87`
- `WIN32K!W32GetUserSessionState` at `0x1400b4e9a`
- `WIN32K!W32GetUserSessionState` at `0x1400b4f30`
- `WIN32K!W32GetUserSessionState` at `0x1400b4f92`
- `WIN32K!W32GetUserSessionState` at `0x1400b4c43`
- `WIN32K!W32GetUserSessionState` at `0x1400b4d87`
- `WIN32K!W32GetUserSessionState` at `0x1400b4e9a`
- `WIN32K!W32GetUserSessionState` at `0x1400b4f30`
- `WIN32K!W32GetUserSessionState` at `0x1400b4f92`
- `HIDPARSE!HidP_SetUsageValue` at `0x1400b4b84`
- `HIDPARSE!HidP_SetUsageValue` at `0x1400b4b84`
- `HIDPARSE!HidP_GetUsageValueArray` at `0x1400b4e32`
- `HIDPARSE!HidP_GetUsageValueArray` at `0x1400b4e32`

## pseudocode

```c

```
