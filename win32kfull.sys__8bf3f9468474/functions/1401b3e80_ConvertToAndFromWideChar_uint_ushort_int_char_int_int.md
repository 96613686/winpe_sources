# ConvertToAndFromWideChar(uint,ushort *,int,char *,int,int)

- ea: `0x1401b3e80`
- end: `0x1401b4300`
- name: `?ConvertToAndFromWideChar@@YAHIPEAGHPEADHH@Z`
- size: `1152`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *, ULONG, char *, ULONG BytesInMultiByteString, int)`
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140010a10`
- `0x1400d4d68`
- `0x1401b36bc`
- `0x1401b3a20`
- `0x1401b3c74`
- `0x1401e8d38`
- `0x14026872c`
- `0x1402997b0`

## callees

- `0x14013db54`
- `0x1401b3e80`
- `0x1401b4688`
- `0x140297ba0`
- `0x140341ff0`
- `0x140342240`
- `0x140342540`

## import_xrefs

- `ntoskrnl!RtlGetDefaultCodePage` at `0x1401b3ee5`
- `ntoskrnl!RtlGetDefaultCodePage` at `0x1401b3ee5`
- `ntoskrnl!RtlUnicodeToCustomCPN` at `0x1401b408b`
- `ntoskrnl!RtlUnicodeToCustomCPN` at `0x1401b408b`
- `ntoskrnl!RtlCustomCPToUnicodeN` at `0x1401b3f97`
- `ntoskrnl!RtlCustomCPToUnicodeN` at `0x1401b3f97`
- `ntoskrnl!RtlInitCodePageTable` at `0x1401b4236`
- `ntoskrnl!RtlInitCodePageTable` at `0x1401b4236`
- `ntoskrnl!ZwReadFile` at `0x1401b41f4`
- `ntoskrnl!ZwReadFile` at `0x1401b41f4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b3f58`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b3fe9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b42d7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b3f58`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b3fe9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401b42d7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b3f22`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b3fcd`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b427c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b3f22`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b3fcd`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401b427c`
- `ntoskrnl!ZwQueryInformationFile` at `0x1401b4197`
- `ntoskrnl!ZwQueryInformationFile` at `0x1401b4197`
- `ntoskrnl!RtlUnicodeToMultiByteN` at `0x1401b40ad`
- `ntoskrnl!RtlUnicodeToMultiByteN` at `0x1401b40ad`
- `ntoskrnl!RtlMultiByteToUnicodeN` at `0x1401b403d`
- `ntoskrnl!RtlMultiByteToUnicodeN` at `0x1401b403d`
- `ntoskrnl!ZwCreateFile` at `0x1401b415c`
- `ntoskrnl!ZwCreateFile` at `0x1401b415c`
- `ntoskrnl!ZwClose` at `0x1401b421a`
- `ntoskrnl!ZwClose` at `0x1401b421a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b40f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b40f4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401b3f09`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401b3f09`
- `win32kbase!Win32FreePool` at `0x1401b4207`
- `win32kbase!Win32FreePool` at `0x1401b42ef`
- `win32kbase!Win32FreePool` at `0x1401b4207`
- `win32kbase!Win32FreePool` at `0x1401b42ef`
- `WIN32K!W32GetSessionState` at `0x1401b3f2e`
- `WIN32K!W32GetSessionState` at `0x1401b3f2e`

## pseudocode

```c

```
