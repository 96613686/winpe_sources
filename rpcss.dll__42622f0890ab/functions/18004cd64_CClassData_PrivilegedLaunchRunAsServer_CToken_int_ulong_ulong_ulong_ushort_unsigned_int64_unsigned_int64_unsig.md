# CClassData::PrivilegedLaunchRunAsServer(CToken *,int,ulong,ulong,ulong,ushort *,unsigned __int64,unsigned __int64,unsigned __int64,tagBLOB *,_GUID const *,void *,tagBLOB *,void *,void *,void *,void * *,void * *,ulong *,int *)

- ea: `0x18004cd64`
- end: `0x18004fc94`
- name: `?PrivilegedLaunchRunAsServer@CClassData@@QEAAJPEAVCToken@@HKKKPEAG_K22PEAUtagBLOB@@PEBU_GUID@@PEAX3555PEAPEAX6PEAKPEAH@Z`
- size: `12080`
- prototype: `__int64 __fastcall(CClassData *this, struct CToken *, int, unsigned int, unsigned int TokenInformation, unsigned int, unsigned __int16 *, unsigned __int64, unsigned __int64, char *, struct tagBLOB *, struct _GUID *, HANDLE hToken, struct tagBLOB *, char *, char *, char *, void **, void **, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `84`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009ab88`
- `0x18009bf1c`

## callees

- `0x180005c40`
- `0x1800081c0`
- `0x180008264`
- `0x180008648`
- `0x180009b30`
- `0x180009de0`
- `0x18000a480`
- `0x18000b310`
- `0x18000b428`
- `0x18001ec28`
- `0x18001f828`
- `0x180021c10`
- `0x1800247a8`
- `0x180025730`
- `0x180026a90`
- `0x180026bec`
- `0x180026c54`
- `0x18002830c`
- `0x18002834c`
- `0x18002ba28`
- `0x18002d6cc`
- `0x18002e210`
- `0x18002ed28`
- `0x18002f058`
- `0x18002f8cc`
- `0x18002fa6c`
- `0x18004778c`
- `0x18004c570`
- `0x18004c5bc`
- `0x18004c760`
- `0x18004c774`
- `0x18004ca64`
- `0x18004ca7c`
- `0x18004cb84`
- `0x18004cd40`
- `0x18004cd64`
- `0x18004fe30`
- `0x18004fee4`
- `0x18004ff04`
- `0x1800501cc`
- `0x180052184`
- `0x1800521a8`
- `0x18005248c`
- `0x180059e18`
- `0x180059e50`
- `0x18005c14c`
- `0x1800675cc`
- `0x1800684b4`
- `0x18006b5a4`
- `0x18006bbe4`

## import_xrefs

- `ntdll!NtResumeThread` at `0x18004f7cd`
- `ntdll!NtResumeThread` at `0x18004f7cd`
- `ntdll!NtTerminateProcess` at `0x18004d098`
- `ntdll!NtTerminateProcess` at `0x18004d186`
- `ntdll!NtTerminateProcess` at `0x18004d302`
- `ntdll!NtTerminateProcess` at `0x18004d3e9`
- `ntdll!NtTerminateProcess` at `0x18004d909`
- `ntdll!NtTerminateProcess` at `0x18004e5bd`
- `ntdll!NtTerminateProcess` at `0x18004e7bb`
- `ntdll!NtTerminateProcess` at `0x18004eb7a`
- `ntdll!NtTerminateProcess` at `0x18004ed78`
- `ntdll!NtTerminateProcess` at `0x18004eedd`
- `ntdll!NtTerminateProcess` at `0x18004f235`
- `ntdll!NtTerminateProcess` at `0x18004f42b`
- `ntdll!NtTerminateProcess` at `0x18004f950`
- `ntdll!NtTerminateProcess` at `0x18004fbd2`
- `ntdll!NtTerminateProcess` at `0x18004d098`
- `ntdll!NtTerminateProcess` at `0x18004d186`
- `ntdll!NtTerminateProcess` at `0x18004d302`
- `ntdll!NtTerminateProcess` at `0x18004d3e9`
- `ntdll!NtTerminateProcess` at `0x18004d909`
- `ntdll!NtTerminateProcess` at `0x18004e5bd`
- `ntdll!NtTerminateProcess` at `0x18004e7bb`
- `ntdll!NtTerminateProcess` at `0x18004eb7a`
- `ntdll!NtTerminateProcess` at `0x18004ed78`
- `ntdll!NtTerminateProcess` at `0x18004eedd`
- `ntdll!NtTerminateProcess` at `0x18004f235`
- `ntdll!NtTerminateProcess` at `0x18004f42b`
- `ntdll!NtTerminateProcess` at `0x18004f950`
- `ntdll!NtTerminateProcess` at `0x18004fbd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004dd12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004dd12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dcff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f64b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dcff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f64b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dd0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e5e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fa6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004faa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fb4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dd0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e5e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fa6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004faa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fb4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e40a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e59e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e5f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e674`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e6c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e79c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e8c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004eb5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ed59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004eebe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fabc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fb37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fb82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e40a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e59e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e5f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e674`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e6c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e79c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e8c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004eb5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ed59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004eebe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fabc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fb37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fb82`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e1cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e1cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004f62a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004f62a`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004d8c1`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004d9ca`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004da14`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004da57`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004da9b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004daf4`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004db31`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004db68`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004dba8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004d8c1`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004d9ca`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004da14`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004da57`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004da9b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004daf4`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004db31`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004db68`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004dba8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18004f599`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18004f599`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ce9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ce9d`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18004e4fc`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18004e4fc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004dd3e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004dd54`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004e8d7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004ef9b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004f38c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004dd3e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004dd54`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004e8d7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004ef9b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004f38c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004dd81`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004ef8f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004f37f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004f5ff`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004dd81`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004ef8f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004f37f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004f5ff`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004d588`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004d588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e2eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e398`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e736`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e9e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eaf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ecec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ee53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ef50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f11b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f1de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f3d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f5d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f80a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f8f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fa06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e2eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e398`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e736`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e9e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eaf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ecec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ee53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ef50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f11b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f1de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f3d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f5d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f80a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f8f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fa06`
- `KERNELBASE!PackageSidFromFamilyName` at `0x18004d52d`
- `KERNELBASE!PackageSidFromFamilyName` at `0x18004d52d`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18004d4de`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18004d4de`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d1e0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d361`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d870`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e608`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e617`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e626`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e635`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e64a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e65c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004facb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fada`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fae9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004faf8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fb0d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fb1f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fc2c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d1e0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d361`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d870`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e608`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e617`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e626`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e635`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e64a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e65c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004facb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fada`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fae9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004faf8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fb0d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fb1f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fc2c`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x18004ee18`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x18004ee18`
- `profapi!__imp_CreateEnvBlock` at `0x18004e35d`
- `profapi!__imp_CreateEnvBlock` at `0x18004e35d`

## string_xrefs

- `0x18004d073`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d156`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d2da`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d3c2`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d4ef`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d53e`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d599`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d5df`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d71f`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d7c1`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d8e2`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004dc2c`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004dd6a`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004deb5`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004df4d`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004e0af`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004e168`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004e379`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004e468`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004e511`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004e712`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004e832`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004e937`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004e9ba`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ea47`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ead2`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ec51`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ecc5`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ee32`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ef2c`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f038`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f0fa`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f1ba`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f33a`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f3a1`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f4c6`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f5b1`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f658`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f782`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f7e2`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f8d8`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004fba8`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f5aa`: `Failed CreateProcessAsUser`
- `0x18004d8d4`: `Failed to add attribute (DCOMLaunch)`
- `0x18004f773`: `PostCreateProcessUWPActivation failed`
- `0x18004dbb2`: `Failed to add attribute (PROC_THREAD_ATTRIBUTE_PROTECTION_LEVEL)`
- `0x18004f63d`: `rpcss.dll`
- `0x18004fb96`: `Invalid console handles specified (DCOMLaunch)`

## pseudocode

