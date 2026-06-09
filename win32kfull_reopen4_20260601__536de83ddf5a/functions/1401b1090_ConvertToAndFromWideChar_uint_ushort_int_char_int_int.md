# ConvertToAndFromWideChar(uint,ushort *,int,char *,int,int)

- ea: `0x1401b1090`
- end: `0x1401b1510`
- name: `?ConvertToAndFromWideChar@@YAHIPEAGHPEADHH@Z`
- size: `1152`
- prototype: `int(unsigned int, unsigned __int16 *, int, char *, int, int)`
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1400bc768`
- `0x1400c1d20`
- `0x1401b08cc`
- `0x1401b0c30`
- `0x1401b0e84`
- `0x1401e5988`
- `0x14026bc4c`
- `0x14029bc80`

## callees

- `0x1401633a4`
- `0x1401b1090`
- `0x1401b1898`
- `0x14029a070`
- `0x140342fa0`
- `0x140343200`
- `0x140343500`

## import_xrefs

- `ntoskrnl!RtlGetDefaultCodePage` at `0x1401b10f5`
- `ntoskrnl!RtlGetDefaultCodePage` at `0x1401b10f5`
- `ntoskrnl!RtlUnicodeToCustomCPN` at `0x1401b129b`
- `ntoskrnl!RtlUnicodeToCustomCPN` at `0x1401b129b`
- `ntoskrnl!RtlCustomCPToUnicodeN` at `0x1401b11a7`
- `ntoskrnl!RtlCustomCPToUnicodeN` at `0x1401b11a7`
- `ntoskrnl!RtlInitCodePageTable` at `0x1401b1446`
- `ntoskrnl!RtlInitCodePageTable` at `0x1401b1446`
- `ntoskrnl!ZwReadFile` at `0x1401b1404`
- `ntoskrnl!ZwReadFile` at `0x1401b1404`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b1168`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b11f9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b14e7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b1168`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b11f9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b14e7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b1132`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b11dd`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b148c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b1132`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b11dd`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b148c`
- `ntoskrnl!ZwQueryInformationFile` at `0x1401b13a7`
- `ntoskrnl!ZwQueryInformationFile` at `0x1401b13a7`
- `ntoskrnl!RtlUnicodeToMultiByteN` at `0x1401b12bd`
- `ntoskrnl!RtlUnicodeToMultiByteN` at `0x1401b12bd`
- `ntoskrnl!RtlMultiByteToUnicodeN` at `0x1401b124d`
- `ntoskrnl!RtlMultiByteToUnicodeN` at `0x1401b124d`
- `ntoskrnl!ZwCreateFile` at `0x1401b136c`
- `ntoskrnl!ZwCreateFile` at `0x1401b136c`
- `ntoskrnl!ZwClose` at `0x1401b142a`
- `ntoskrnl!ZwClose` at `0x1401b142a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b1304`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b1304`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401b1119`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401b1119`
- `win32kbase!Win32FreePool` at `0x1401b1417`
- `win32kbase!Win32FreePool` at `0x1401b14ff`
- `win32kbase!Win32FreePool` at `0x1401b1417`
- `win32kbase!Win32FreePool` at `0x1401b14ff`
- `WIN32K!W32GetSessionState` at `0x1401b113e`
- `WIN32K!W32GetSessionState` at `0x1401b113e`

## pseudocode

```c

```
