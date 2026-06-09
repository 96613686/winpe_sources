# DrvEnumDisplayDevices

- ea: `0x1400fd3b0`
- end: `0x1400fde48`
- name: `DrvEnumDisplayDevices`
- size: `2712`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, int, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config`

## callers

- `0x1400fd2f0`

## callees

- `0x14000dc4c`
- `0x1400305c0`
- `0x140032170`
- `0x1400492a4`
- `0x14004a0d0`
- `0x1400aa980`
- `0x1400ab30c`
- `0x1400abd4c`
- `0x1400abe40`
- `0x1400ac9c0`
- `0x1400eaa54`
- `0x1400fd3b0`
- `0x1400fde50`
- `0x1400fde8c`
- `0x1400fdea0`
- `0x1400fdf50`
- `0x14014e92c`
- `0x14015e1cc`
- `0x14015f35c`
- `0x14017d5a0`
- `0x1401f6e98`
- `0x140238160`
- `0x140238240`
- `0x1402382c0`
- `0x1402bb054`
- `0x1402bb1a0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400fdbdc`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400fdbdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fd906`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fdc1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fd906`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fdc1f`
- `ntoskrnl!wcscpy_s` at `0x1400fda3a`
- `ntoskrnl!wcscpy_s` at `0x1400fda3a`
- `ntoskrnl!wcsncpy_s` at `0x1400fd801`
- `ntoskrnl!wcsncpy_s` at `0x1400fd9d8`
- `ntoskrnl!wcsncpy_s` at `0x1400fda7a`
- `ntoskrnl!wcsncpy_s` at `0x1400fdab8`
- `ntoskrnl!wcsncpy_s` at `0x1400fdd92`
- `ntoskrnl!wcsncpy_s` at `0x1400fd801`
- `ntoskrnl!wcsncpy_s` at `0x1400fd9d8`
- `ntoskrnl!wcsncpy_s` at `0x1400fda7a`
- `ntoskrnl!wcsncpy_s` at `0x1400fdab8`
- `ntoskrnl!wcsncpy_s` at `0x1400fdd92`
- `ntoskrnl!swprintf_s` at `0x1400fdd5f`
- `ntoskrnl!swprintf_s` at `0x1400fdd5f`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400fd656`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400fd9ae`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400fda13`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400fdb91`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400fd656`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400fd9ae`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400fda13`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400fdb91`
- `ntoskrnl!ObfDereferenceObject` at `0x1400fdc7f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400fdd20`
- `watchdog!WdLogSingleEntry4` at `0x1400fd42f`
- `watchdog!WdLogSingleEntry4` at `0x1400fd42f`
- `watchdog!WdLogSingleEntry0` at `0x1400fd473`
- `watchdog!WdLogSingleEntry0` at `0x1400fdca1`
- `watchdog!WdLogSingleEntry0` at `0x1400fdcf3`
- `watchdog!WdLogSingleEntry0` at `0x1400fd473`
- `watchdog!WdLogSingleEntry0` at `0x1400fdca1`
- `watchdog!WdLogSingleEntry0` at `0x1400fdcf3`
- `watchdog!WdLogSingleEntry1` at `0x1400fd6f2`
- `watchdog!WdLogSingleEntry1` at `0x1400fdddb`
- `watchdog!WdLogSingleEntry1` at `0x1400fd6f2`
- `watchdog!WdLogSingleEntry1` at `0x1400fdddb`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400fd893`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400fd893`
- `WIN32K!W32GetSessionState` at `0x1400fd445`
- `WIN32K!W32GetSessionState` at `0x1400fdba2`
- `WIN32K!W32GetSessionState` at `0x1400fd445`
- `WIN32K!W32GetSessionState` at `0x1400fdba2`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400fdbcc`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400fdbcc`
- `WIN32K!W32GetUserSessionState` at `0x1400fd4fa`
- `WIN32K!W32GetUserSessionState` at `0x1400fd4fa`

## string_xrefs

- `0x1400fda27`: `\Registry\Machine\System\CurrentControlSet`

## pseudocode

```c

```