```c
__int64 __fastcall CClassData::PrivilegedLaunchRunAsServer(
        CClassData *this,
        struct CToken *a2,
        int a3,
        unsigned int a4,
        unsigned int TokenInformation,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned __int64 a8,
        unsigned __int64 a9,
        char *a10,
        struct tagBLOB *a11,
        struct _GUID *a12,
        HANDLE hToken,
        struct tagBLOB *a14,
        char *a15,
        char *a16,
        char *a17,
        void **a18,
        void **a19,
        unsigned int *a20,
        int *a21)
{
  struct tagBLOB *v22; // rbx
  int *v23; // r12
  HANDLE v24; // rsi
  char *v25; // r14
  char *v26; // r15
  char *v27; // r13
  struct DESKTOP_APPX_LAUNCH_CONTEXT *v28; // rdx
  CClassData *v29; // rcx
  int IsInteractiveUser; // eax
  int v31; // edx
  struct wil::CallContextInfo *v32; // r8
  bool v33; // r9
  __int64 v34; // rcx
  unsigned int v35; // ebx
  signed int LastError; // ebx
  __int64 v37; // rdx
  __int64 v38; // r9
  int IsActivateAsIUAllowedOld; // eax
  int v40; // r13d
  HLOCAL v41; // rcx
  unsigned __int8 v42; // r12
  unsigned int v43; // ebx
  const unsigned __int16 *v44; // rax
  int HasSysAppId; // eax
  __int64 v46; // rdx
  HLOCAL v47; // rcx
  int v48; // r14d
  unsigned __int8 v49; // r15
  __int64 v50; // rdx
  unsigned __int64 v51; // r9
  __int64 v52; // rax
  int v53; // ecx
  unsigned int v54; // eax
  int v55; // eax
  const char *v56; // r9
  int v57; // eax
  int PackageProperties; // eax
  __int64 v59; // r14
  unsigned __int8 v60; // r13
  __int64 v61; // rax
  int v62; // eax
  int v63; // edx
  int v64; // ecx
  int v65; // edx
  HLOCAL v66; // rcx
  __int64 v67; // rdx
  const char *v68; // r9
  PVOID *v69; // rdx
  DWORD v70; // r13d
  int LaunchCommandLine; // eax
  __int64 v72; // rdx
  __int64 v73; // r9
  CClassData *v74; // rcx
  CClassData *v75; // rcx
  unsigned __int16 *v76; // rax
  void *v77; // rdx
  unsigned __int16 *v78; // r9
  __int64 v79; // rcx
  unsigned __int16 *v80; // r8
  unsigned __int16 *v81; // rax
  void *RunAsToken; // rax
  HANDLE v83; // r14
  DWORD v84; // ebx
  char *v85; // r12
  __int64 v86; // rdx
  unsigned int v87; // ebx
  const unsigned __int16 *v88; // rdx
  bool v89; // si
  unsigned int v90; // ebx
  const unsigned __int16 *v91; // rdx
  int UserTokenWithPsmClaimsAdded; // eax
  void **v93; // rcx
  CClassData *v94; // rcx
  int v95; // eax
  __int64 v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rax
  int MediumRaisedCredUIToken; // eax
  WCHAR *lpDesktop; // rax
  void *v101; // rbx
  void *UserSid; // rax
  __int64 v103; // rdx
  _QWORD *v104; // r10
  HLOCAL v105; // rcx
  __int64 v106; // r8
  __int64 v107; // r9
  void (__fastcall *v108)(CClassData *, HSTRING *); // rbx
  int IsPackageSideLoaded; // eax
  __int64 v110; // rdx
  bool v111; // zf
  const char *v112; // r9
  const char *v113; // r9
  void *v114; // rdx
  HLOCAL v115; // rcx
  unsigned int v116; // ebx
  unsigned int v117; // r15d
  int v118; // r14d
  __int64 v119; // rdx
  bool v120; // r15
  char v121; // r14
  void **v122; // rax
  const unsigned __int16 *v123; // rdx
  int v124; // eax
  __int64 *v125; // rcx
  void **v126; // rax
  const unsigned __int16 *v127; // rdx
  int v128; // eax
  int IsPpleClass; // eax
  __int64 v130; // rdx
  void **v131; // rax
  int v132; // eax
  void *v133; // rax
  signed int KeyFromToken; // eax
  __int64 v135; // rdx
  bool v136; // zf
  const unsigned __int16 *v137; // rcx
  void *v138; // r8
  char *v139; // r9
  int DebuggerInfo; // eax
  unsigned __int8 v141; // r14
  int v142; // r13d
  unsigned __int64 v143; // rcx
  int *v144; // r12
  int v145; // eax
  void **v146; // rax
  int v147; // eax
  int v148; // eax
  void *v149; // rdx
  DWORD v150; // r12d
  void **v151; // rax
  DWORD v152; // eax
  DWORD v153; // eax
  int ActivationActivityIfNeeded; // eax
  __int64 v155; // rdx
  HSTRING v156; // r13
  int v157; // r12d
  CClassData *v158; // rcx
  const unsigned __int16 *v159; // r15
  const unsigned __int16 *v160; // rbx
  __int64 v161; // rdi
  HLOCAL v162; // rsi
  unsigned int v163; // r14d
  unsigned int SessionId; // eax
  __int64 v165; // r8
  NTSTATUS v166; // eax
  bool v167; // zf
  CClassData *v168; // rcx
  int v169; // esi
  unsigned int v170; // r14d
  unsigned int v171; // eax
  struct _PROCESS_INFORMATION *v172; // rdx
  HANDLE hProcess; // rax
  DWORD dwProcessId; // edx
  HANDLE hThread; // rcx
  HANDLE v177; // rax
  void *v178; // rdx
  HLOCAL v179; // rcx
  HLOCAL v180; // rcx
  struct _PROCESS_INFORMATION *v181; // rdx
  const char *cbSize; // [rsp+20h] [rbp-E0h]
  int cbSizea; // [rsp+20h] [rbp-E0h]
  const char *cbSizeb; // [rsp+20h] [rbp-E0h]
  const char *lpPreviousValue; // [rsp+28h] [rbp-D8h]
  const char *lpPreviousValuea; // [rsp+28h] [rbp-D8h]
  const char *lpPreviousValueb; // [rsp+28h] [rbp-D8h]
  NTSTATUS ExitStatus; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  bool v190; // [rsp+80h] [rbp-80h] BYREF
  bool v191[7]; // [rsp+81h] [rbp-7Fh] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v193; // [rsp+90h] [rbp-70h] BYREF
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v195; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE v196; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL v197; // [rsp+B0h] [rbp-50h] BYREF
  HLOCAL v198; // [rsp+B8h] [rbp-48h] BYREF
  bool v199; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 v200; // [rsp+C1h] [rbp-3Fh]
  bool v201; // [rsp+C2h] [rbp-3Eh] BYREF
  bool v202; // [rsp+C3h] [rbp-3Dh]
  bool v203; // [rsp+C4h] [rbp-3Ch] BYREF
  bool v204; // [rsp+C5h] [rbp-3Bh] BYREF
  bool v205; // [rsp+C6h] [rbp-3Ah] BYREF
  bool v206; // [rsp+C7h] [rbp-39h] BYREF
  char *v207; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v208; // [rsp+D0h] [rbp-30h]
  LPVOID *v209; // [rsp+D8h] [rbp-28h]
  unsigned int *p_TokenInformation; // [rsp+E0h] [rbp-20h]
  char v211; // [rsp+E8h] [rbp-18h]
  char v212; // [rsp+F0h] [rbp-10h]
  char v213; // [rsp+F1h] [rbp-Fh]
  struct _PROCESS_INFORMATION ProcessHandle; // [rsp+F8h] [rbp-8h] BYREF
  HANDLE hObject; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 **v216; // [rsp+118h] [rbp+18h] BYREF
  int *v217; // [rsp+120h] [rbp+20h]
  unsigned __int16 **p_lpEnvironment; // [rsp+128h] [rbp+28h]
  char v219; // [rsp+130h] [rbp+30h]
  char v220; // [rsp+138h] [rbp+38h] BYREF
  DWORD dwCreationFlags; // [rsp+13Ch] [rbp+3Ch]
  CToken *v222; // [rsp+140h] [rbp+40h] BYREF
  LPVOID v223; // [rsp+148h] [rbp+48h] BYREF
  int v224; // [rsp+150h] [rbp+50h]
  _QWORD v225[9]; // [rsp+160h] [rbp+60h] BYREF
  char v226; // [rsp+1A8h] [rbp+A8h]
  LPWSTR lpCommandLine; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned int v228; // [rsp+1B8h] [rbp+B8h]
  int Value; // [rsp+1BCh] [rbp+BCh] BYREF
  HLOCAL v230; // [rsp+1C0h] [rbp+C0h] BYREF
  PCWSTR packageFullName; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 (__fastcall **v232)(); // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v233[48]; // [rsp+1D8h] [rbp+D8h] BYREF
  NTSTATUS *p_ExitStatus; // [rsp+208h] [rbp+108h]
  __int64 v235; // [rsp+210h] [rbp+110h] BYREF
  PSID Sid; // [rsp+218h] [rbp+118h] BYREF
  struct DESKTOP_APPX_LAUNCH_CONTEXT *v237; // [rsp+220h] [rbp+120h] BYREF
  unsigned int v238; // [rsp+228h] [rbp+128h]
  LPWSTR StringSid; // [rsp+230h] [rbp+130h] BYREF
  void *v240; // [rsp+238h] [rbp+138h] BYREF
  void *v241; // [rsp+240h] [rbp+140h] BYREF
  __int64 v242; // [rsp+248h] [rbp+148h]
  __int64 v243; // [rsp+250h] [rbp+150h]
  __int64 v244; // [rsp+258h] [rbp+158h]
  __int64 v245; // [rsp+260h] [rbp+160h]
  int v246; // [rsp+268h] [rbp+168h] BYREF
  int v247; // [rsp+26Ch] [rbp+16Ch] BYREF
  void *v248; // [rsp+270h] [rbp+170h] BYREF
  void *OutAccessToken; // [rsp+278h] [rbp+178h] BYREF
  __int64 v250; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 *v251; // [rsp+288h] [rbp+188h] BYREF
  unsigned __int16 *lpEnvironment; // [rsp+290h] [rbp+190h] BYREF
  int v253; // [rsp+298h] [rbp+198h] BYREF
  int v254; // [rsp+29Ch] [rbp+19Ch] BYREF
  __int64 v255; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v256; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v257; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v258; // [rsp+2B8h] [rbp+1B8h] BYREF
  _QWORD *v259; // [rsp+2C0h] [rbp+1C0h] BYREF
  int *v260; // [rsp+2C8h] [rbp+1C8h]
  int v261; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v262; // [rsp+2D4h] [rbp+1D4h]
  UINT32 packageFamilyNameLength; // [rsp+2D8h] [rbp+1D8h] BYREF
  struct _GUID *v264; // [rsp+2E0h] [rbp+1E0h]
  void **v265; // [rsp+2E8h] [rbp+1E8h]
  void **v266; // [rsp+2F0h] [rbp+1F0h]
  unsigned int *v267; // [rsp+2F8h] [rbp+1F8h]
  _QWORD *v268; // [rsp+300h] [rbp+200h] BYREF
  HLOCAL *p_hMem; // [rsp+308h] [rbp+208h]
  struct _PROC_THREAD_ATTRIBUTE_LIST *v270; // [rsp+310h] [rbp+210h] BYREF
  char v271; // [rsp+318h] [rbp+218h]
  char v272[8]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v273[88]; // [rsp+328h] [rbp+228h] BYREF
  struct tagBLOB *v274; // [rsp+380h] [rbp+280h]
  _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+388h] [rbp+288h] BYREF
  HANDLE CurrentProcess; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v277; // [rsp+3A8h] [rbp+2A8h] BYREF
  unsigned __int16 *v278; // [rsp+3B0h] [rbp+2B0h]
  CClassData *v279; // [rsp+3B8h] [rbp+2B8h]
  struct tagBLOB *v280; // [rsp+3C0h] [rbp+2C0h]
  _QWORD v281[5]; // [rsp+3C8h] [rbp+2C8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+3F0h] [rbp+2F0h] BYREF
  HLOCAL v283; // [rsp+458h] [rbp+358h]
  HSTRING *p_string; // [rsp+460h] [rbp+360h]
  unsigned int *v285; // [rsp+468h] [rbp+368h]
  CToken **v286; // [rsp+470h] [rbp+370h]
  LPWSTR *p_lpCommandLine; // [rsp+478h] [rbp+378h]
  CClassData *v288; // [rsp+480h] [rbp+380h]
  int v289; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v290[142]; // [rsp+494h] [rbp+394h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 v292[232]; // [rsp+640h] [rbp+540h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+858h] [rbp+758h]

  v22 = a11;
  v23 = a21;
  v24 = hToken;
  v25 = a15;
  v26 = a16;
  v27 = a17;
  v278 = a7;
  v264 = a12;
  v280 = a14;
  v265 = a18;
  v266 = a19;
  v267 = a20;
  v262 = a3;
  v279 = this;
  v222 = a2;
  v228 = a4;
  v274 = a11;
  v260 = a21;
  lpCommandLine = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  hObject = 0;
  memset(&ProcessHandle, 0, sizeof(ProcessHandle));
  memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
  v223 = 0;
  v259 = 0;
  v230 = 0;
  packageFullName = 0;
  hMem = 0;
  CurrentProcess = GetCurrentProcess();
  v277 = 0;
  v258 = 0;
  v193 = 0;
  v195 = 0;
  v198 = 0;
  v197 = 0;
  v238 = CClassData::AppIDFlags(this);
  v220 = (char)v28;
  v201 = (char)v28;
  v237 = v28;
  IsInteractiveUser = CClassData::IsInteractiveUser(v29);
  v31 = 0;
  if ( !IsInteractiveUser || (v213 = 1, (CClassData::AppIDFlags(this) & 0x1000) == 0) )
    v213 = v31;
  memset_0(&v289, v31, 0x114u);
  memset_0(v292, 0, sizeof(v292));
  v261 = 464;
  lpMem = 0;
  v190 = 0;
  v254 = 0;
  v196 = 0;
  *v265 = 0;
  v225[7] = this;
  *v266 = 0;
  *v267 = 0;
  v225[0] = &v201;
  v225[1] = &packageFullName;
  v225[2] = &v254;
  v225[3] = &hMem;
  v225[4] = &v259;
  *v23 = 0;
  v225[5] = &v237;
  ExitStatus = 0;
  v225[6] = &ExitStatus;
  v225[8] = &v190;
  v232 = &off_18010ECB0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v233,
    (struct wil::details::IFailureCallback *)&v232,
    v32,
    v33);
  p_ExitStatus = &ExitStatus;
  if ( v22 )
  {
    v202 = 1;
  }
  else
  {
    v34 = *((_QWORD *)this + 11);
    v202 = 0;
    if ( (-(__int64)(v34 != 0) & (v34 + 80)) != 0 )
      v202 = *(_QWORD *)(((v34 + 80) & -(__int64)(v34 != 0)) + 8) != 0;
  }
  v35 = v228 & 4;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    if ( v35 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      LastError = -2147418113;
      v37 = 2558;
      v38 = 2147549183LL;
      goto LABEL_11;
    }
  }
  else if ( v35 )
  {
    IsActivateAsIUAllowedOld = CClassData::PrivilegedLaunchIsActivateAsIUAllowedOld(this, v222, 1);
    LastError = IsActivateAsIUAllowedOld;
    if ( IsActivateAsIUAllowedOld < 0 )
    {
      v38 = (unsigned int)IsActivateAsIUAllowedOld;
      v37 = 2564;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)v38,
        (int)cbSize);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
      if ( ProcessHandle.hProcess )
        NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
LABEL_38:
      v226 = 0;
      lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v225);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v196);
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v197);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v198);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v195);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v193);
      v47 = hMem;
      hMem = 0;
      if ( v47 )
        LocalFree(v47);
      goto LABEL_495;
    }
  }
  if ( v25 || v26 || v27 )
  {
    if ( !(unsigned int)CClassData::HasActivateAsPackage(this) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)0x80070005LL,
        (int)cbSize);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
      if ( ProcessHandle.hProcess )
        NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
      v226 = 0;
      lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v225);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v196);
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v197);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v198);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v195);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v193);
      v41 = hMem;
      hMem = 0;
      if ( v41 )
        LocalFree(v41);
      goto LABEL_26;
    }
    if ( (unsigned __int64)(v25 - 1) > 0xFFFFFFFFFFFFFFFDuLL
      || (unsigned __int64)(v26 - 1) > 0xFFFFFFFFFFFFFFFDuLL
      || (unsigned __int64)(v27 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xA12,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)0x80070057LL,
        (int)"Invalid console handles specified (DCOMLaunch)",
        lpPreviousValue);
      goto LABEL_527;
    }
    StartupInfo.dwFlags |= 0x100u;
    StartupInfo.hStdError = v27;
    v40 = 1024;
    dwCreationFlags = 1024;
    StartupInfo.hStdInput = v25;
    StartupInfo.hStdOutput = v26;
    v212 = 1;
  }
  else
  {
    v40 = 1040;
    v212 = 0;
    dwCreationFlags = 1040;
  }
  v200 = 0;
  v42 = 0;
  v206 = 0;
  v205 = 0;
  v204 = 0;
  v203 = 0;
  v199 = 0;
  if ( (unsigned int)CClassData::HasActivateAsPackage(this) )
  {
    packageFullName = CClassData::ExecutionPackageName(this);
    if ( (unsigned int)CClassData::GetRuntimeBehavior(this) )
    {
      if ( (unsigned int)CClassData::GetRuntimeBehavior(this) != 1
        && (unsigned int)CClassData::GetRuntimeBehavior(this) != 3 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v50 = 2653;
        LastError = -2147418113;
LABEL_45:
        v51 = (unsigned int)LastError;
LABEL_46:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v50,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)v51,
          (int)cbSize);
        goto LABEL_47;
      }
      v49 = 1;
      v48 = 2;
      v42 = 1;
    }
    else
    {
      if ( (unsigned __int8)IsPrepareExclusiveResourceForPackageActivationPresent() )
      {
        v43 = *((_DWORD *)this + 33);
        v44 = CClassData::AppUserModelID(this);
        HasSysAppId = PrepareExclusiveResourceForPackageActivation(packageFullName, v44, v43, &v258);
        LastError = HasSysAppId;
        if ( HasSysAppId < 0 )
        {
          v46 = 2637;
          goto LABEL_36;
        }
        v201 = v258 != 0;
      }
      v48 = 1;
      v49 = 1;
    }
    v224 = v48;
    if ( !(unsigned int)CClassData::HasActivateAsPackage(this) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v52 = *((_QWORD *)this + 12);
    if ( v52 )
      v53 = *(_DWORD *)(v52 + 252);
    else
      v53 = *(_DWORD *)(*((_QWORD *)this + 11) + 300LL);
    if ( v53 == 1 && CClassData::GetAppTrustLevel(this) == PartialTrust )
    {
      if ( CClassData::GetAppTrustLevel(this) == PartialTrust )
      {
        memset_0(packageFamilyName, 0, 0x82u);
        packageFamilyNameLength = 65;
        v54 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
        if ( v54 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xA66,
                        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                        (const char *)v54,
                        (unsigned int)cbSize);
          goto LABEL_47;
        }
        Sid = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &Sid,
          0);
        v55 = PackageSidFromFamilyName(packageFamilyName, &Sid);
        if ( v55 < 0 )
        {
          LastError = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0xA68,
                        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                        (const char *)(unsigned int)v55,
                        (int)cbSize);
LABEL_63:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
          goto LABEL_47;
        }
        StringSid = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &StringSid,
          0);
        if ( !ConvertSidToStringSidW(Sid, &StringSid) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xA6A,
                        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                        v56);
LABEL_66:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          goto LABEL_63;
        }
        v57 = StringCchCopyW(v290, 0x88u, StringSid);
        LastError = v57;
        if ( v57 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA6B,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)v57,
            (int)cbSize);
          goto LABEL_66;
        }
        v289 = 1;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchHosts>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchHosts>::GetImpl'::`2'::impl) )
    {
      PackageProperties = GetPackageProperties(packageFullName, &v206, &v205, &v204, &v203, &v199);
      LastError = PackageProperties;
      if ( PackageProperties < 0 )
      {
        v51 = (unsigned int)PackageProperties;
        v50 = 2678;
        goto LABEL_46;
      }
      if ( v199 && CClassData::IsSystemSurrogateServer(this) )
        v200 = 1;
    }
  }
  else
  {
    v49 = 0;
    v224 = 0;
    if ( !v213 )
      goto LABEL_86;
    v191[0] = 0;
    HasSysAppId = CToken::HasSysAppId(v222, v191);
    LastError = HasSysAppId;
    if ( HasSysAppId < 0 )
    {
      v46 = 2696;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v46,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)(unsigned int)HasSysAppId,
        (int)cbSize);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
      if ( ProcessHandle.hProcess )
        NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
      goto LABEL_38;
    }
    if ( !v191[0] )
      goto LABEL_86;
    v48 = (unsigned __int8)IsPrepareExclusiveResourceForPackageActivationPresent() == 0 ? 4 : 0;
    v224 = v48;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpMem,
      0);
    LastError = GetPackageNameFromToken(*((void **)v222 + 9), (unsigned __int16 **)&lpMem);
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xAA0,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)(unsigned int)LastError,
        (int)"Failed GetPackageName",
        lpPreviousValue);
