# DrvEnumDisplayDevices

- ea: `0x14000e5e0`
- end: `0x14000f078`
- name: `DrvEnumDisplayDevices`
- size: `2712`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, int, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config`

## callers

- `0x14000e520`

## callees

- `0x14000d76c`
- `0x14000e5e0`
- `0x14000f0e8`
- `0x14000f124`
- `0x14000f138`
- `0x14000f290`
- `0x140019668`
- `0x140019d50`
- `0x14006a6d0`
- `0x14007ab04`
- `0x14007b930`
- `0x1400d4290`
- `0x1400d4c1c`
- `0x1400d565c`
- `0x1400d5750`
- `0x1400d62d0`
- `0x1400e5154`
- `0x140150adc`
- `0x1401607ac`
- `0x1401618b8`
- `0x1401f76f8`
- `0x1402388e0`
- `0x1402389c0`
- `0x140238a40`
- `0x1402bb054`
- `0x1402bb1a0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14000ee0c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000ee0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee4f`
- `ntoskrnl!wcscpy_s` at `0x14000ec6a`
- `ntoskrnl!wcscpy_s` at `0x14000ec6a`
- `ntoskrnl!wcsncpy_s` at `0x14000ea31`
- `ntoskrnl!wcsncpy_s` at `0x14000ec08`
- `ntoskrnl!wcsncpy_s` at `0x14000ecaa`
- `ntoskrnl!wcsncpy_s` at `0x14000ece8`
- `ntoskrnl!wcsncpy_s` at `0x14000efc2`
- `ntoskrnl!wcsncpy_s` at `0x14000ea31`
- `ntoskrnl!wcsncpy_s` at `0x14000ec08`
- `ntoskrnl!wcsncpy_s` at `0x14000ecaa`
- `ntoskrnl!wcsncpy_s` at `0x14000ece8`
- `ntoskrnl!wcsncpy_s` at `0x14000efc2`
- `ntoskrnl!swprintf_s` at `0x14000ef8f`
- `ntoskrnl!swprintf_s` at `0x14000ef8f`
- `ntoskrnl!IoGetDeviceProperty` at `0x14000e886`
- `ntoskrnl!IoGetDeviceProperty` at `0x14000ebde`
- `ntoskrnl!IoGetDeviceProperty` at `0x14000ec43`
- `ntoskrnl!IoGetDeviceProperty` at `0x14000edc1`
- `ntoskrnl!IoGetDeviceProperty` at `0x14000e886`
- `ntoskrnl!IoGetDeviceProperty` at `0x14000ebde`
- `ntoskrnl!IoGetDeviceProperty` at `0x14000ec43`
- `ntoskrnl!IoGetDeviceProperty` at `0x14000edc1`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eeaf`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ef50`
- `watchdog!WdLogSingleEntry4` at `0x14000e65f`
- `watchdog!WdLogSingleEntry4` at `0x14000e65f`
- `watchdog!WdLogSingleEntry0` at `0x14000e6a3`
- `watchdog!WdLogSingleEntry0` at `0x14000eed1`
- `watchdog!WdLogSingleEntry0` at `0x14000ef23`
- `watchdog!WdLogSingleEntry0` at `0x14000e6a3`
- `watchdog!WdLogSingleEntry0` at `0x14000eed1`
- `watchdog!WdLogSingleEntry0` at `0x14000ef23`
- `watchdog!WdLogSingleEntry1` at `0x14000e922`
- `watchdog!WdLogSingleEntry1` at `0x14000f00b`
- `watchdog!WdLogSingleEntry1` at `0x14000e922`
- `watchdog!WdLogSingleEntry1` at `0x14000f00b`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14000eac3`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14000eac3`
- `WIN32K!W32GetSessionState` at `0x14000e675`
- `WIN32K!W32GetSessionState` at `0x14000edd2`
- `WIN32K!W32GetSessionState` at `0x14000e675`
- `WIN32K!W32GetSessionState` at `0x14000edd2`
- `WIN32K!W32GetUserGdiSessionState` at `0x14000edfc`
- `WIN32K!W32GetUserGdiSessionState` at `0x14000edfc`
- `WIN32K!W32GetUserSessionState` at `0x14000e72a`
- `WIN32K!W32GetUserSessionState` at `0x14000e72a`

## string_xrefs

- `0x14000ec57`: `\Registry\Machine\System\CurrentControlSet`

## pseudocode

```c

```
