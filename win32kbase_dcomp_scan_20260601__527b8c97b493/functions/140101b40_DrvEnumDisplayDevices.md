# DrvEnumDisplayDevices

- ea: `0x140101b40`
- end: `0x1401025d8`
- name: `DrvEnumDisplayDevices`
- size: `2712`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, int, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config`

## callers

- `0x140101a80`

## callees

- `0x140027340`
- `0x140028ef0`
- `0x140040394`
- `0x1400411c0`
- `0x14009202c`
- `0x1400c5250`
- `0x1400c5bdc`
- `0x1400c661c`
- `0x1400c6710`
- `0x1400c7290`
- `0x1400ed3d4`
- `0x140101b40`
- `0x1401025e0`
- `0x14010261c`
- `0x140102630`
- `0x1401026e0`
- `0x14014de7c`
- `0x14015d7dc`
- `0x14015e96c`
- `0x14017cb30`
- `0x1401f7658`
- `0x140238b10`
- `0x140238bf0`
- `0x140238c40`
- `0x1402bd054`
- `0x1402bd244`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14010236c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010236c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140102096`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401023af`
- `ntoskrnl!ExFreePoolWithTag` at `0x140102096`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401023af`
- `ntoskrnl!wcscpy_s` at `0x1401021ca`
- `ntoskrnl!wcscpy_s` at `0x1401021ca`
- `ntoskrnl!wcsncpy_s` at `0x140101f91`
- `ntoskrnl!wcsncpy_s` at `0x140102168`
- `ntoskrnl!wcsncpy_s` at `0x14010220a`
- `ntoskrnl!wcsncpy_s` at `0x140102248`
- `ntoskrnl!wcsncpy_s` at `0x140102522`
- `ntoskrnl!wcsncpy_s` at `0x140101f91`
- `ntoskrnl!wcsncpy_s` at `0x140102168`
- `ntoskrnl!wcsncpy_s` at `0x14010220a`
- `ntoskrnl!wcsncpy_s` at `0x140102248`
- `ntoskrnl!wcsncpy_s` at `0x140102522`
- `ntoskrnl!swprintf_s` at `0x1401024ef`
- `ntoskrnl!swprintf_s` at `0x1401024ef`
- `ntoskrnl!IoGetDeviceProperty` at `0x140101de6`
- `ntoskrnl!IoGetDeviceProperty` at `0x14010213e`
- `ntoskrnl!IoGetDeviceProperty` at `0x1401021a3`
- `ntoskrnl!IoGetDeviceProperty` at `0x140102321`
- `ntoskrnl!IoGetDeviceProperty` at `0x140101de6`
- `ntoskrnl!IoGetDeviceProperty` at `0x14010213e`
- `ntoskrnl!IoGetDeviceProperty` at `0x1401021a3`
- `ntoskrnl!IoGetDeviceProperty` at `0x140102321`
- `ntoskrnl!ObfDereferenceObject` at `0x14010240f`
- `ntoskrnl!ObfDereferenceObject` at `0x1401024b0`
- `watchdog!WdLogSingleEntry4` at `0x140101bbf`
- `watchdog!WdLogSingleEntry4` at `0x140101bbf`
- `watchdog!WdLogSingleEntry0` at `0x140101c03`
- `watchdog!WdLogSingleEntry0` at `0x140102431`
- `watchdog!WdLogSingleEntry0` at `0x140102483`
- `watchdog!WdLogSingleEntry0` at `0x140101c03`
- `watchdog!WdLogSingleEntry0` at `0x140102431`
- `watchdog!WdLogSingleEntry0` at `0x140102483`
- `watchdog!WdLogSingleEntry1` at `0x140101e82`
- `watchdog!WdLogSingleEntry1` at `0x14010256b`
- `watchdog!WdLogSingleEntry1` at `0x140101e82`
- `watchdog!WdLogSingleEntry1` at `0x14010256b`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140102023`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140102023`
- `WIN32K!W32GetSessionState` at `0x140101bd5`
- `WIN32K!W32GetSessionState` at `0x140102332`
- `WIN32K!W32GetSessionState` at `0x140101bd5`
- `WIN32K!W32GetSessionState` at `0x140102332`
- `WIN32K!W32GetUserGdiSessionState` at `0x14010235c`
- `WIN32K!W32GetUserGdiSessionState` at `0x14010235c`
- `WIN32K!W32GetUserSessionState` at `0x140101c8a`
- `WIN32K!W32GetUserSessionState` at `0x140101c8a`

## string_xrefs

- `0x1401021b7`: `\Registry\Machine\System\CurrentControlSet`

## pseudocode

```c

```