LABEL_47:
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
      if ( ProcessHandle.hProcess )
        NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
      goto LABEL_38;
    }
  }
  if ( (unsigned int)(v48 - 1) <= 1 || (v224 = v48, v48 == 4) )
    dwCreationFlags = v40 | 4;
LABEL_86:
  StartupInfo.cb = 112;
  v59 = -1;
  v246 = 0;
  v60 = 0;
  v61 = *((_QWORD *)this + 11);
  if ( !v61 || *(_DWORD *)(v61 + 76) == -1 )
  {
LABEL_90:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchHosts>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchHosts>::GetImpl'::`2'::impl) )
    {
      if ( v42 || (v62 = 0, v200) )
        v62 = 1;
      v63 = v62 + v49;
    }
    else
    {
      v63 = v49 + v42;
    }
    v64 = v63 + v202 + v201;
    if ( v212 )
    {
      v65 = 1;
      ++v64;
    }
    else
    {
      v65 = 0;
    }
    v270 = 0;
    v271 = 1;
    p_hMem = &hMem;
    LastError = InitializeAttributeList((v289 != 0) + v65 + (unsigned int)v60 + v64, v280, &v270);
    if ( v271 )
    {
      v66 = *p_hMem;
      *p_hMem = v270;
      if ( v66 )
        LocalFree(v66);
    }
    if ( LastError < 0 )
    {
      v50 = 2814;
      goto LABEL_45;
    }
    if ( v49 )
    {
      do
        ++v59;
      while ( packageFullName[v59] );
      if ( !UpdateProcThreadAttribute(
              (LPPROC_THREAD_ATTRIBUTE_LIST)hMem,
              0,
              0x20008u,
              (PVOID)packageFullName,
              2 * v59,
              0,
              0) )
      {
        v67 = 2821;
LABEL_109:
        v68 = "Failed to add attribute (DCOMLaunch)";
        goto LABEL_110;
      }
    }
    Value = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchHosts>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchHosts>::GetImpl'::`2'::impl) )
    {
      if ( v42 || v200 )
      {
        Value = (4 * v42) | (8 * v200);
        if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x20012u, &Value, 4u, 0, 0) )
        {
          v67 = 2836;
          goto LABEL_109;
        }
      }
    }
    else
    {
      Value = 4;
      if ( v42 && !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x20012u, &Value, 4u, 0, 0) )
      {
        v67 = 2846;
        goto LABEL_109;
      }
    }
    if ( v201 && !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x2000Du, &v258, 8u, 0, 0) )
    {
      v67 = 2854;
      goto LABEL_109;
    }
    if ( v289 && !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x20013u, &v289, 0x114u, 0, 0) )
    {
      v67 = 2860;
      goto LABEL_109;
    }
    if ( v202 )
    {
      v69 = (PVOID *)v274;
      if ( !v274 )
        v69 = (PVOID *)((*((_QWORD *)this + 11) + 80LL)
                      & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this + 11) >> 64));
      if ( !UpdateProcThreadAttribute(
              (LPPROC_THREAD_ATTRIBUTE_LIST)hMem,
              0,
              0x20007u,
              v69[1],
              *(unsigned int *)v69,
              0,
              0) )
      {
        v67 = 2870;
        goto LABEL_109;
      }
    }
    if ( v212 )
    {
      if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x20000u, &CurrentProcess, 8u, 0, 0) )
      {
        v67 = 2876;
        goto LABEL_109;
      }
      if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x2000Au, &v277, 8u, 0, 0) )
      {
        v67 = 2882;
        goto LABEL_109;
      }
    }
    if ( v60 )
    {
      if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x2000Bu, &v246, 4u, 0, 0) )
      {
        v68 = "Failed to add attribute (PROC_THREAD_ATTRIBUTE_PROTECTION_LEVEL)";
        v67 = 2888;
LABEL_110:
        LastError = wil::details::in1diag3::Return_GetLastErrorMsg(
                      retaddr,
                      (void *)v67,
                      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                      v68,
                      cbSize);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
        if ( ProcessHandle.hProcess )
          NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
        goto LABEL_38;
      }
      v70 = dwCreationFlags | 0x40000;
      dwCreationFlags |= 0x40000u;
    }
    else
    {
      v70 = dwCreationFlags;
    }
    if ( hMem )
    {
      v70 |= 0x80000u;
      v283 = hMem;
      dwCreationFlags = v70;
    }
    if ( lpCommandLine )
      wil::details::close_invoke_helper<1,void (*)(void *),&void PrivMemFree(void *),unsigned short *>::close_reset(lpCommandLine);
    lpCommandLine = 0;
    LaunchCommandLine = CClassData::GetLaunchCommandLine(this, &lpCommandLine);
    LastError = LaunchCommandLine;
    if ( LaunchCommandLine < 0 )
    {
      v72 = 2904;
LABEL_148:
      v73 = (unsigned int)LaunchCommandLine;
LABEL_149:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v72,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)v73,
        (int)cbSize);
