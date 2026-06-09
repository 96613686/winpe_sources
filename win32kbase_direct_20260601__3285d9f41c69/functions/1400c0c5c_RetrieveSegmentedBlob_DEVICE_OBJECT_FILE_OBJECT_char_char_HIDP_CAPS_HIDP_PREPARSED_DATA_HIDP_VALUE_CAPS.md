# RetrieveSegmentedBlob(_DEVICE_OBJECT *,_FILE_OBJECT *,char * *,char * *,_HIDP_CAPS *,_HIDP_PREPARSED_DATA *,_HIDP_VALUE_CAPS)

- ea: `0x1400c0c5c`
- end: `0x1400c119b`
- name: `?RetrieveSegmentedBlob@@YAJPEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@PEAPEAD2PEAU_HIDP_CAPS@@PEAU_HIDP_PREPARSED_DATA@@U_HIDP_VALUE_CAPS@@@Z`
- size: `1343`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, struct _FILE_OBJECT *@<rdx>, char **@<r8>, char **@<r9>, struct _HIDP_CAPS *, struct _HIDP_PREPARSED_DATA *, struct _HIDP_VALUE_CAPS *__struct_ptr)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400c0988`

## callees

- `0x140072a90`
- `0x1400b1d40`
- `0x1400c0c5c`
- `0x1400c25cc`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400c0ce9`
- `ntoskrnl!KeInitializeEvent` at `0x1400c0e68`
- `ntoskrnl!KeInitializeEvent` at `0x1400c0ce9`
- `ntoskrnl!KeInitializeEvent` at `0x1400c0e68`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c0e40`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c0f84`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c0e40`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c0f84`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400c0d61`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400c0ea7`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400c0d61`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400c0ea7`
- `ntoskrnl!IofCallDriver` at `0x1400c0d8b`
- `ntoskrnl!IofCallDriver` at `0x1400c0ecd`
- `ntoskrnl!IofCallDriver` at `0x1400c0d8b`
- `ntoskrnl!IofCallDriver` at `0x1400c0ecd`
- `WIN32K!W32GetUserSessionState` at `0x1400c0de3`
- `WIN32K!W32GetUserSessionState` at `0x1400c0f27`
- `WIN32K!W32GetUserSessionState` at `0x1400c103a`
- `WIN32K!W32GetUserSessionState` at `0x1400c10d0`
- `WIN32K!W32GetUserSessionState` at `0x1400c1132`
- `WIN32K!W32GetUserSessionState` at `0x1400c0de3`
- `WIN32K!W32GetUserSessionState` at `0x1400c0f27`
- `WIN32K!W32GetUserSessionState` at `0x1400c103a`
- `WIN32K!W32GetUserSessionState` at `0x1400c10d0`
- `WIN32K!W32GetUserSessionState` at `0x1400c1132`
- `HIDPARSE!HidP_SetUsageValue` at `0x1400c0d24`
- `HIDPARSE!HidP_SetUsageValue` at `0x1400c0d24`
- `HIDPARSE!HidP_GetUsageValueArray` at `0x1400c0fd2`
- `HIDPARSE!HidP_GetUsageValueArray` at `0x1400c0fd2`

## pseudocode

```c

```