LABEL_491:
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
      if ( ProcessHandle.hProcess )
        NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
      v226 = 0;
LABEL_494:
      lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v225);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v196);
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v197);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v198);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v195);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v193);
      wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &hMem,
        0);
      goto LABEL_495;
    }
    if ( *((_BYTE *)this + 80) == 3 )
      StartupInfo.lpTitle = 0;
    else
      StartupInfo.lpTitle = (LPWSTR)*((_QWORD *)this + 2);
    StartupInfo.dwFlags |= 0x80u;
    if ( !(unsigned int)CClassData::IsInteractiveUser(this) && !(unsigned int)CClassData::HasActivateAsPackage(this) )
    {
      CClassData::AppIDFlags(this);
      CClassData::RunAsUser(v74);
      v76 = CClassData::RunAsDomain(v75);
      v79 = *((_QWORD *)this + 11);
      v80 = v76;
      if ( v79 )
        v81 = (unsigned __int16 *)(v79 + 118);
      else
        v81 = CClassData::WinRTServerName(this);
      RunAsToken = GetRunAsToken(a6, v81, v80, v78, 1, v77);
      v83 = hObject;
      v24 = RunAsToken;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v84 = GetLastError();
        CloseHandle(v83);
        SetLastError(v84);
      }
      v85 = a10;
      hObject = v24;
      goto LABEL_213;
    }
    if ( !v262 )
    {
      if ( !v222 || !ImpersonateLoggedOnUser(*((HANDLE *)v222 + 9)) )
      {
        v86 = 2927;
        goto LABEL_167;
      }
      v190 = 1;
      if ( v24 && !ImpersonateLoggedOnUser(v24) )
      {
        v86 = 2929;
LABEL_167:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v86,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)0x80070005LL,
          (int)cbSize);
LABEL_446:
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
        if ( ProcessHandle.hProcess )
          NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
        v226 = 0;
        lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v225);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v196);
        utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v197);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v198);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v195);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v193);
        wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
          &hMem,
          0);
LABEL_26:
        LastError = -2147024891;
LABEL_495:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v230);
        utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v223);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
        wil::details::CloseProcessInformation((wil::details *)&ProcessHandle, v172);
        utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpCommandLine);
        return (unsigned int)LastError;
      }
      RevertToSelf();
      v190 = 0;
    }
    if ( (unsigned int)CClassData::HasActivateAsPackage(this) )
    {
      if ( v24 )
      {
        v85 = a10;
        goto LABEL_181;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        0);
      v87 = TokenInformation;
      CClassData::ExecutionPackageName(this);
      v85 = a10;
      LaunchCommandLine = GetInteractiveUserTokenForCallerRequest(v222, v88, (unsigned __int64)a10, v87, 1, &hObject);
      LastError = LaunchCommandLine;
      if ( LaunchCommandLine < 0 )
      {
        v72 = 2945;
        goto LABEL_148;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        0);
      if ( (CClassData::AppIDFlags(this) & 0x200) != 0
        || (v89 = 0, (unsigned int)((__int64 (*)(void))CClassData::IdentityType)() == 5) )
      {
        v89 = 1;
      }
      v90 = TokenInformation;
      CClassData::ExecutionPackageName(this);
      v85 = a10;
      LaunchCommandLine = GetInteractiveUserTokenForCallerRequest(v222, v91, (unsigned __int64)a10, v90, v89, &hObject);
      LastError = LaunchCommandLine;
      if ( LaunchCommandLine < 0 )
      {
        v72 = 2970;
        goto LABEL_148;
      }
    }
    v24 = hObject;
LABEL_181:
    if ( v24 )
    {
      if ( v213 )
      {
        v248 = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v248,
          0);
        UserTokenWithPsmClaimsAdded = GetUserTokenWithPsmClaimsAdded(v222, v24, 1, &v248);
        LastError = UserTokenWithPsmClaimsAdded;
        if ( UserTokenWithPsmClaimsAdded < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBA8,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)UserTokenWithPsmClaimsAdded,
            (int)cbSize);
          v93 = &v248;
LABEL_185:
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v93);
          goto LABEL_491;
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
          &hObject,
          &v248);
        v24 = hObject;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v248);
      }
      if ( (CClassData::AppIDFlags(this) & 8) == 0 && !(unsigned int)CClassData::HasActivateAsPackage(v94) )
      {
        v240 = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v240,
          0);
        v95 = CClassData::DuplicateAndAdjustInteractiveUserTokenILIfNecessary(v222, v24, &v240);
        LastError = v95;
        if ( v95 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBB7,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)v95,
            (int)cbSize);
          v93 = &v240;
          goto LABEL_185;
        }
        if ( (char *)v240 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
            &hObject,
            &v240);
          v24 = hObject;
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v240);
      }
    }
    if ( (CClassData::AppIDFlags(this) & 0x8000) != 0 )
    {
      v268 = 0;
      v96 = *((_QWORD *)this + 8);
      v242 = 0x42EB16A6924DC564LL;
      v243 = 0x6FA07DFA619A9A92LL;
      v244 = 0x4ABD4CB77FC12E96LL;
      v245 = 0x2906B14578EFAAADLL;
      if ( v96 )
      {
        LaunchCommandLine = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v96 + 40LL))(v96, &v268);
        LastError = LaunchCommandLine;
        if ( LaunchCommandLine < 0 )
        {
          v72 = 3022;
          goto LABEL_148;
        }
        if ( v268 )
        {
          v97 = *v268 - v242;
          if ( *v268 == v242 )
            v97 = v268[1] - v243;
          if ( !v97 )
            goto LABEL_205;
          v98 = *v268 - v244;
          if ( *v268 == v244 )
            v98 = v268[1] - v245;
          if ( !v98 )
          {
LABEL_205:
            v241 = 0;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              &v241,
              0);
            MediumRaisedCredUIToken = GetMediumRaisedCredUIToken(v24, &v241);
            LastError = MediumRaisedCredUIToken;
            if ( MediumRaisedCredUIToken < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBD3,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)(unsigned int)MediumRaisedCredUIToken,
                (int)cbSize);
              v93 = &v241;
              goto LABEL_185;
            }
            if ( v241 )
            {
              wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
                &hObject,
                &v241);
              v24 = hObject;
            }
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v241);
          }
        }
      }
    }
    v111 = (CClassData::AppIDFlags(this) & 1) == 0;
    lpDesktop = StartupInfo.lpDesktop;
    if ( !v111 )
      lpDesktop = v278;
    StartupInfo.lpDesktop = lpDesktop;
LABEL_213:
    if ( !v24 )
    {
      LastError = -2147467238;
      v72 = 3063;
      v73 = 2147500058LL;
      goto LABEL_149;
    }
    v101 = 0;
    if ( !(unsigned int)CClassData::HasActivateAsPackage(this) )
    {
      UserSid = GetUserSid(v24);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v223,
        UserSid);
      if ( !v223 )
      {
        v103 = 3072;
LABEL_218:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v103,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)0x8007000ELL,
          (int)cbSize);
LABEL_363:
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
        if ( ProcessHandle.hProcess )
          NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
        v226 = 0;
        lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v225);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v196);
        utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v197);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v198);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v195);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v193);
        wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
          &hMem,
          0);
        LastError = -2147024882;
        goto LABEL_495;
      }
      if ( (CClassData::AppIDFlags(this) & 2) != 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &v230,
          0);
        LaunchCommandLine = CToken::GetLogonIDSid(v24, &v230);
        LastError = LaunchCommandLine;
        if ( LaunchCommandLine < 0 )
        {
          v72 = 3075;
          goto LABEL_148;
        }
        LODWORD(v101) = 1;
      }
      v104 = HeapAlloc(g_hHeap, 0, 0xA0u);
      if ( !v104 )
      {
        v259 = 0;
        v103 = 3080;
        goto LABEL_218;
      }
      v105 = v230;
      *v104 = v223;
      v104[1] = v105;
      v104[2] = 0;
      v104[3] = 0;
      v104[4] = 0;
      v104[5] = 0;
      v259 = v104;
      if ( (_DWORD)v101 )
      {
        v106 = 0x1FFFFF;
        v107 = 0;
      }
      else
      {
        v106 = 0;
        v107 = 0x1FFFFF;
      }
      LODWORD(cbSize) = 0;
      v101 = (void *)CAccessInfo::IdentifyAccess(v104, (_DWORD)v101 != 0 ? 3 : 0, v106, v107);
      if ( !v101 )
      {
        v103 = 3087;
        goto LABEL_218;
      }
    }
    ProcessAttributes.nLength = 24;
    v216 = &v251;
    ProcessAttributes.lpSecurityDescriptor = v101;
    v217 = &v253;
    p_lpEnvironment = &lpEnvironment;
    v207 = &v220;
    v208 = v292;
    v209 = &v223;
    p_TokenInformation = &TokenInformation;
    ProcessAttributes.bInheritHandle = 0;
    v251 = 0;
    lpEnvironment = 0;
    v253 = 0;
    v219 = 1;
    v211 = 1;
    string = 0;
    v108 = *(void (__fastcall **)(CClassData *, HSTRING *))(*(_QWORD *)this + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v108(this, &string);
    v288 = this;
    p_string = &string;
    v285 = &a6;
    v286 = &v222;
    p_lpCommandLine = &lpCommandLine;
    wil::ThreadFailureCallback__lambda_4f8fe278ca1d0cbd6998976ea4d86a7e___((struct wil::details::IFailureCallback *)v272);
    IsPackageSideLoaded = CreateEnvBlock(&v251, v24, 0);
    LastError = IsPackageSideLoaded;
    if ( IsPackageSideLoaded < 0 )
    {
      v110 = 3134;
LABEL_232:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v110,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)(unsigned int)IsPackageSideLoaded,
        (int)cbSize);
      goto LABEL_233;
    }
    if ( *((_QWORD *)this + 7) && (unsigned __int8)IsSaferCloseLevelPresent() )
    {
      OutAccessToken = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &OutAccessToken,
        0);
      if ( !SaferComputeTokenFromLevel(*((SAFER_LEVEL_HANDLE *)this + 7), v24, &OutAccessToken, 0, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xC43,
                      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                      v112);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&OutAccessToken);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
        WindowsDeleteString(string);
        string = 0;
        if ( v211 )
        {
          v211 = 0;
          v111 = *v207 == 0;
LABEL_235:
          if ( !v111 )
            UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
        }
LABEL_237:
        if ( v219 )
        {
          v219 = 0;
          if ( *v216 )
            DestroyEnvBlock();
          if ( *v217 )
            HeapFree(g_hHeap, 0, *p_lpEnvironment);
        }
        goto LABEL_491;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        &hObject,
        &OutAccessToken);
      v24 = hObject;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&OutAccessToken);
    }
    if ( TokenInformation && !SetTokenInformation(v24, TokenSessionId, &TokenInformation, 4u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xC4B,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                    v113);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
      WindowsDeleteString(string);
      string = 0;
      if ( v211 )
      {
        v211 = 0;
        if ( *v207 )
          UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
      }
      if ( v219 )
      {
        v219 = 0;
        if ( *v216 )
          DestroyEnvBlock();
        if ( *v217 )
          HeapFree(g_hHeap, 0, *p_lpEnvironment);
      }
LABEL_258:
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
      if ( ProcessHandle.hProcess )
        NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
      v226 = 0;
      lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v225);
      if ( (char *)v196 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v196);
      if ( lpMem )
        HeapFree(g_hHeap, 0, lpMem);
      if ( v197 )
        LocalFree(v197);
      if ( v198 )
        LocalFree(v198);
      if ( v195 )
        LocalFree(v195);
      if ( v193 )
        LocalFree(v193);
      v115 = hMem;
      hMem = 0;
      if ( v115 )
        LocalFree(v115);
      if ( v230 )
        LocalFree(v230);
      if ( v223 )
        HeapFree(g_hHeap, 0, v223);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( ProcessHandle.hProcess )
        wil::details::CloseHandle((wil::details *)ProcessHandle.hProcess, v114);
      if ( ProcessHandle.hThread )
        wil::details::CloseHandle((wil::details *)ProcessHandle.hThread, v114);
      if ( lpCommandLine )
        HeapFree(g_hHeap, 0, lpCommandLine);
      return (unsigned int)LastError;
    }
    v116 = v228 & 0x10;
    v117 = v228 & 2;
    if ( (v228 & 2) != 0 || (v228 & 0x10) != 0 )
    {
      v247 = 0;
      v118 = IsDeveloperLicenseInstalled(&v247);
      if ( v118 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC52,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)v118,
          (int)cbSize);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
        WindowsDeleteString(string);
        string = 0;
        if ( v211 )
        {
          v211 = 0;
          if ( *v207 )
            UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
        }
        if ( v219 )
        {
          v219 = 0;
          if ( *v216 )
            DestroyEnvBlock();
          if ( *v217 )
            HeapFree(g_hHeap, 0, *p_lpEnvironment);
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
        if ( ProcessHandle.hProcess )
          NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
        v226 = 0;
        lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v225);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v196);
        utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v197);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v198);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v195);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v193);
        wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
          &hMem,
          0);
        LastError = v118;
        goto LABEL_495;
      }
      if ( !v247 )
      {
        v119 = 3155;
LABEL_302:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v119,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)0x80070005LL,
          (int)cbSize);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
        WindowsDeleteString(string);
        goto LABEL_303;
      }
    }
    ImpersonateLoggedOnUser(v24);
    v190 = 1;
    if ( v117 )
    {
      v120 = 0;
    }
    else
    {
      v120 = 0;
      v121 = 0;
      if ( !v116 )
        goto LABEL_321;
    }
    v255 = 0;
    v122 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v255);
    v123 = L"WIN://DESIGN_MODE_V2";
    if ( !v116 )
      v123 = L"WIN://DESIGN_MODE";
    v124 = DuplicateAndSetTokenBooleanClaim(v24, v123, v122);
    LastError = v124;
    if ( v124 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC6D,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)(unsigned int)v124,
        (int)cbSize);
      v125 = &v255;
LABEL_319:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v125);
LABEL_233:
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
      WindowsDeleteString(string);
      string = 0;
      if ( v211 )
      {
        v211 = 0;
        v111 = *v207 == 0;
        goto LABEL_235;
      }
      goto LABEL_237;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &hObject,
      &v255);
    v24 = hObject;
    v121 = 1;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v255);
LABEL_321:
    if ( (v238 & 0x80u) != 0 )
    {
      v191[0] = 0;
      IsPackageSideLoaded = CToken::IsPackageSideLoaded(v222, v191);
      LastError = IsPackageSideLoaded;
      if ( IsPackageSideLoaded < 0 )
      {
        v110 = 3190;
        goto LABEL_232;
      }
      if ( !v191[0] )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC77,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)0x80070005LL,
          (int)cbSize);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
        WindowsDeleteString(string);
LABEL_303:
        string = 0;
        if ( v211 )
        {
          v211 = 0;
          if ( *v207 )
            UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
        }
        if ( v219 )
        {
          v219 = 0;
          if ( *v216 )
            DestroyEnvBlock();
          if ( *v217 )
            HeapFree(g_hHeap, 0, *p_lpEnvironment);
        }
        goto LABEL_446;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpMem,
        0);
      IsPackageSideLoaded = GetPackageNameFromToken(*((void **)v222 + 9), (unsigned __int16 **)&lpMem);
      LastError = IsPackageSideLoaded;
      if ( IsPackageSideLoaded < 0 )
      {
        v110 = 3195;
        goto LABEL_232;
      }
      v256 = 0;
      v126 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v256);
      v128 = DuplicateAndSetTokenStringClaim(v24, v127, (const unsigned __int16 *)lpMem, v126);
      LastError = v128;
      if ( v128 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC7F,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)v128,
          (int)cbSize);
        v125 = &v256;
        goto LABEL_319;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        &hObject,
        &v256);
      v24 = hObject;
      v121 = 1;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v256);
    }
    v191[0] = 0;
    if ( (unsigned int)CClassData::HasActivateAsPackage(this) && (unsigned __int8)IsPsmCreateBrokerTokenPresent() )
    {
      IsPpleClass = CClassData::IsPpleClass(this, v191);
      LastError = IsPpleClass;
      if ( IsPpleClass < 0 )
      {
        v130 = 3210;
LABEL_335:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v130,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)IsPpleClass,
          (int)cbSize);
        goto LABEL_336;
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchHosts>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchHosts>::GetImpl'::`2'::impl) )
      {
        IsPpleClass = GetPackageProperties(packageFullName, &v206, &v205, &v204, &v203, &v199);
        LastError = IsPpleClass;
        if ( IsPpleClass < 0 )
        {
          v130 = 3214;
          goto LABEL_335;
        }
      }
      v257 = 0;
      v131 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v257);
      v120 = v191[0];
      v132 = CClassData::AdjustActivationToken(
               this,
               v24,
               v228,
               a8,
               v264,
               v191[0],
               v206,
               v205,
               v204,
               v203,
               v199,
               0,
               v131);
      LastError = v132;
      if ( v132 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC93,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)v132,
          (int)cbSize);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v257);
LABEL_336:
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
        WindowsDeleteString(string);
        string = 0;
        if ( v211 )
        {
          v211 = 0;
          if ( *v207 )
            UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
        }
        if ( v219 )
        {
          v219 = 0;
          if ( *v216 )
            DestroyEnvBlock();
          if ( *v217 )
            HeapFree(g_hHeap, 0, *p_lpEnvironment);
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
        if ( ProcessHandle.hProcess )
          NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
        v226 = 0;
        goto LABEL_494;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        v257);
      v24 = hObject;
      v257 = 0;
      v121 = 1;
    }
    if ( !v223 )
    {
      v133 = GetUserSid(v24);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v223,
        v133);
      if ( !v223 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC9C,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)0x8007000ELL,
          (int)cbSize);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
        WindowsDeleteString(string);
        string = 0;
        if ( v211 )
        {
          v211 = 0;
          if ( *v207 )
            UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
        }
        if ( v219 )
        {
          v219 = 0;
          if ( *v216 )
            DestroyEnvBlock();
          if ( *v217 )
            HeapFree(g_hHeap, 0, *p_lpEnvironment);
        }
        goto LABEL_363;
      }
    }
    if ( (unsigned int)CClassData::HasActivateAsPackage(this) && (unsigned __int8)IsMountVolumeForAppPackagePresent() )
    {
      if ( !v292[0] )
      {
        KeyFromToken = PsmGetKeyFromToken(v24, v292, &v261, 0);
        if ( KeyFromToken < 0 )
        {
          v135 = 3235;
          goto LABEL_371;
        }
      }
      KeyFromToken = MountVolumeForAppPackage(v292, v223, TokenInformation);
      if ( (KeyFromToken & 0x20000000) != 0 )
      {
        KeyFromToken &= ~0x20000000u;
        LastError = KeyFromToken > 0 ? (unsigned __int16)KeyFromToken | 0x80070000 : KeyFromToken;
        if ( LastError < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCA5,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)LastError,
            (int)cbSize);
          wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
          WindowsDeleteString(string);
          string = 0;
          if ( v211 )
          {
            v211 = 0;
            v136 = *v207 == 0;
LABEL_373:
            if ( !v136 )
              UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
          }
LABEL_375:
          if ( v219 )
          {
            v219 = 0;
            if ( *v216 )
              DestroyEnvBlock();
            if ( *v217 )
              HeapFree(g_hHeap, 0, *p_lpEnvironment);
          }
LABEL_380:
          wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
          if ( ProcessHandle.hProcess )
            NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
          v226 = 0;
          goto LABEL_494;
        }
      }
      if ( KeyFromToken < 0 )
      {
        v135 = 3237;
LABEL_371:
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)v135,
                      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                      (const char *)(unsigned int)KeyFromToken,
                      (int)cbSize);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
        WindowsDeleteString(string);
        string = 0;
        if ( v211 )
        {
          v211 = 0;
          v136 = *v207 == 0;
          goto LABEL_373;
        }
        goto LABEL_375;
      }
      v220 = 1;
    }
    if ( v121 )
    {
      RevertToSelf();
      v190 = 0;
      if ( !ImpersonateLoggedOnUser(v24) )
      {
        v119 = 3249;
        goto LABEL_302;
      }
      v190 = 1;
    }
    if ( v195 )
      wil::details::close_invoke_helper<1,void * (*)(void *),&void * LocalFree(void *),void *>::close_reset(v195);
    v195 = 0;
    if ( v193 )
      wil::details::close_invoke_helper<1,void * (*)(void *),&void * LocalFree(void *),void *>::close_reset(v193);
    v137 = lpCommandLine;
    v193 = 0;
    if ( *((_QWORD *)this + 5) )
      v137 = (const unsigned __int16 *)*((_QWORD *)this + 5);
    if ( v85 )
    {
      v138 = (void *)*((_QWORD *)v222 + 9);
      v139 = (char *)v222 + 156;
    }
    else
    {
      v138 = 0;
      v139 = 0;
    }
    DebuggerInfo = GetDebuggerInfo(
                     v24,
                     v223,
                     v138,
                     v139,
                     v190,
                     v137,
                     (unsigned __int16 **)&v193,
                     (unsigned __int16 **)&v195);
    if ( DebuggerInfo < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCBB,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)(unsigned int)DebuggerInfo,
        cbSizea);
    if ( v193 )
    {
      v141 = 1;
      dwCreationFlags = v70 | 4;
    }
    else
    {
      v141 = 0;
    }
    v142 = v224;
    v143 = (unsigned int)(v224 - 1);
    if ( v224 != 1 )
    {
      if ( v224 == 2 || (v143 = (unsigned int)(v224 - 3), v224 == 3) )
      {
        v281[2] = packageFullName;
        v281[0] = v24;
        v281[1] = 0;
        v281[3] = *((_QWORD *)this + 5);
        v281[4] = 3;
        v145 = PrepareDesktopAppXActivation(v281, &v237);
        LastError = v145;
        if ( v145 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCF0,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)v145,
            cbSizea);
          wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
          WindowsDeleteString(string);
          string = 0;
          if ( v211 )
          {
            v211 = 0;
            if ( *v207 )
              UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
          }
          wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v216);
          wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
          if ( ProcessHandle.hProcess )
            NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
          v226 = 0;
          goto LABEL_494;
        }
        v143 = *((unsigned int *)v237 + 4);
        *v260 = v143;
        goto LABEL_436;
      }
      if ( v224 != 4 )
        goto LABEL_436;
    }
    if ( v141 || !lpMem )
    {
      *v260 = v141;
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v197,
        0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v198,
        0);
      v144 = v260;
      LastError = PrepareUWPActivation(
                    (unsigned __int16 *)lpMem,
                    (char *)v222 + 156,
                    (unsigned __int16 **)&v198,
                    (unsigned __int16 **)&v197,
                    v260);
      if ( LastError < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xCCB,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)LastError,
          (int)"Failed PrepareUWPActivation",
          lpPreviousValuea);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
        WindowsDeleteString(string);
        string = 0;
        if ( v211 )
        {
          v211 = 0;
          if ( *v207 )
            UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
        }
        wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v216);
        goto LABEL_380;
      }
      if ( *v144 )
      {
        if ( v198 )
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v193,
            &v198);
        if ( v197 )
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v195,
            &v197);
      }
    }
LABEL_436:
    if ( v237 && *((_QWORD *)v237 + 7) )
    {
      v250 = 0;
      v146 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v250);
      v147 = CClassData::AdjustActivationToken(
               this,
               v24,
               v228,
               a8,
               v264,
               v120,
               v206,
               v205,
               v204,
               v203,
               v199,
               v237,
               v146);
      LastError = v147;
      if ( v147 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD02,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)v147,
          cbSizea);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v250);
LABEL_440:
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
        goto LABEL_486;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        &hObject,
        &v250);
      v24 = hObject;
      RevertToSelf();
      v190 = 0;
      if ( !ImpersonateLoggedOnUser(v24) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD0C,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)0x80070005LL,
          cbSizea);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v250);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
        WindowsDeleteString(string);
        string = 0;
        if ( v211 )
        {
          v211 = 0;
          if ( *v207 )
            UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
        }
        wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v216);
        goto LABEL_446;
      }
      v190 = 1;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v250);
    }
    if ( v195 )
    {
      v148 = CClassData::AddDebugEnvironmentBlock((CClassData *)v143, v251, (unsigned __int16 *)v195, &lpEnvironment);
      LastError = v148;
      if ( v148 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD14,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)v148,
          cbSizea);
        goto LABEL_440;
      }
      if ( v251 != lpEnvironment )
        v253 = 1;
    }
    else
    {
      lpEnvironment = v251;
    }
    CClassData::FireAAMCreateProcessEvent(this, a9, v24, v292);
    if ( ProcessHandle.hProcess )
      wil::details::CloseHandle((wil::details *)ProcessHandle.hProcess, v149);
    if ( ProcessHandle.hThread )
      wil::details::CloseHandle((wil::details *)ProcessHandle.hThread, v149);
    v150 = dwCreationFlags;
    memset(&ProcessHandle, 0, sizeof(ProcessHandle));
    if ( !CreateProcessAsUserW(
            v24,
            *((LPCWSTR *)this + 5),
            lpCommandLine,
            &ProcessAttributes,
            0,
            0,
            dwCreationFlags,
            lpEnvironment,
            0,
            &StartupInfo,
            &ProcessHandle) )
    {
      LastError = wil::details::in1diag3::Return_GetLastErrorMsg(
                    retaddr,
                    (void *)0xD41,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                    "Failed CreateProcessAsUser",
                    cbSizeb);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
      WindowsDeleteString(string);
      string = 0;
      if ( v211 )
      {
        v211 = 0;
        lambda_67f6d9bfab93cea1a1c3904b0150db13_::operator()(&v207);
      }
      wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v216);
      goto LABEL_258;
    }
    RevertToSelf();
    v190 = 0;
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v273);
    v151 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v196);
    if ( !OpenProcessToken(ProcessHandle.hProcess, 8u, v151) )
    {
      v152 = GetLastError();
      MicrosoftTelemetryAssertTriggeredArgs("rpcss.dll", v152, 0);
      v153 = GetLastError();
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0xD4D,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)v153,
        (unsigned int)cbSizeb);
    }
    v235 = 0;
    if ( (char *)v196 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      ActivationActivityIfNeeded = CClassData::GetActivationActivityIfNeeded((__int64 *)this, v196, (__int64)&v235);
      LastError = ActivationActivityIfNeeded;
      if ( ActivationActivityIfNeeded < 0 )
      {
        v155 = 3413;
LABEL_484:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v155,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)ActivationActivityIfNeeded,
          (int)cbSizeb);
        goto LABEL_485;
      }
    }
    if ( v142 )
    {
      switch ( v142 )
      {
        case 1:
          goto LABEL_474;
        case 2:
        case 3:
          *((_DWORD *)v237 + 10) = v150;
          ActivationActivityIfNeeded = PostCreateProcessDesktopAppXActivation(v24, v237, &ProcessHandle);
          LastError = ActivationActivityIfNeeded;
          if ( ActivationActivityIfNeeded < 0 )
          {
            v155 = 3446;
            goto LABEL_484;
          }
          v166 = NtResumeThread(ProcessHandle.hThread, 0);
          if ( v166 < 0 )
          {
            LastError = wil::details::in1diag3::Return_NtStatus(
                          retaddr,
                          (void *)0xD77,
                          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                          (const char *)(unsigned int)v166,
                          (int)cbSizeb);
            wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
              &v235,
              0);
            WindowsDeleteString(string);
            string = 0;
            if ( v211 )
            {
              v211 = 0;
              v167 = *v207 == 0;
              goto LABEL_488;
            }
LABEL_490:
            wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v216);
            goto LABEL_491;
          }
          break;
        case 4:
LABEL_474:
          v156 = string;
          v157 = CClassData::IdentityType(this);
          v159 = CClassData::AppUserModelID(v158);
          v160 = CClassData::ExecutionPackageName(this);
          v161 = *((_QWORD *)this + 7);
          v162 = v193;
          v163 = a6;
          SessionId = CToken::GetSessionId(v222);
          LOBYTE(v165) = v224 == 4;
          LastError = PostCreateProcessUWPActivation(
                        v222,
                        *((unsigned int *)v279 + 33),
                        v165,
                        SessionId,
                        v163,
                        a10,
                        v162,
                        v161,
                        v160,
                        v159,
                        v157,
                        v156,
                        &ProcessHandle);
          if ( LastError < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0xD6D,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
              (const char *)(unsigned int)LastError,
              (int)"PostCreateProcessUWPActivation failed",
              lpPreviousValueb);
LABEL_485:
            wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
              &v235,
              0);
LABEL_486:
            WindowsDeleteString(string);
            string = 0;
            if ( v211 )
            {
              v211 = 0;
              v167 = *v207 == 0;
LABEL_488:
              if ( !v167 )
                UnmountVolumeForAppPackage(v208, *v209, *p_TokenInformation);
              goto LABEL_490;
            }
            goto LABEL_490;
          }
          break;
      }
    }
    else if ( v141 )
    {
      v238 = *((_DWORD *)this + 33);
      CClassData::IdentityType(this);
      CClassData::AppUserModelID(v168);
      CClassData::ExecutionPackageName(this);
      v169 = (int)v193;
      v170 = a6;
      v171 = CToken::GetSessionId(v222);
      LODWORD(cbSizeb) = v169;
      ActivationActivityIfNeeded = LaunchDebugger(v222, v171, v170, 0);
      LastError = ActivationActivityIfNeeded;
      if ( ActivationActivityIfNeeded < 0 )
      {
        v155 = 3427;
        goto LABEL_484;
      }
    }
    wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
      &v235,
      0);
    v211 = 0;
    wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
      &v235,
      0);
    WindowsDeleteString(string);
    string = 0;
    if ( v211 )
    {
      v211 = 0;
      lambda_67f6d9bfab93cea1a1c3904b0150db13_::operator()(&v207);
    }
    wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v216);
    hProcess = ProcessHandle.hProcess;
    dwProcessId = ProcessHandle.dwProcessId;
    hThread = ProcessHandle.hThread;
    memset(&ProcessHandle, 0, sizeof(ProcessHandle));
    *v265 = hProcess;
    v177 = v196;
    v196 = 0;
    *v266 = v177;
    *v267 = dwProcessId;
    CloseHandle(hThread);
    v254 = 1;
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
    v226 = 0;
    lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v225);
    if ( (char *)v196 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v196);
    if ( lpMem )
      HeapFree(g_hHeap, 0, lpMem);
    if ( v197 )
      LocalFree(v197);
    if ( v198 )
      LocalFree(v198);
    if ( v195 )
      LocalFree(v195);
    if ( v193 )
      LocalFree(v193);
    v179 = hMem;
    hMem = 0;
    if ( v179 )
      LocalFree(v179);
    if ( v230 )
      LocalFree(v230);
    if ( v223 )
      HeapFree(g_hHeap, 0, v223);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( ProcessHandle.hProcess )
      wil::details::CloseHandle((wil::details *)ProcessHandle.hProcess, v178);
    if ( ProcessHandle.hThread )
      wil::details::CloseHandle((wil::details *)ProcessHandle.hThread, v178);
    if ( lpCommandLine )
      HeapFree(g_hHeap, 0, lpCommandLine);
    return 0;
  }
  if ( *(_DWORD *)(v61 + 76) == 2 )
  {
    v60 = 1;
    v246 = 2;
    goto LABEL_90;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xABA,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
    (const char *)0x80070057LL,
    (int)cbSize);
LABEL_527:
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v233);
  if ( ProcessHandle.hProcess )
    NtTerminateProcess(ProcessHandle.hProcess, ExitStatus);
  v226 = 0;
  lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v225);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v196);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v197);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v198);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v195);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v193);
  v180 = hMem;
  hMem = 0;
  if ( v180 )
    LocalFree(v180);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v230);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v223);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
  wil::details::CloseProcessInformation((wil::details *)&ProcessHandle, v181);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpCommandLine);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18004cd64  mov     [rsp-8+arg_10], rbx
0x18004cd69  push    rbp
0x18004cd6a  push    rsi
0x18004cd6b  push    rdi
0x18004cd6c  push    r12
0x18004cd6e  push    r13
0x18004cd70  push    r14
0x18004cd72  push    r15
0x18004cd74  lea     rbp, [rsp-720h]
0x18004cd7c  sub     rsp, 820h
0x18004cd83  mov     rax, cs:__security_cookie
0x18004cd8a  xor     rax, rsp
0x18004cd8d  mov     [rbp+750h+var_40], rax
0x18004cd94  mov     rax, [rbp+750h+arg_30]
0x18004cd9b  mov     rdi, rcx
0x18004cd9e  mov     rbx, [rbp+750h+arg_50]
0x18004cda5  mov     r12, [rbp+750h+arg_A0]
0x18004cdac  mov     rsi, [rbp+750h+hToken]
0x18004cdb3  mov     r14, [rbp+750h+arg_70]
0x18004cdba  mov     r15, [rbp+750h+arg_78]
0x18004cdc1  mov     r13, [rbp+750h+arg_80]
0x18004cdc8  mov     [rbp+750h+var_4A0], rax
0x18004cdcf  mov     rax, [rbp+750h+arg_58]
0x18004cdd6  mov     [rbp+750h+var_570], rax
0x18004cddd  mov     rax, [rbp+750h+arg_68]
0x18004cde4  mov     [rbp+750h+var_490], rax
0x18004cdeb  mov     rax, [rbp+750h+arg_88]
0x18004cdf2  mov     [rbp+750h+var_568], rax
0x18004cdf9  mov     rax, [rbp+750h+arg_90]
0x18004ce00  mov     [rbp+750h+var_560], rax
0x18004ce07  mov     rax, [rbp+750h+arg_98]
0x18004ce0e  mov     [rbp+750h+var_558], rax
0x18004ce15  xor     eax, eax
0x18004ce17  mov     [rbp+750h+var_57C], r8d
0x18004ce1e  mov     [rbp+750h+var_498], rcx
0x18004ce25  lea     rcx, [rbp+750h+StartupInfo.lpReserved]; void *
0x18004ce2c  mov     [rbp+750h+var_710], rdx
0x18004ce30  xor     edx, edx; Val
0x18004ce32  lea     r8d, [rax+68h]; Size
0x18004ce36  mov     [rbp+750h+var_698], r9d
0x18004ce3d  mov     [rbp+750h+var_4D0], rbx
0x18004ce44  mov     [rbp+750h+var_588], r12
0x18004ce4b  mov     [rbp+750h+lpCommandLine], rax
0x18004ce52  mov     qword ptr [rbp+750h+StartupInfo.cb], rax
0x18004ce59  call    memset_0
0x18004ce5e  xor     ecx, ecx
0x18004ce60  xorps   xmm0, xmm0
0x18004ce63  xor     eax, eax
0x18004ce65  mov     [rbp+750h+hObject], rcx
0x18004ce69  movups  xmmword ptr [rbp+750h+ProcessHandle], xmm0
0x18004ce6d  mov     [rbp+750h+var_748], rax
0x18004ce71  movups  xmmword ptr [rbp+750h+ProcessAttributes.nLength], xmm0
0x18004ce78  mov     qword ptr [rbp+750h+ProcessAttributes.bInheritHandle], rax
0x18004ce7f  mov     [rbp+750h+var_708], rcx
0x18004ce83  mov     [rbp+750h+var_590], rcx
0x18004ce8a  mov     [rbp+750h+var_690], rcx
0x18004ce91  mov     [rbp+750h+packageFullName], rcx
0x18004ce98  mov     [rsp+850h+hMem], rcx
0x18004ce9d  call    cs:__imp_GetCurrentProcess
0x18004cea3  xor     edx, edx
0x18004cea5  mov     rcx, rdi; this
0x18004cea8  mov     [rbp+750h+var_4B0], rax
0x18004ceaf  mov     [rbp+750h+var_4A8], rdx
0x18004ceb6  mov     [rbp+750h+var_598], rdx
0x18004cebd  mov     [rbp+750h+var_7C0], rdx
0x18004cec1  mov     [rbp+750h+var_7B0], rdx
0x18004cec5  mov     [rbp+750h+var_798], rdx
0x18004cec9  mov     [rbp+750h+var_7A0], rdx
0x18004cecd  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x18004ced2  mov     [rbp+750h+var_628], eax
0x18004ced8  mov     [rbp+750h+var_718], dl
0x18004cedb  mov     [rbp+750h+var_78E], dl
0x18004cede  mov     [rbp+750h+var_630], rdx
0x18004cee5  call    ?IsInteractiveUser@CClassData@@QEAAHXZ; CClassData::IsInteractiveUser(void)
0x18004ceea  xor     edx, edx
0x18004ceec  test    eax, eax
0x18004ceee  jz      short loc_18004CF02
0x18004cef0  mov     rcx, rdi; this
0x18004cef3  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x18004cef8  mov     [rbp+750h+var_75F], 1
0x18004cefc  bt      eax, 0Ch
0x18004cf00  jb      short loc_18004CF05
0x18004cf02  mov     [rbp+750h+var_75F], dl
0x18004cf05  mov     r8d, 114h; Size
0x18004cf0b  lea     rcx, [rbp+750h+var_3C0]; void *
0x18004cf12  call    memset_0
0x18004cf17  xor     edx, edx; Val
0x18004cf19  lea     rcx, [rbp+750h+var_210]; void *
0x18004cf20  mov     r8d, 1D0h; Size
0x18004cf26  call    memset_0
0x18004cf2b  mov     rax, [rbp+750h+var_568]
0x18004cf32  lea     rdx, [rbp+750h+var_680]; struct wil::details::IFailureCallback *
0x18004cf39  xor     ecx, ecx
0x18004cf3b  mov     [rbp+750h+var_580], 1D0h
0x18004cf45  mov     [rbp+750h+lpMem], rcx
0x18004cf49  mov     [rbp+750h+var_7D0], cl
0x18004cf4c  mov     [rbp+750h+var_5B4], ecx
0x18004cf52  mov     [rbp+750h+var_7A8], rcx
0x18004cf56  mov     [rax], rcx
0x18004cf59  mov     rax, [rbp+750h+var_560]
0x18004cf60  mov     [rbp+750h+var_6B8], rdi
0x18004cf67  mov     [rax], rcx
0x18004cf6a  mov     rax, [rbp+750h+var_558]
0x18004cf71  mov     [rax], ecx
0x18004cf73  lea     rax, [rbp+750h+var_78E]
0x18004cf77  mov     [rbp+750h+var_6F0], rax
0x18004cf7b  lea     rax, [rbp+750h+packageFullName]
0x18004cf82  mov     [rbp+750h+var_6E8], rax
0x18004cf86  lea     rax, [rbp+750h+var_5B4]
0x18004cf8d  mov     [rbp+750h+var_6E0], rax
0x18004cf91  lea     rax, [rsp+850h+hMem]
0x18004cf96  mov     [rbp+750h+var_6D8], rax
0x18004cf9a  lea     rax, [rbp+750h+var_590]
0x18004cfa1  mov     [rbp+750h+var_6D0], rax
0x18004cfa8  lea     rax, [rbp+750h+var_630]
0x18004cfaf  mov     [r12], ecx
0x18004cfb3  xor     r12d, r12d
0x18004cfb6  mov     [rbp+750h+var_6C8], rax
0x18004cfbd  lea     rcx, [rbp+750h+var_678]; this
0x18004cfc4  lea     rax, [rsp+850h+ExitStatus]
0x18004cfc9  mov     [rsp+850h+ExitStatus], r12d
0x18004cfce  mov     [rbp+750h+var_6C0], rax
0x18004cfd5  lea     rax, [rbp+750h+var_7D0]
0x18004cfd9  mov     [rbp+750h+var_6B0], rax
0x18004cfe0  lea     rax, off_18010ECB0
0x18004cfe7  mov     [rbp+750h+var_680], rax
0x18004cfee  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18004cff3  lea     rax, [rsp+850h+ExitStatus]
0x18004cff8  mov     [rbp+750h+var_648], rax
0x18004cfff  test    rbx, rbx
0x18004d002  jz      short loc_18004D00A
0x18004d004  mov     [rbp+750h+var_78D], 1
0x18004d008  jmp     short loc_18004D035
0x18004d00a  mov     rcx, [rdi+58h]
0x18004d00e  mov     rax, rcx
0x18004d011  mov     [rbp+750h+var_78D], r12b
0x18004d015  neg     rax
0x18004d018  sbb     rax, rax
0x18004d01b  lea     rdx, [rcx+50h]
0x18004d01f  test    rdx, rax
0x18004d022  jz      short loc_18004D035
0x18004d024  neg     rcx
0x18004d027  sbb     rax, rax
0x18004d02a  and     rax, rdx
0x18004d02d  cmp     [rax+8], r12
0x18004d031  setnz   [rbp+750h+var_78D]
0x18004d035  mov     ebx, [rbp+750h+var_698]
0x18004d03b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18004d042  and     ebx, 4
0x18004d045  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18004d04a  test    al, al
0x18004d04c  jz      loc_18004D0F3
0x18004d052  test    ebx, ebx
0x18004d054  jz      loc_18004D11C
0x18004d05a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004d05f  mov     ebx, 8000FFFFh
0x18004d064  mov     edx, 9FEh; void *
0x18004d069  mov     r9d, ebx; char *
0x18004d06c  mov     rcx, [rbp+758h]; this
0x18004d073  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18004d07a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d07f  lea     rcx, [rbp+750h+var_678]; this
0x18004d086  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18004d08b  mov     rcx, [rbp+750h+ProcessHandle]; ProcessHandle
0x18004d08f  test    rcx, rcx
0x18004d092  jz      short loc_18004D09E
0x18004d094  mov     edx, [rsp+850h+ExitStatus]; ExitStatus
0x18004d098  call    cs:__imp_NtTerminateProcess
0x18004d09e  lea     rcx, [rbp+750h+var_6F0]
0x18004d0a2  mov     [rbp+750h+var_6A8], r12b
0x18004d0a9  call    _lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb___operator__
0x18004d0ae  lea     rcx, [rbp+750h+var_7A8]
0x18004d0b2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004d0b7  lea     rcx, [rbp+750h+lpMem]
0x18004d0bb  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@PEAVCClientOxid@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(void)
0x18004d0c0  lea     rcx, [rbp+750h+var_7A0]
0x18004d0c4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d0c9  lea     rcx, [rbp+750h+var_798]
0x18004d0cd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d0d2  lea     rcx, [rbp+750h+var_7B0]
0x18004d0d6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d0db  lea     rcx, [rbp+750h+var_7C0]
0x18004d0df  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d0e4  mov     rcx, [rsp+850h+hMem]
0x18004d0e9  mov     [rsp+850h+hMem], r12
0x18004d0ee  jmp     loc_18004D358
0x18004d0f3  test    ebx, ebx
0x18004d0f5  jz      short loc_18004D11C
0x18004d0f7  mov     rdx, [rbp+750h+var_710]; struct CToken *
0x18004d0fb  mov     r8d, 1; int
0x18004d101  mov     rcx, rdi; this
0x18004d104  call    ?PrivilegedLaunchIsActivateAsIUAllowedOld@CClassData@@QEAAJPEAVCToken@@H@Z; CClassData::PrivilegedLaunchIsActivateAsIUAllowedOld(CToken *,int)
0x18004d109  mov     ebx, eax
0x18004d10b  test    eax, eax
0x18004d10d  jns     short loc_18004D11C
0x18004d10f  mov     r9d, eax
0x18004d112  mov     edx, 0A04h
0x18004d117  jmp     loc_18004D06C
0x18004d11c  xor     ebx, ebx
0x18004d11e  test    r14, r14
0x18004d121  jnz     short loc_18004D13F
0x18004d123  test    r15, r15
0x18004d126  jnz     short loc_18004D13F
0x18004d128  test    r13, r13
0x18004d12b  jnz     short loc_18004D13F
0x18004d12d  mov     r13d, 410h
0x18004d133  mov     [rbp+750h+var_760], bl
0x18004d136  mov     [rbp+750h+dwCreationFlags], r13d
0x18004d13a  jmp     loc_18004D248
0x18004d13f  mov     rcx, rdi; this
0x18004d142  call    ?HasActivateAsPackage@CClassData@@QEBAHXZ; CClassData::HasActivateAsPackage(void)
0x18004d147  test    eax, eax
0x18004d149  jnz     loc_18004D1F0
0x18004d14f  mov     rcx, [rbp+758h]; this
0x18004d156  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18004d15d  mov     r9d, 80070005h; char *
0x18004d163  mov     edx, 0A0Bh; void *
0x18004d168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d16d  lea     rcx, [rbp+750h+var_678]; this
0x18004d174  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18004d179  mov     rcx, [rbp+750h+ProcessHandle]; ProcessHandle
0x18004d17d  test    rcx, rcx
0x18004d180  jz      short loc_18004D18C
0x18004d182  mov     edx, [rsp+850h+ExitStatus]; ExitStatus
0x18004d186  call    cs:__imp_NtTerminateProcess
0x18004d18c  lea     rcx, [rbp+750h+var_6F0]
0x18004d190  mov     [rbp+750h+var_6A8], bl
0x18004d196  call    _lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb___operator__
0x18004d19b  lea     rcx, [rbp+750h+var_7A8]
0x18004d19f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004d1a4  lea     rcx, [rbp+750h+lpMem]
0x18004d1a8  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@PEAVCClientOxid@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(void)
0x18004d1ad  lea     rcx, [rbp+750h+var_7A0]
0x18004d1b1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d1b6  lea     rcx, [rbp+750h+var_798]
0x18004d1ba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d1bf  lea     rcx, [rbp+750h+var_7B0]
0x18004d1c3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d1c8  lea     rcx, [rbp+750h+var_7C0]
0x18004d1cc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d1d1  mov     rcx, [rsp+850h+hMem]; hMem
0x18004d1d6  mov     [rsp+850h+hMem], rbx
0x18004d1db  test    rcx, rcx
0x18004d1de  jz      short loc_18004D1E6
0x18004d1e0  call    cs:__imp_LocalFree
0x18004d1e6  mov     ebx, 80070005h
0x18004d1eb  jmp     loc_18004F9A8
0x18004d1f0  lea     rax, [r14-1]
0x18004d1f4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004d1f8  ja      loc_18004FB8F
0x18004d1fe  lea     rax, [r15-1]
0x18004d202  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004d206  ja      loc_18004FB8F
0x18004d20c  lea     rax, [r13-1]
0x18004d210  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004d214  ja      loc_18004FB8F
0x18004d21a  bts     [rbp+750h+StartupInfo.dwFlags], 8
0x18004d222  mov     r12d, 400h
0x18004d228  mov     [rbp+750h+StartupInfo.hStdError], r13
0x18004d22f  mov     r13d, r12d
0x18004d232  mov     [rbp+750h+dwCreationFlags], r12d
0x18004d236  mov     [rbp+750h+StartupInfo.hStdInput], r14
0x18004d23d  mov     [rbp+750h+StartupInfo.hStdOutput], r15
0x18004d244  mov     [rbp+750h+var_760], 1
0x18004d248  mov     rcx, rdi; this
0x18004d24b  mov     [rbp+750h+var_78F], bl
0x18004d24e  mov     r12b, bl
0x18004d251  mov     [rbp+750h+var_789], bl
0x18004d254  mov     [rbp+750h+var_78A], bl
0x18004d257  mov     [rbp+750h+var_78B], bl
0x18004d25a  mov     [rbp+750h+var_78C], bl
0x18004d25d  mov     [rbp+750h+var_790], bl
0x18004d260  call    ?HasActivateAsPackage@CClassData@@QEBAHXZ; CClassData::HasActivateAsPackage(void)
0x18004d265  test    eax, eax
0x18004d267  jz      loc_18004D695
0x18004d26d  mov     rcx, rdi; this
0x18004d270  call    ?ExecutionPackageName@CClassData@@QEBAPEBGXZ; CClassData::ExecutionPackageName(void)
0x18004d275  mov     rcx, rdi
0x18004d278  mov     [rbp+750h+packageFullName], rax
0x18004d27f  call    ?GetRuntimeBehavior@CClassData@@QEBA?AW4RuntimeBehavior@AppModel@@XZ; CClassData::GetRuntimeBehavior(void)
0x18004d284  test    eax, eax
0x18004d286  jnz     loc_18004D387
0x18004d28c  call    IsPrepareExclusiveResourceForPackageActivationPresent
0x18004d291  test    al, al
0x18004d293  jz      loc_18004D379
0x18004d299  mov     ebx, [rdi+84h]
0x18004d29f  mov     rcx, rdi; this
0x18004d2a2  call    ?AppUserModelID@CClassData@@QEBAPEBGXZ; CClassData::AppUserModelID(void)
0x18004d2a7  mov     rcx, [rbp+750h+packageFullName]
0x18004d2ae  lea     r9, [rbp+750h+var_598]
0x18004d2b5  mov     r8d, ebx
0x18004d2b8  mov     rdx, rax
0x18004d2bb  call    cs:__imp_PrepareExclusiveResourceForPackageActivation
0x18004d2c1  xor     r14d, r14d
0x18004d2c4  mov     ebx, eax
0x18004d2c6  test    eax, eax
0x18004d2c8  jns     loc_18004D36C
0x18004d2ce  mov     edx, 0A4Dh; void *
0x18004d2d3  mov     rcx, [rbp+758h]; this
0x18004d2da  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
  ... truncated ...
```
