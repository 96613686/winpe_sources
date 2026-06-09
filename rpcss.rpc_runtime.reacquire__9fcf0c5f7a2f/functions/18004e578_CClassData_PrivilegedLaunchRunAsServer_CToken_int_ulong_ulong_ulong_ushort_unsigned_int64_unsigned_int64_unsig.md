# CClassData::PrivilegedLaunchRunAsServer(CToken *,int,ulong,ulong,ulong,ushort *,unsigned __int64,unsigned __int64,unsigned __int64,tagBLOB *,_GUID const *,void *,tagBLOB *,void *,void *,void *,void * *,void * *,ulong *,int *)

- ea: `0x18004e578`
- end: `0x180050fc8`
- name: `?PrivilegedLaunchRunAsServer@CClassData@@QEAAJPEAVCToken@@HKKKPEAG_K22PEAUtagBLOB@@PEBU_GUID@@PEAX3555PEAPEAX6PEAKPEAH@Z`
- size: `10832`
- prototype: `__int64 __usercall@<rax>(CClassData *__hidden this@<rcx>, struct CToken *@<rdx>, int@<r8d>, unsigned int@<r9d>, unsigned int TokenInformation, unsigned int, unsigned __int16 *, unsigned __int64, unsigned __int64, char *, struct tagBLOB *, const struct _GUID *, HANDLE hToken, struct tagBLOB *, void *, void *, void *, void **, void **, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `84`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a01ec`
- `0x1800a1540`

## callees

- `0x1800065a4`
- `0x180008b74`
- `0x180008c20`
- `0x18000902c`
- `0x18000a5bc`
- `0x18000a880`
- `0x18000b0c4`
- `0x18000b100`
- `0x18000b9e0`
- `0x18000c3f8`
- `0x18000c454`
- `0x18000c6fc`
- `0x18000ce5c`
- `0x18000ce7c`
- `0x18000fb8c`
- `0x180010e04`
- `0x180011db0`
- `0x1800210f8`
- `0x180022ddc`
- `0x180023da8`
- `0x180023dc4`
- `0x180024590`
- `0x180025088`
- `0x180025950`
- `0x180025b54`
- `0x18002ea40`
- `0x18002faa8`
- `0x1800375e0`
- `0x180039a7c`
- `0x18004c160`
- `0x18004c440`
- `0x18004dbf4`
- `0x18004dd1c`
- `0x18004dee8`
- `0x18004e554`
- `0x18004e578`
- `0x18005112c`
- `0x180051334`
- `0x180051378`
- `0x18005141c`
- `0x180051484`
- `0x1800516c0`
- `0x18005192c`
- `0x180051954`
- `0x180051a10`
- `0x18006bd64`
- `0x18006c3a4`
- `0x18006d3ec`
- `0x1800710a4`
- `0x180073ab8`

## import_xrefs

- `ntdll!NtResumeThread` at `0x180050a53`
- `ntdll!NtResumeThread` at `0x180050a53`
- `ntdll!NtTerminateProcess` at `0x18004fbfd`
- `ntdll!NtTerminateProcess` at `0x18005019b`
- `ntdll!NtTerminateProcess` at `0x1800506d6`
- `ntdll!NtTerminateProcess` at `0x180050be3`
- `ntdll!NtTerminateProcess` at `0x180050f05`
- `ntdll!NtTerminateProcess` at `0x18004fbfd`
- `ntdll!NtTerminateProcess` at `0x18005019b`
- `ntdll!NtTerminateProcess` at `0x1800506d6`
- `ntdll!NtTerminateProcess` at `0x180050be3`
- `ntdll!NtTerminateProcess` at `0x180050f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fc2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fd05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050d28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050d83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050e5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fc2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fd05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050d28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050d83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050e5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fa0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fbc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fc48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fceb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fd49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050da1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050e44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050e9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fa0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fbc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fc48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fceb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fd49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050da1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050e44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050e9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004f7b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004f7b0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180050895`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180050895`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004ef2f`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004efc2`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f036`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f07e`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f0c7`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f125`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f167`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f1a3`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f1e8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004ef2f`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004efc2`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f036`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f07e`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f0c7`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f125`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f167`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f1a3`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004f1e8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800507ef`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800507ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004e6ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004e6ad`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18004fb0d`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18004fb0d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004f339`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004f355`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004fde4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800502dc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180050614`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004f339`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004f355`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004fde4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800502dc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180050614`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004f36f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800502ca`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180050601`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180050861`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004f36f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800502ca`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180050601`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180050861`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004ebbe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004ebbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f8d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f98b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004faa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fb4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005009a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005031a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050a93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050b6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050caf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f8d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f98b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004faa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fb4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005009a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005031a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050a93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050b6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050caf`
- `KERNELBASE!PackageSidFromFamilyName` at `0x18004eb5d`
- `KERNELBASE!PackageSidFromFamilyName` at `0x18004eb5d`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18004eae3`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18004eae3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fc5d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fc72`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fc87`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fc9c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fcb5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fccd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050db6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050dcb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050de0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050df5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050e0e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050e26`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fc5d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fc72`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fc87`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fc9c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fcb5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004fccd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050db6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050dcb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050de0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050df5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050e0e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050e26`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x1800501eb`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x1800501eb`
- `profapi!__imp_CreateEnvBlock` at `0x18004f94a`
- `profapi!__imp_CreateEnvBlock` at `0x18004f94a`
- `profapi!__imp_DestroyEnvBlock` at `0x18004f9e6`
- `profapi!__imp_DestroyEnvBlock` at `0x18004fba2`
- `profapi!__imp_DestroyEnvBlock` at `0x18004f9e6`
- `profapi!__imp_DestroyEnvBlock` at `0x18004fba2`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x18004fa5c`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x18004fa5c`
- `ext-ms-win-core-app-package-volume-l1-1-0!MountVolumeForAppPackage` at `0x180050267`
- `ext-ms-win-core-app-package-volume-l1-1-0!MountVolumeForAppPackage` at `0x180050267`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18004f9c0`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18004fb80`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18005015c`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x180050697`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x180050ba4`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18004f9c0`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18004fb80`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18005015c`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x180050697`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x180050ba4`
- `ext-ms-win-core-xbrm-l1-1-0!PrepareExclusiveResourceForPackageActivation` at `0x18004e9e7`
- `ext-ms-win-core-xbrm-l1-1-0!PrepareExclusiveResourceForPackageActivation` at `0x18004e9e7`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x1800504bb`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x1800504bb`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x180050a2e`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x180050a2e`

## string_xrefs

- `0x18004e8c9`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004e914`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004eafa`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004eb74`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ebd5`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ec1b`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ecd6`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ed92`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ee34`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ef4d`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004efe5`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f4a9`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f537`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f693`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f74c`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004f967`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004fa73`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004fb28`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004fd95`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004fdca`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004fe45`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ff26`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005006a`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800500fd`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180050207`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800502a0`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800502f3`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800503a6`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180050468`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800505cd`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005062f`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005080d`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800508d5`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800509fc`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180050a6e`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180050b51`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180050eca`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ef46`: `Failed to add attribute (DCOMLaunch)`
- `0x18004efd7`: `Failed to add attribute (DCOMLaunch)`
- `0x180050806`: `Failed CreateProcessAsUser`
- `0x180050eb8`: `Invalid console handles specified (DCOMLaunch)`
- `0x18004f1f8`: `Failed to add attribute (PROC_THREAD_ATTRIBUTE_PROTECTION_LEVEL)`
- `0x1800509ed`: `PostCreateProcessUWPActivation failed`
- `0x1800508b4`: `rpcss.dll`

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
  unsigned __int8 v32; // r12
  struct wil::CallContextInfo *v33; // r8
  bool v34; // r9
  __int64 v35; // rcx
  unsigned int v36; // ebx
  __int64 v37; // rdx
  int IsActivateAsIUAllowedOld; // eax
  signed int LastError; // ebx
  __int64 v40; // r9
  int v41; // r13d
  __int64 v42; // rdx
  unsigned int v43; // ebx
  const unsigned __int16 *v44; // rax
  int v45; // r14d
  unsigned __int8 v46; // r15
  __int64 v47; // rax
  int v48; // ecx
  unsigned int v49; // eax
  signed int LastErrorMsg; // eax
  HANDLE hProcess; // rcx
  int v52; // eax
  const char *v53; // r9
  int v54; // eax
  int PackageProperties; // eax
  __int64 v56; // r14
  unsigned __int8 v57; // r13
  __int64 v58; // rax
  int v59; // eax
  int v60; // edx
  int v61; // ecx
  int v62; // edx
  int v63; // eax
  bool v64; // r12
  __int64 v65; // rdx
  const char *v66; // r9
  PVOID *v67; // rdx
  int v68; // ecx
  CClassData *v69; // rcx
  CClassData *v70; // rcx
  unsigned __int16 *v71; // rax
  void *v72; // rdx
  unsigned __int16 *v73; // r9
  __int64 v74; // rcx
  unsigned __int16 *v75; // r8
  unsigned __int16 *v76; // rax
  void *RunAsToken; // rax
  char *v78; // r13
  unsigned int v79; // ebx
  const unsigned __int16 *v80; // rdx
  void **v81; // r14
  bool v82; // si
  unsigned int v83; // ebx
  const unsigned __int16 *v84; // rdx
  void **v85; // rax
  int UserTokenWithPsmClaimsAdded; // eax
  __int64 *v87; // rcx
  CClassData *v88; // rcx
  void **v89; // rax
  int v90; // eax
  __int64 v91; // rcx
  __int64 v92; // rax
  __int64 v93; // rax
  void **v94; // rax
  int MediumRaisedCredUIToken; // eax
  WCHAR *lpDesktop; // rax
  void *v97; // rbx
  void *UserSid; // rax
  __int64 v99; // rdx
  _QWORD *v100; // r10
  HLOCAL v101; // rcx
  __int64 v102; // r8
  __int64 v103; // r9
  void (__fastcall *v104)(CClassData *, HSTRING *); // rbx
  int v105; // eax
  bool v106; // zf
  void **v107; // rax
  const char *v108; // r9
  const char *v109; // r9
  void *v110; // rdx
  LPPROC_THREAD_ATTRIBUTE_LIST v111; // rcx
  unsigned int v112; // r14d
  unsigned int v113; // r15d
  int IsPackageSideLoaded; // eax
  __int64 v115; // rdx
  __int64 v116; // rdx
  char v117; // r15
  void **v118; // rax
  const unsigned __int16 *v119; // rdx
  int v120; // eax
  __int64 *v121; // rcx
  void **v122; // rax
  const unsigned __int16 *v123; // rdx
  int v124; // eax
  void **v125; // rax
  int v126; // eax
  void *v127; // rax
  signed int KeyFromToken; // eax
  __int64 v129; // rdx
  bool v130; // zf
  unsigned __int64 v131; // r9
  __int64 v132; // rdx
  const unsigned __int16 *v133; // rcx
  void *v134; // r8
  char *v135; // r9
  int DebuggerInfo; // eax
  DWORD v137; // r13d
  unsigned __int8 v138; // r14
  int v139; // r15d
  unsigned __int64 v140; // rcx
  int v141; // eax
  void **v142; // rax
  int v143; // eax
  void *v144; // rdx
  void **v145; // rax
  DWORD v146; // eax
  DWORD v147; // eax
  int ActivationActivityIfNeeded; // eax
  __int64 v149; // rdx
  HSTRING v150; // r13
  int v151; // r12d
  CClassData *v152; // rcx
  const unsigned __int16 *v153; // r15
  const unsigned __int16 *v154; // rbx
  __int64 v155; // rdi
  HLOCAL v156; // rsi
  unsigned int v157; // r14d
  unsigned int SessionId; // eax
  __int64 v159; // r8
  NTSTATUS v160; // eax
  CClassData *v161; // rcx
  int v162; // esi
  unsigned int v163; // r14d
  unsigned int v164; // eax
  struct _PROCESS_INFORMATION *v165; // rdx
  struct ActivationActivity *v167; // rax
  struct ActivationActivity *v168; // rcx
  HANDLE v169; // rax
  DWORD dwProcessId; // edx
  HANDLE hThread; // rcx
  HANDLE v172; // rax
  void *v173; // rdx
  LPPROC_THREAD_ATTRIBUTE_LIST v174; // rcx
  struct _PROCESS_INFORMATION *v175; // rdx
  const char *cbSize; // [rsp+20h] [rbp-E0h]
  const char *cbSizea; // [rsp+20h] [rbp-E0h]
  const char *lpPreviousValue; // [rsp+28h] [rbp-D8h]
  const char *lpPreviousValuea; // [rsp+28h] [rbp-D8h]
  const char *lpPreviousValueb; // [rsp+28h] [rbp-D8h]
  bool v181; // [rsp+88h] [rbp-78h] BYREF
  bool v182[7]; // [rsp+89h] [rbp-77h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  bool v184; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 v185; // [rsp+99h] [rbp-67h]
  bool v186; // [rsp+9Ah] [rbp-66h] BYREF
  bool v187; // [rsp+9Bh] [rbp-65h]
  bool v188[4]; // [rsp+9Ch] [rbp-64h] BYREF
  char *v189; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v190; // [rsp+A8h] [rbp-58h]
  LPVOID *v191; // [rsp+B0h] [rbp-50h]
  unsigned int *p_TokenInformation; // [rsp+B8h] [rbp-48h]
  char v193; // [rsp+C0h] [rbp-40h]
  char v194; // [rsp+C8h] [rbp-38h]
  char v195; // [rsp+C9h] [rbp-37h]
  HANDLE InAccessToken; // [rsp+D0h] [rbp-30h] BYREF
  char v197; // [rsp+D8h] [rbp-28h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+E0h] [rbp-20h] BYREF
  int v199; // [rsp+E8h] [rbp-18h]
  CToken *v200; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID v201; // [rsp+F8h] [rbp-8h] BYREF
  int v202; // [rsp+100h] [rbp+0h]
  LPVOID lpMem; // [rsp+108h] [rbp+8h] BYREF
  HLOCAL v204; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 **v205; // [rsp+118h] [rbp+18h] BYREF
  int *v206; // [rsp+120h] [rbp+20h]
  unsigned __int16 **p_lpEnvironment; // [rsp+128h] [rbp+28h]
  char v208; // [rsp+130h] [rbp+30h]
  struct ActivationActivity *v209; // [rsp+138h] [rbp+38h] BYREF
  LPWSTR lpCommandLine; // [rsp+140h] [rbp+40h] BYREF
  int Value; // [rsp+148h] [rbp+48h] BYREF
  unsigned int v212; // [rsp+14Ch] [rbp+4Ch]
  HLOCAL v213; // [rsp+150h] [rbp+50h] BYREF
  HLOCAL v214; // [rsp+158h] [rbp+58h] BYREF
  HANDLE hObject; // [rsp+160h] [rbp+60h] BYREF
  HLOCAL hMem; // [rsp+168h] [rbp+68h] BYREF
  PCWSTR packageFullName; // [rsp+170h] [rbp+70h] BYREF
  __int64 (__fastcall **v218)(); // [rsp+180h] [rbp+80h] BYREF
  _BYTE v219[48]; // [rsp+188h] [rbp+88h] BYREF
  NTSTATUS *v220; // [rsp+1B8h] [rbp+B8h]
  HLOCAL v221; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+1C8h] [rbp+C8h] BYREF
  NTSTATUS v223; // [rsp+1E0h] [rbp+E0h] BYREF
  PSID Sid; // [rsp+1E8h] [rbp+E8h] BYREF
  struct DESKTOP_APPX_LAUNCH_CONTEXT *v225; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned int v226; // [rsp+1F8h] [rbp+F8h]
  LPWSTR StringSid; // [rsp+200h] [rbp+100h] BYREF
  __int64 v228; // [rsp+208h] [rbp+108h]
  __int64 v229; // [rsp+210h] [rbp+110h]
  __int64 v230; // [rsp+218h] [rbp+118h]
  __int64 v231; // [rsp+220h] [rbp+120h]
  int v232; // [rsp+228h] [rbp+128h] BYREF
  int v233; // [rsp+22Ch] [rbp+12Ch] BYREF
  __int64 v234; // [rsp+230h] [rbp+130h] BYREF
  __int64 v235; // [rsp+238h] [rbp+138h] BYREF
  __int64 v236; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 *v237; // [rsp+248h] [rbp+148h] BYREF
  unsigned __int16 *lpEnvironment; // [rsp+250h] [rbp+150h] BYREF
  int v239; // [rsp+258h] [rbp+158h] BYREF
  int v240; // [rsp+25Ch] [rbp+15Ch] BYREF
  __int64 v241; // [rsp+260h] [rbp+160h] BYREF
  __int64 v242; // [rsp+268h] [rbp+168h] BYREF
  __int64 v243; // [rsp+270h] [rbp+170h] BYREF
  __int64 v244; // [rsp+278h] [rbp+178h] BYREF
  __int64 v245; // [rsp+280h] [rbp+180h] BYREF
  int *v246; // [rsp+288h] [rbp+188h]
  __int64 v247; // [rsp+290h] [rbp+190h] BYREF
  _QWORD *v248; // [rsp+298h] [rbp+198h] BYREF
  int v249; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v250; // [rsp+2A4h] [rbp+1A4h]
  UINT32 packageFamilyNameLength; // [rsp+2A8h] [rbp+1A8h] BYREF
  _QWORD *v252; // [rsp+2B0h] [rbp+1B0h] BYREF
  struct _GUID *v253; // [rsp+2B8h] [rbp+1B8h]
  void **v254; // [rsp+2C0h] [rbp+1C0h]
  void **v255; // [rsp+2C8h] [rbp+1C8h]
  unsigned int *v256; // [rsp+2D0h] [rbp+1D0h]
  LPPROC_THREAD_ATTRIBUTE_LIST *p_lpAttributeList; // [rsp+2D8h] [rbp+1D8h]
  struct _PROC_THREAD_ATTRIBUTE_LIST *v258; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v259; // [rsp+2E8h] [rbp+1E8h]
  char v260[8]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v261[88]; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int64 v262; // [rsp+350h] [rbp+250h] BYREF
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+358h] [rbp+258h] BYREF
  unsigned __int16 *v264; // [rsp+370h] [rbp+270h]
  struct tagBLOB *v265; // [rsp+378h] [rbp+278h]
  CClassData *v266; // [rsp+380h] [rbp+280h]
  struct tagBLOB *v267; // [rsp+388h] [rbp+288h]
  HANDLE v268[2]; // [rsp+390h] [rbp+290h] BYREF
  _QWORD v269[9]; // [rsp+3A0h] [rbp+2A0h] BYREF
  char v270; // [rsp+3E8h] [rbp+2E8h]
  _QWORD v271[6]; // [rsp+3F0h] [rbp+2F0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+420h] [rbp+320h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v273; // [rsp+488h] [rbp+388h]
  HSTRING *p_string; // [rsp+490h] [rbp+390h]
  unsigned int *v275; // [rsp+498h] [rbp+398h]
  CToken **v276; // [rsp+4A0h] [rbp+3A0h]
  LPWSTR *p_lpCommandLine; // [rsp+4A8h] [rbp+3A8h]
  CClassData *v278; // [rsp+4B0h] [rbp+3B0h]
  int v279; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v280[142]; // [rsp+4C4h] [rbp+3C4h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int16 v282[232]; // [rsp+670h] [rbp+570h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+888h] [rbp+788h]

  v22 = a11;
  v23 = a21;
  v24 = hToken;
  v25 = a15;
  v26 = a16;
  v27 = a17;
  v264 = a7;
  v253 = a12;
  v267 = a14;
  v254 = a18;
  v255 = a19;
  v256 = a20;
  v250 = a3;
  v266 = this;
  v200 = a2;
  v212 = a4;
  v265 = a11;
  v246 = a21;
  lpCommandLine = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  InAccessToken = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
  v201 = 0;
  v248 = 0;
  v221 = 0;
  packageFullName = 0;
  lpAttributeList = 0;
  v268[0] = GetCurrentProcess();
  v262 = 0;
  v247 = 0;
  v204 = 0;
  v214 = 0;
  v213 = 0;
  hMem = 0;
  v226 = CClassData::AppIDFlags(this);
  v197 = (char)v28;
  v186 = (char)v28;
  v225 = v28;
  IsInteractiveUser = CClassData::IsInteractiveUser(v29);
  v31 = 0;
  if ( !IsInteractiveUser || (v195 = 1, (CClassData::AppIDFlags(this) & 0x1000) == 0) )
    v195 = v31;
  memset_0(&v279, v31, 0x114u);
  memset_0(v282, 0, sizeof(v282));
  v249 = 464;
  lpMem = 0;
  v181 = 0;
  v239 = 0;
  hObject = 0;
  *v254 = 0;
  v269[7] = this;
  *v255 = 0;
  *v256 = 0;
  v269[0] = &v186;
  v269[1] = &packageFullName;
  v269[2] = &v239;
  v269[3] = &lpAttributeList;
  *v23 = 0;
  v32 = 0;
  v269[4] = &v248;
  v223 = 0;
  v269[5] = &v225;
  v269[6] = &v223;
  v269[8] = &v181;
  v218 = off_180117CA8;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v219,
    (struct wil::details::IFailureCallback *)&v218,
    v33,
    v34);
  v220 = &v223;
  if ( v22 )
  {
    v187 = 1;
  }
  else
  {
    v35 = *((_QWORD *)this + 11);
    v187 = 0;
    if ( (-(__int64)(v35 != 0) & (v35 + 80)) != 0 )
      v187 = *(_QWORD *)(((v35 + 80) & -(__int64)(v35 != 0)) + 8) != 0;
  }
  v36 = v212 & 4;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    if ( v36 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v37 = 2558;
LABEL_36:
      LastError = -2147418113;
      v40 = 2147549183LL;
      goto LABEL_63;
    }
  }
  else if ( v36 )
  {
    IsActivateAsIUAllowedOld = CClassData::PrivilegedLaunchIsActivateAsIUAllowedOld(this, v200, 1);
    LastError = IsActivateAsIUAllowedOld;
    if ( IsActivateAsIUAllowedOld < 0 )
    {
      v37 = 2564;
LABEL_14:
      v40 = (unsigned int)IsActivateAsIUAllowedOld;
LABEL_63:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)v40,
        (int)cbSize);
      goto LABEL_420;
    }
  }
  if ( v25 || v26 || v27 )
  {
    if ( !(unsigned int)CClassData::HasActivateAsPackage(this) )
    {
      v42 = 2571;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)0x80070005LL,
        (int)cbSize);
LABEL_374:
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v219);
      if ( ProcessInformation.hProcess )
        NtTerminateProcess(ProcessInformation.hProcess, v223);
      LastError = -2147024891;
      goto LABEL_424;
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
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v219);
      goto LABEL_460;
    }
    StartupInfo.dwFlags |= 0x100u;
    StartupInfo.hStdError = v27;
    v41 = 1024;
    v199 = 1024;
    StartupInfo.hStdInput = v25;
    StartupInfo.hStdOutput = v26;
    v194 = 1;
  }
  else
  {
    v41 = 1040;
    v194 = 0;
    v199 = 1040;
  }
  v185 = 0;
  v188[3] = 0;
  v188[2] = 0;
  v188[1] = 0;
  v188[0] = 0;
  v184 = 0;
  if ( (unsigned int)CClassData::HasActivateAsPackage(this) )
  {
    packageFullName = CClassData::ExecutionPackageName(this);
    if ( (unsigned int)CClassData::GetRuntimeBehavior(this) )
    {
      if ( (unsigned int)CClassData::GetRuntimeBehavior(this) != 1
        && (unsigned int)CClassData::GetRuntimeBehavior(this) != 3 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v37 = 2653;
        goto LABEL_36;
      }
      v46 = 1;
      v45 = 2;
      v32 = 1;
    }
    else
    {
      if ( (unsigned __int8)IsPrepareExclusiveResourceForPackageActivationPresent() )
      {
        v43 = *((_DWORD *)this + 33);
        v44 = CClassData::AppUserModelID(this);
        IsActivateAsIUAllowedOld = PrepareExclusiveResourceForPackageActivation(packageFullName, v44, v43, &v247);
        LastError = IsActivateAsIUAllowedOld;
        if ( IsActivateAsIUAllowedOld < 0 )
        {
          v37 = 2637;
          goto LABEL_14;
        }
        v186 = v247 != 0;
      }
      v45 = 1;
      v46 = 1;
    }
    v202 = v45;
    if ( !(unsigned int)CClassData::HasActivateAsPackage(this) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v47 = *((_QWORD *)this + 12);
    if ( v47 )
      v48 = *(_DWORD *)(v47 + 252);
    else
      v48 = *(_DWORD *)(*((_QWORD *)this + 11) + 300LL);
    if ( v48 == 1 && CClassData::GetAppTrustLevel(this) == PartialTrust )
    {
      if ( CClassData::GetAppTrustLevel(this) == PartialTrust )
      {
        memset_0(packageFamilyName, 0, 0x82u);
        packageFamilyNameLength = 65;
        v49 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
        if ( v49 )
        {
          LastErrorMsg = wil::details::in1diag3::Return_Win32(
                           retaddr,
                           (void *)0xA66,
                           (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                           (const char *)v49,
                           (unsigned int)cbSize);
LABEL_48:
          LastError = LastErrorMsg;
LABEL_49:
          wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v219);
LABEL_50:
          hProcess = ProcessInformation.hProcess;
LABEL_422:
          if ( hProcess )
            NtTerminateProcess(hProcess, v223);
LABEL_424:
          v270 = 0;
          lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v269);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
          utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v213);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v214);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v204);
          wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
            &lpAttributeList,
            0);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v221);
          utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v201);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&InAccessToken);
          wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v165);
          utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpCommandLine);
          return (unsigned int)LastError;
        }
        Sid = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &Sid,
          0);
        v52 = PackageSidFromFamilyName(packageFamilyName, &Sid);
        if ( v52 < 0 )
        {
          LastError = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0xA68,
                        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                        (const char *)(unsigned int)v52,
                        (int)cbSize);
LABEL_53:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
          goto LABEL_49;
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
                        v53);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          goto LABEL_53;
        }
        v54 = StringCchCopyW(v280, 0x88u, StringSid);
        LastError = v54;
        if ( v54 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA6B,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)v54,
            (int)cbSize);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
          goto LABEL_420;
        }
        v279 = 1;
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
      PackageProperties = GetPackageProperties(packageFullName, &v188[3], &v188[2], &v188[1], v188, &v184);
      LastError = PackageProperties;
      if ( PackageProperties < 0 )
      {
        v40 = (unsigned int)PackageProperties;
        v37 = 2678;
        goto LABEL_63;
      }
      if ( v184 && CClassData::IsSystemSurrogateServer(this) )
        v185 = 1;
    }
  }
  else
  {
    v46 = 0;
    v202 = 0;
    if ( !v195 )
      goto LABEL_76;
    v182[0] = 0;
    IsActivateAsIUAllowedOld = CToken::HasSysAppId(v200, v182);
    LastError = IsActivateAsIUAllowedOld;
    if ( IsActivateAsIUAllowedOld < 0 )
    {
      v37 = 2696;
      goto LABEL_14;
    }
    if ( !v182[0] )
      goto LABEL_76;
    v45 = (unsigned __int8)IsPrepareExclusiveResourceForPackageActivationPresent() == 0 ? 4 : 0;
    v202 = v45;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpMem,
      0);
    LastError = GetPackageNameFromToken(*((void **)v200 + 9), (unsigned __int16 **)&lpMem);
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xAA0,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)(unsigned int)LastError,
        (int)"Failed GetPackageName",
        lpPreviousValue);
      goto LABEL_420;
    }
  }
  if ( (unsigned int)(v45 - 1) <= 1 || (v202 = v45, v45 == 4) )
    v199 = v41 | 4;
LABEL_76:
  StartupInfo.cb = 112;
  v56 = -1;
  v232 = 0;
  v57 = 0;
  v58 = *((_QWORD *)this + 11);
  if ( !v58 || *(_DWORD *)(v58 + 76) == -1 )
  {
LABEL_80:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchHosts>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchHosts>::GetImpl'::`2'::impl) )
    {
      if ( v32 || (v59 = 0, v185) )
        v59 = 1;
      v60 = v46 + v59;
    }
    else
    {
      v60 = v46 + v32;
    }
    v61 = v60 + v187 + v186;
    if ( v194 )
    {
      v62 = 1;
      ++v61;
    }
    else
    {
      v62 = 0;
    }
    v258 = 0;
    v259 = 1;
    p_lpAttributeList = &lpAttributeList;
    LastError = InitializeAttributeList((v279 != 0) + v62 + (unsigned int)v57 + v61, v267, &v258);
    if ( v259 )
      wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        p_lpAttributeList,
        v258);
    if ( LastError < 0 )
    {
      v40 = (unsigned int)LastError;
      v37 = 2814;
      goto LABEL_63;
    }
    if ( v46 )
    {
      do
        ++v56;
      while ( packageFullName[v56] );
      if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20008u, (PVOID)packageFullName, 2 * v56, 0, 0) )
      {
        LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                         retaddr,
                         (void *)0xB05,
                         (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                         "Failed to add attribute (DCOMLaunch)",
                         cbSize);
        goto LABEL_48;
      }
    }
    Value = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchHosts>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchHosts>::GetImpl'::`2'::impl) )
    {
      if ( v32 || v185 )
      {
        v63 = v32;
        v64 = 0;
        Value = (4 * v63) | (8 * v185);
        if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20012u, &Value, 4u, 0, 0) )
        {
          v65 = 2836;
LABEL_103:
          v66 = "Failed to add attribute (DCOMLaunch)";
LABEL_104:
          LastError = wil::details::in1diag3::Return_GetLastErrorMsg(
                        retaddr,
                        (void *)v65,
                        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                        v66,
                        cbSize);
          wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v219);
          goto LABEL_50;
        }
        goto LABEL_109;
      }
    }
    else
    {
      Value = 4;
      if ( v32 )
      {
        v64 = 0;
        if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20012u, &Value, 4u, 0, 0) )
        {
          v65 = 2846;
          goto LABEL_103;
        }
LABEL_109:
        if ( v186 && !UpdateProcThreadAttribute(lpAttributeList, 0, 0x2000Du, &v247, 8u, 0, 0) )
        {
          v65 = 2854;
          goto LABEL_103;
        }
        if ( v279 && !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20013u, &v279, 0x114u, 0, 0) )
        {
          v65 = 2860;
          goto LABEL_103;
        }
        if ( v187 )
        {
          v67 = (PVOID *)v265;
          if ( !v265 )
            v67 = (PVOID *)((*((_QWORD *)this + 11) + 80LL)
                          & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this + 11) >> 64));
          if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20007u, v67[1], *(unsigned int *)v67, 0, 0) )
          {
            v65 = 2870;
            goto LABEL_103;
          }
        }
        if ( v194 )
        {
          if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20000u, v268, 8u, 0, 0) )
          {
            v65 = 2876;
            goto LABEL_103;
          }
          if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x2000Au, &v262, 8u, 0, 0) )
          {
            v65 = 2882;
            goto LABEL_103;
          }
        }
        if ( v57 )
        {
          if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x2000Bu, &v232, 4u, 0, 0) )
          {
            v66 = "Failed to add attribute (PROC_THREAD_ATTRIBUTE_PROTECTION_LEVEL)";
            v65 = 2888;
            goto LABEL_104;
          }
          v68 = v199 | 0x40000;
          v199 |= 0x40000u;
        }
        else
        {
          v68 = v199;
        }
        if ( lpAttributeList )
        {
          v273 = lpAttributeList;
          v199 = v68 | 0x80000;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &lpCommandLine,
          0);
        IsActivateAsIUAllowedOld = CClassData::GetLaunchCommandLine(this, &lpCommandLine);
        LastError = IsActivateAsIUAllowedOld;
        if ( IsActivateAsIUAllowedOld < 0 )
        {
          v37 = 2904;
          goto LABEL_14;
        }
        if ( *((_BYTE *)this + 80) == 3 )
          StartupInfo.lpTitle = 0;
        else
          StartupInfo.lpTitle = (LPWSTR)*((_QWORD *)this + 2);
        StartupInfo.dwFlags |= 0x80u;
        if ( !(unsigned int)CClassData::IsInteractiveUser(this) && !(unsigned int)CClassData::HasActivateAsPackage(this) )
        {
          CClassData::AppIDFlags(this);
          CClassData::RunAsUser(v69);
          v71 = CClassData::RunAsDomain(v70);
          v74 = *((_QWORD *)this + 11);
          v75 = v71;
          if ( v74 )
            v76 = (unsigned __int16 *)(v74 + 118);
          else
            v76 = CClassData::WinRTServerName(this);
          RunAsToken = GetRunAsToken(a6, v76, v75, v73, 1, v72);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &InAccessToken,
            RunAsToken);
          v24 = InAccessToken;
          v78 = a10;
LABEL_194:
          if ( !v24 )
          {
            LastError = -2147467238;
            v37 = 3063;
            v40 = 2147500058LL;
            goto LABEL_63;
          }
          v97 = 0;
          if ( !(unsigned int)CClassData::HasActivateAsPackage(this) )
          {
            UserSid = GetUserSid(v24);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
              &v201,
              UserSid);
            if ( !v201 )
            {
              v99 = 3072;
LABEL_199:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v99,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)0x8007000ELL,
                (int)cbSize);
LABEL_310:
              wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v219);
              if ( ProcessInformation.hProcess )
                NtTerminateProcess(ProcessInformation.hProcess, v223);
              LastError = -2147024882;
              goto LABEL_424;
            }
            if ( (CClassData::AppIDFlags(this) & 2) != 0 )
            {
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                &v221,
                0);
              IsActivateAsIUAllowedOld = CToken::GetLogonIDSid(v24, &v221);
              LastError = IsActivateAsIUAllowedOld;
              if ( IsActivateAsIUAllowedOld < 0 )
              {
                v37 = 3075;
                goto LABEL_14;
              }
              LODWORD(v97) = 1;
            }
            v100 = HeapAlloc(g_hHeap, 0, 0xA0u);
            if ( !v100 )
            {
              v248 = 0;
              v99 = 3080;
              goto LABEL_199;
            }
            v101 = v221;
            *v100 = v201;
            v100[1] = v101;
            v100[2] = 0;
            v100[3] = 0;
            v100[4] = 0;
            v100[5] = 0;
            v248 = v100;
            if ( (_DWORD)v97 )
            {
              v102 = 0x1FFFFF;
              v103 = 0;
            }
            else
            {
              v102 = 0;
              v103 = 0x1FFFFF;
            }
            LODWORD(cbSize) = 0;
            v97 = (void *)CAccessInfo::IdentifyAccess(v100, (_DWORD)v97 != 0 ? 3 : 0, v102, v103);
            if ( !v97 )
            {
              v99 = 3087;
              goto LABEL_199;
            }
          }
          ProcessAttributes.nLength = 24;
          v205 = &v237;
          ProcessAttributes.lpSecurityDescriptor = v97;
          v206 = &v240;
          p_lpEnvironment = &lpEnvironment;
          v189 = &v197;
          v190 = v282;
          v191 = &v201;
          p_TokenInformation = &TokenInformation;
          ProcessAttributes.bInheritHandle = 0;
          v237 = 0;
          lpEnvironment = 0;
          v240 = 0;
          v208 = 1;
          v193 = 1;
          string = 0;
          v104 = *(void (__fastcall **)(CClassData *, HSTRING *))(*(_QWORD *)this + 80LL);
          WindowsDeleteString(0);
          string = 0;
          v104(this, &string);
          v278 = this;
          p_string = &string;
          v275 = &a6;
          v276 = &v200;
          p_lpCommandLine = &lpCommandLine;
          wil::ThreadFailureCallback__lambda_4f8fe278ca1d0cbd6998976ea4d86a7e___((struct wil::details::IFailureCallback *)v260);
          v105 = CreateEnvBlock(&v237, v24, 0);
          LastError = v105;
          if ( v105 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC3E,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
              (const char *)(unsigned int)v105,
              (int)cbSize);
            wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
            WindowsDeleteString(string);
            string = 0;
            if ( v193 )
            {
              v193 = 0;
              v106 = *v189 == 0;
              goto LABEL_214;
            }
            goto LABEL_216;
          }
          if ( *((_QWORD *)this + 7) && (unsigned __int8)IsSaferCloseLevelPresent() )
          {
            v242 = 0;
            v107 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v242);
            if ( !SaferComputeTokenFromLevel(*((SAFER_LEVEL_HANDLE *)this + 7), v24, v107, 0, 0) )
            {
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0xC43,
                            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                            v108);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v242);
              wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
              WindowsDeleteString(string);
              string = 0;
              if ( v193 )
              {
                v193 = 0;
                v106 = *v189 == 0;
LABEL_214:
                if ( !v106 )
                  UnmountVolumeForAppPackage(v190, *v191, *p_TokenInformation);
              }
LABEL_216:
              if ( v208 )
              {
                v208 = 0;
                if ( *v205 )
                  DestroyEnvBlock();
                if ( *v206 )
                  HeapFree(g_hHeap, 0, *p_lpEnvironment);
              }
              goto LABEL_420;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
              &InAccessToken,
              &v242);
            v24 = InAccessToken;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v242);
          }
          if ( TokenInformation && !SetTokenInformation(v24, TokenSessionId, &TokenInformation, 4u) )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0xC4B,
                          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                          v109);
            wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
            WindowsDeleteString(string);
            string = 0;
            if ( v193 )
            {
              v193 = 0;
              if ( *v189 )
                UnmountVolumeForAppPackage(v190, *v191, *p_TokenInformation);
            }
            if ( v208 )
            {
              v208 = 0;
              if ( *v205 )
                DestroyEnvBlock();
              if ( *v206 )
                HeapFree(g_hHeap, 0, *p_lpEnvironment);
            }
LABEL_237:
            wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v219);
            if ( ProcessInformation.hProcess )
              NtTerminateProcess(ProcessInformation.hProcess, v223);
            v270 = 0;
            lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v269);
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
            if ( lpMem )
              HeapFree(g_hHeap, 0, lpMem);
            if ( hMem )
              LocalFree(hMem);
            if ( v213 )
              LocalFree(v213);
            if ( v214 )
              LocalFree(v214);
            if ( v204 )
              LocalFree(v204);
            v111 = lpAttributeList;
            lpAttributeList = 0;
            if ( v111 )
              LocalFree(v111);
            if ( v221 )
              LocalFree(v221);
            if ( v201 )
              HeapFree(g_hHeap, 0, v201);
            if ( (char *)InAccessToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(InAccessToken);
            if ( ProcessInformation.hProcess )
              wil::details::CloseHandle((wil::details *)ProcessInformation.hProcess, v110);
            if ( ProcessInformation.hThread )
              wil::details::CloseHandle((wil::details *)ProcessInformation.hThread, v110);
            if ( lpCommandLine )
              HeapFree(g_hHeap, 0, lpCommandLine);
            return (unsigned int)LastError;
          }
          v112 = v212 & 0x10;
          v113 = v212 & 2;
          if ( (v212 & 2) != 0 || (v212 & 0x10) != 0 )
          {
            v233 = 0;
            IsPackageSideLoaded = IsDeveloperLicenseInstalled(&v233);
            LastError = IsPackageSideLoaded;
            if ( IsPackageSideLoaded < 0 )
            {
              v115 = 3154;
LABEL_270:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v115,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)(unsigned int)IsPackageSideLoaded,
                (int)cbSize);
LABEL_271:
              wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
LABEL_414:
              WindowsDeleteString(string);
LABEL_415:
              string = 0;
              if ( v193 )
              {
                v193 = 0;
                v130 = *v189 == 0;
LABEL_417:
                if ( !v130 )
                  UnmountVolumeForAppPackage(v190, *v191, *p_TokenInformation);
                goto LABEL_419;
              }
              goto LABEL_419;
            }
            if ( !v233 )
            {
              v116 = 3155;
LABEL_274:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v116,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)0x80070005LL,
                (int)cbSize);
LABEL_369:
              wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
              WindowsDeleteString(string);
LABEL_370:
              string = 0;
              if ( v193 )
              {
                v193 = 0;
                if ( *v189 )
                  UnmountVolumeForAppPackage(v190, *v191, *p_TokenInformation);
              }
              wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v205);
              goto LABEL_374;
            }
          }
          ImpersonateLoggedOnUser(v24);
          v181 = 1;
          if ( v113 || (v117 = 0, v112) )
          {
            v243 = 0;
            v118 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v243);
            v119 = L"WIN://DESIGN_MODE_V2";
            if ( !v112 )
              v119 = L"WIN://DESIGN_MODE";
            v120 = DuplicateAndSetTokenBooleanClaim(v24, v119, v118);
            LastError = v120;
            if ( v120 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC6D,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)(unsigned int)v120,
                (int)cbSize);
              v121 = &v243;
LABEL_281:
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v121);
              goto LABEL_271;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
              &InAccessToken,
              &v243);
            v24 = InAccessToken;
            v117 = 1;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v243);
          }
          if ( (v226 & 0x80u) != 0 )
          {
            v182[0] = 0;
            IsPackageSideLoaded = CToken::IsPackageSideLoaded(v200, v182);
            LastError = IsPackageSideLoaded;
            if ( IsPackageSideLoaded < 0 )
            {
              v115 = 3190;
              goto LABEL_270;
            }
            if ( !v182[0] )
            {
              v116 = 3191;
              goto LABEL_274;
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &lpMem,
              0);
            IsPackageSideLoaded = GetPackageNameFromToken(*((void **)v200 + 9), (unsigned __int16 **)&lpMem);
            LastError = IsPackageSideLoaded;
            if ( IsPackageSideLoaded < 0 )
            {
              v115 = 3195;
              goto LABEL_270;
            }
            v244 = 0;
            v122 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v244);
            v124 = DuplicateAndSetTokenStringClaim(v24, v123, (const unsigned __int16 *)lpMem, v122);
            LastError = v124;
            if ( v124 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC7F,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)(unsigned int)v124,
                (int)cbSize);
              v121 = &v244;
              goto LABEL_281;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
              &InAccessToken,
              &v244);
            v24 = InAccessToken;
            v117 = 1;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v244);
          }
          v182[0] = 0;
          if ( (unsigned int)CClassData::HasActivateAsPackage(this) && (unsigned __int8)IsPsmCreateBrokerTokenPresent() )
          {
            IsPackageSideLoaded = CClassData::IsPpleClass(this, v182);
            LastError = IsPackageSideLoaded;
            if ( IsPackageSideLoaded < 0 )
            {
              v115 = 3210;
              goto LABEL_270;
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchHosts>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchHosts>::GetImpl'::`2'::impl) )
            {
              IsPackageSideLoaded = GetPackageProperties(packageFullName, &v188[3], &v188[2], &v188[1], v188, &v184);
              LastError = IsPackageSideLoaded;
              if ( IsPackageSideLoaded < 0 )
              {
                v115 = 3214;
                goto LABEL_270;
              }
            }
            v245 = 0;
            v125 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v245);
            v64 = v182[0];
            v126 = CClassData::AdjustActivationToken(
                     this,
                     v24,
                     v212,
                     a8,
                     v253,
                     v182[0],
                     v188[3],
                     v188[2],
                     v188[1],
                     v188[0],
                     v184,
                     0,
                     v125);
            LastError = v126;
            if ( v126 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC93,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)(unsigned int)v126,
                (int)cbSize);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v245);
LABEL_302:
              wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
              WindowsDeleteString(string);
              goto LABEL_415;
            }
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              &InAccessToken,
              v245);
            v24 = InAccessToken;
            v245 = 0;
            v117 = 1;
          }
          if ( !v201 )
          {
            v127 = GetUserSid(v24);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
              &v201,
              v127);
            if ( !v201 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC9C,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)0x8007000ELL,
                (int)cbSize);
              wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
              WindowsDeleteString(string);
              string = 0;
              if ( v193 )
              {
                v193 = 0;
                if ( *v189 )
                  UnmountVolumeForAppPackage(v190, *v191, *p_TokenInformation);
              }
              wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v205);
              goto LABEL_310;
            }
          }
          if ( (unsigned int)CClassData::HasActivateAsPackage(this)
            && (unsigned __int8)IsMountVolumeForAppPackagePresent() )
          {
            if ( !v282[0] )
            {
              KeyFromToken = PsmGetKeyFromToken(v24, v282, &v249, 0);
              if ( KeyFromToken < 0 )
              {
                v129 = 3235;
LABEL_319:
                LastError = wil::details::in1diag3::Return_NtStatus(
                              retaddr,
                              (void *)v129,
                              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                              (const char *)(unsigned int)KeyFromToken,
                              (int)cbSize);
                wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
                WindowsDeleteString(string);
                goto LABEL_320;
              }
            }
            KeyFromToken = MountVolumeForAppPackage(v282, v201, TokenInformation);
            if ( (KeyFromToken & 0x20000000) != 0 )
            {
              KeyFromToken &= ~0x20000000u;
              LastError = KeyFromToken > 0 ? (unsigned __int16)KeyFromToken | 0x80070000 : KeyFromToken;
              if ( LastError < 0 )
              {
                v131 = (unsigned int)LastError;
                v132 = 3237;
LABEL_328:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v132,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                  (const char *)v131,
                  (int)cbSize);
                goto LABEL_302;
              }
            }
            if ( KeyFromToken < 0 )
            {
              v129 = 3237;
              goto LABEL_319;
            }
            v197 = 1;
          }
          if ( v117 )
          {
            RevertToSelf();
            v181 = 0;
            if ( !ImpersonateLoggedOnUser(v24) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCB1,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)0x80070005LL,
                (int)cbSize);
              wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
              WindowsDeleteString(string);
              goto LABEL_370;
            }
            v181 = 1;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v214,
            0);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v204,
            0);
          v133 = lpCommandLine;
          if ( *((_QWORD *)this + 5) )
            v133 = (const unsigned __int16 *)*((_QWORD *)this + 5);
          if ( v78 )
          {
            v134 = (void *)*((_QWORD *)v200 + 9);
            v135 = (char *)v200 + 156;
          }
          else
          {
            v134 = 0;
            v135 = 0;
          }
          DebuggerInfo = GetDebuggerInfo(
                           v24,
                           v201,
                           v134,
                           v135,
                           v181,
                           v133,
                           (unsigned __int16 **)&v204,
                           (unsigned __int16 **)&v214);
          if ( DebuggerInfo < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xCBB,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
              (const char *)(unsigned int)DebuggerInfo,
              (int)cbSize);
          v137 = v199;
          if ( v204 )
          {
            v138 = 1;
            v137 = v199 | 4;
          }
          else
          {
            v138 = 0;
          }
          v139 = v202;
          v140 = (unsigned int)(v202 - 1);
          if ( v202 != 1 )
          {
            if ( v202 == 2 || (v140 = (unsigned int)(v202 - 3), v202 == 3) )
            {
              v271[2] = packageFullName;
              v271[0] = v24;
              v271[1] = 0;
              v271[3] = *((_QWORD *)this + 5);
              v271[4] = 3;
              v141 = PrepareDesktopAppXActivation(v271, &v225);
              LastError = v141;
              if ( v141 < 0 )
              {
                v131 = (unsigned int)v141;
                v132 = 3312;
                goto LABEL_328;
              }
              v140 = *((unsigned int *)v225 + 4);
              *v246 = v140;
LABEL_363:
              if ( v225 && *((_QWORD *)v225 + 7) )
              {
                v236 = 0;
                v142 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v236);
                v143 = CClassData::AdjustActivationToken(
                         this,
                         v24,
                         v212,
                         a8,
                         v253,
                         v64,
                         v188[3],
                         v188[2],
                         v188[1],
                         v188[0],
                         v184,
                         v225,
                         v142);
                LastError = v143;
                if ( v143 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xD02,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                    (const char *)(unsigned int)v143,
                    (int)cbSize);
                  v121 = &v236;
                  goto LABEL_281;
                }
                wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
                  &InAccessToken,
                  &v236);
                v24 = InAccessToken;
                RevertToSelf();
                v181 = 0;
                if ( !ImpersonateLoggedOnUser(v24) )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xD0C,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                    (const char *)0x80070005LL,
                    (int)cbSize);
                  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v236);
                  goto LABEL_369;
                }
                v181 = 1;
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v236);
              }
              if ( v214 )
              {
                IsPackageSideLoaded = CClassData::AddDebugEnvironmentBlock(
                                        (CClassData *)v140,
                                        v237,
                                        (unsigned __int16 *)v214,
                                        &lpEnvironment);
                LastError = IsPackageSideLoaded;
                if ( IsPackageSideLoaded < 0 )
                {
                  v115 = 3348;
                  goto LABEL_270;
                }
                if ( v237 != lpEnvironment )
                  v240 = 1;
              }
              else
              {
                lpEnvironment = v237;
              }
              CClassData::FireAAMCreateProcessEvent(this, a9, v24, v282);
              if ( ProcessInformation.hProcess )
                wil::details::CloseHandle((wil::details *)ProcessInformation.hProcess, v144);
              if ( ProcessInformation.hThread )
                wil::details::CloseHandle((wil::details *)ProcessInformation.hThread, v144);
              memset(&ProcessInformation, 0, sizeof(ProcessInformation));
              if ( !CreateProcessAsUserW(
                      v24,
                      *((LPCWSTR *)this + 5),
                      lpCommandLine,
                      &ProcessAttributes,
                      0,
                      0,
                      v137,
                      lpEnvironment,
                      0,
                      &StartupInfo,
                      &ProcessInformation) )
              {
                LastError = wil::details::in1diag3::Return_GetLastErrorMsg(
                              retaddr,
                              (void *)0xD41,
                              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                              "Failed CreateProcessAsUser",
                              cbSizea);
                wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
                WindowsDeleteString(string);
                string = 0;
                if ( v193 )
                {
                  v193 = 0;
                  lambda_67f6d9bfab93cea1a1c3904b0150db13_::operator()(&v189);
                }
                wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v205);
                goto LABEL_237;
              }
              RevertToSelf();
              v181 = 0;
              wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v261);
              v145 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&hObject);
              if ( !OpenProcessToken(ProcessInformation.hProcess, 8u, v145) )
              {
                v146 = GetLastError();
                MicrosoftTelemetryAssertTriggeredArgs("rpcss.dll", v146, 0);
                v147 = GetLastError();
                wil::details::in1diag3::Log_Win32(
                  retaddr,
                  (void *)0xD4D,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                  (const char *)v147,
                  (unsigned int)cbSizea);
              }
              v209 = 0;
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                ActivationActivityIfNeeded = CClassData::GetActivationActivityIfNeeded(this, hObject, &v209);
                LastError = ActivationActivityIfNeeded;
                if ( ActivationActivityIfNeeded < 0 )
                {
                  v149 = 3413;
LABEL_412:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v149,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                    (const char *)(unsigned int)ActivationActivityIfNeeded,
                    (int)cbSizea);
                  goto LABEL_413;
                }
              }
              if ( v139 )
              {
                switch ( v139 )
                {
                  case 1:
                    goto LABEL_403;
                  case 2:
                  case 3:
                    *((_DWORD *)v225 + 10) = v137;
                    ActivationActivityIfNeeded = PostCreateProcessDesktopAppXActivation(v24, v225, &ProcessInformation);
                    LastError = ActivationActivityIfNeeded;
                    if ( ActivationActivityIfNeeded < 0 )
                    {
                      v149 = 3446;
                      goto LABEL_412;
                    }
                    v160 = NtResumeThread(ProcessInformation.hThread, 0);
                    if ( v160 < 0 )
                    {
                      LastError = wil::details::in1diag3::Return_NtStatus(
                                    retaddr,
                                    (void *)0xD77,
                                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                                    (const char *)(unsigned int)v160,
                                    (int)cbSizea);
                      wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
                        &v209,
                        0);
                      WindowsDeleteString(string);
LABEL_320:
                      string = 0;
                      if ( v193 )
                      {
                        v193 = 0;
                        v130 = *v189 == 0;
                        goto LABEL_417;
                      }
LABEL_419:
                      wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v205);
LABEL_420:
                      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v219);
                      hProcess = ProcessInformation.hProcess;
                      goto LABEL_422;
                    }
                    break;
                  case 4:
LABEL_403:
                    v150 = string;
                    v151 = CClassData::IdentityType(this);
                    v153 = CClassData::AppUserModelID(v152);
                    v154 = CClassData::ExecutionPackageName(this);
                    v155 = *((_QWORD *)this + 7);
                    v156 = v204;
                    v157 = a6;
                    SessionId = CToken::GetSessionId(v200);
                    LOBYTE(v159) = v202 == 4;
                    LastError = PostCreateProcessUWPActivation(
                                  v200,
                                  *((unsigned int *)v266 + 33),
                                  v159,
                                  SessionId,
                                  v157,
                                  a10,
                                  v156,
                                  v155,
                                  v154,
                                  v153,
                                  v151,
                                  v150,
                                  &ProcessInformation);
                    if ( LastError < 0 )
                    {
                      wil::details::in1diag3::Return_HrMsg(
                        retaddr,
                        (void *)0xD6D,
                        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                        (const char *)(unsigned int)LastError,
                        (int)"PostCreateProcessUWPActivation failed",
                        lpPreviousValueb);
LABEL_413:
                      wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
                        &v209,
                        0);
                      goto LABEL_414;
                    }
                    break;
                }
              }
              else if ( v138 )
              {
                v226 = *((_DWORD *)this + 33);
                CClassData::IdentityType(this);
                CClassData::AppUserModelID(v161);
                CClassData::ExecutionPackageName(this);
                v162 = (int)v204;
                v163 = a6;
                v164 = CToken::GetSessionId(v200);
                LODWORD(cbSizea) = v162;
                ActivationActivityIfNeeded = LaunchDebugger(v200, v164, v163, 0);
                LastError = ActivationActivityIfNeeded;
                if ( ActivationActivityIfNeeded < 0 )
                {
                  v149 = 3427;
                  goto LABEL_412;
                }
              }
              v167 = v209;
              v168 = 0;
              v209 = 0;
              if ( v167 )
              {
                ActivationActivity::DestroyActivationActivity(v167);
                v168 = v209;
              }
              v193 = 0;
              v209 = 0;
              if ( v168 )
                ActivationActivity::DestroyActivationActivity(v168);
              WindowsDeleteString(string);
              string = 0;
              if ( v193 )
              {
                v193 = 0;
                lambda_67f6d9bfab93cea1a1c3904b0150db13_::operator()(&v189);
              }
              wil::details::lambda_call__lambda_2942b891d21f79810d9cbda34a89e9f0___::reset(&v205);
              v169 = ProcessInformation.hProcess;
              dwProcessId = ProcessInformation.dwProcessId;
              hThread = ProcessInformation.hThread;
              memset(&ProcessInformation, 0, sizeof(ProcessInformation));
              *v254 = v169;
              v172 = hObject;
              hObject = 0;
              *v255 = v172;
              *v256 = dwProcessId;
              CloseHandle(hThread);
              v239 = 1;
              wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v219);
              v270 = 0;
              lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v269);
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(hObject);
              if ( lpMem )
                HeapFree(g_hHeap, 0, lpMem);
              if ( hMem )
                LocalFree(hMem);
              if ( v213 )
                LocalFree(v213);
              if ( v214 )
                LocalFree(v214);
              if ( v204 )
                LocalFree(v204);
              v174 = lpAttributeList;
              lpAttributeList = 0;
              if ( v174 )
                LocalFree(v174);
              if ( v221 )
                LocalFree(v221);
              if ( v201 )
                HeapFree(g_hHeap, 0, v201);
              if ( (char *)InAccessToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(InAccessToken);
              if ( ProcessInformation.hProcess )
                wil::details::CloseHandle((wil::details *)ProcessInformation.hProcess, v173);
              if ( ProcessInformation.hThread )
                wil::details::CloseHandle((wil::details *)ProcessInformation.hThread, v173);
              if ( lpCommandLine )
                HeapFree(g_hHeap, 0, lpCommandLine);
              return 0;
            }
            if ( v202 != 4 )
              goto LABEL_363;
          }
          if ( v138 || !lpMem )
          {
            *v246 = v138;
          }
          else
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &hMem,
              0);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v213,
              0);
            LastError = PrepareUWPActivation(
                          (unsigned __int16 *)lpMem,
                          (char *)v200 + 156,
                          (unsigned __int16 **)&v213,
                          (unsigned __int16 **)&hMem,
                          v246);
            if ( LastError < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0xCCB,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)(unsigned int)LastError,
                (int)"Failed PrepareUWPActivation",
                lpPreviousValuea);
              goto LABEL_302;
            }
            if ( *v246 )
            {
              if ( v213 )
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                  &v204,
                  &v213);
              if ( hMem )
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                  &v214,
                  &hMem);
            }
          }
          goto LABEL_363;
        }
        if ( !v250 )
        {
          if ( !v200 || !ImpersonateLoggedOnUser(*((HANDLE *)v200 + 9)) )
          {
            v42 = 2927;
            goto LABEL_21;
          }
          v181 = 1;
          if ( v24 && !ImpersonateLoggedOnUser(v24) )
          {
            v42 = 2929;
            goto LABEL_21;
          }
          RevertToSelf();
          v181 = 0;
        }
        if ( (unsigned int)CClassData::HasActivateAsPackage(this) )
        {
          if ( v24 )
          {
            v78 = a10;
            goto LABEL_162;
          }
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &InAccessToken,
            0);
          v79 = TokenInformation;
          CClassData::ExecutionPackageName(this);
          v78 = a10;
          IsActivateAsIUAllowedOld = GetInteractiveUserTokenForCallerRequest(
                                       v200,
                                       v80,
                                       (unsigned __int64)a10,
                                       v79,
                                       1,
                                       &InAccessToken);
          LastError = IsActivateAsIUAllowedOld;
          if ( IsActivateAsIUAllowedOld < 0 )
          {
            v37 = 2945;
            goto LABEL_14;
          }
        }
        else
        {
          v81 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&InAccessToken);
          if ( (CClassData::AppIDFlags(this) & 0x200) != 0
            || (v82 = 0, (unsigned int)((__int64 (*)(void))CClassData::IdentityType)() == 5) )
          {
            v82 = 1;
          }
          v83 = TokenInformation;
          CClassData::ExecutionPackageName(this);
          v78 = a10;
          IsActivateAsIUAllowedOld = GetInteractiveUserTokenForCallerRequest(
                                       v200,
                                       v84,
                                       (unsigned __int64)a10,
                                       v83,
                                       v82,
                                       v81);
          LastError = IsActivateAsIUAllowedOld;
          if ( IsActivateAsIUAllowedOld < 0 )
          {
            v37 = 2970;
            goto LABEL_14;
          }
        }
        v24 = InAccessToken;
LABEL_162:
        if ( v24 )
        {
          if ( v195 )
          {
            v241 = 0;
            v85 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v241);
            UserTokenWithPsmClaimsAdded = GetUserTokenWithPsmClaimsAdded(v200, v24, 1, v85);
            LastError = UserTokenWithPsmClaimsAdded;
            if ( UserTokenWithPsmClaimsAdded < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBA8,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)(unsigned int)UserTokenWithPsmClaimsAdded,
                (int)cbSize);
              v87 = &v241;
LABEL_166:
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v87);
              goto LABEL_420;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
              &InAccessToken,
              &v241);
            v24 = InAccessToken;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v241);
          }
          if ( (CClassData::AppIDFlags(this) & 8) == 0 && !(unsigned int)CClassData::HasActivateAsPackage(v88) )
          {
            v234 = 0;
            v89 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v234);
            v90 = CClassData::DuplicateAndAdjustInteractiveUserTokenILIfNecessary(v200, v24, v89);
            LastError = v90;
            if ( v90 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBB7,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                (const char *)(unsigned int)v90,
                (int)cbSize);
              v87 = &v234;
              goto LABEL_166;
            }
            if ( (unsigned __int64)(v234 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
                &InAccessToken,
                &v234);
              v24 = InAccessToken;
            }
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v234);
          }
        }
        if ( (CClassData::AppIDFlags(this) & 0x8000) != 0 )
        {
          v252 = 0;
          v91 = *((_QWORD *)this + 8);
          v228 = 0x42EB16A6924DC564LL;
          v229 = 0x6FA07DFA619A9A92LL;
          v230 = 0x4ABD4CB77FC12E96LL;
          v231 = 0x2906B14578EFAAADLL;
          if ( v91 )
          {
            IsActivateAsIUAllowedOld = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v91 + 40LL))(
                                         v91,
                                         &v252);
            LastError = IsActivateAsIUAllowedOld;
            if ( IsActivateAsIUAllowedOld < 0 )
            {
              v37 = 3022;
              goto LABEL_14;
            }
            if ( v252 )
            {
              v92 = *v252 - v228;
              if ( *v252 == v228 )
                v92 = v252[1] - v229;
              if ( !v92 )
                goto LABEL_186;
              v93 = *v252 - v230;
              if ( *v252 == v230 )
                v93 = v252[1] - v231;
              if ( !v93 )
              {
LABEL_186:
                v235 = 0;
                v94 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v235);
                MediumRaisedCredUIToken = GetMediumRaisedCredUIToken(v24, v94);
                LastError = MediumRaisedCredUIToken;
                if ( MediumRaisedCredUIToken < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xBD3,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                    (const char *)(unsigned int)MediumRaisedCredUIToken,
                    (int)cbSize);
                  v87 = &v235;
                  goto LABEL_166;
                }
                if ( v235 )
                {
                  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
                    &InAccessToken,
                    &v235);
                  v24 = InAccessToken;
                }
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v235);
              }
            }
          }
        }
        v106 = (CClassData::AppIDFlags(this) & 1) == 0;
        lpDesktop = StartupInfo.lpDesktop;
        if ( !v106 )
          lpDesktop = v264;
        StartupInfo.lpDesktop = lpDesktop;
        goto LABEL_194;
      }
    }
    v64 = 0;
    goto LABEL_109;
  }
  if ( *(_DWORD *)(v58 + 76) == 2 )
  {
    v57 = 1;
    v232 = 2;
    goto LABEL_80;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xABA,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
    (const char *)0x80070057LL,
    (int)cbSize);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v219);
LABEL_460:
  if ( ProcessInformation.hProcess )
    NtTerminateProcess(ProcessInformation.hProcess, v223);
  v270 = 0;
  lambda_cbcbdc03c8f14a3fd3b6967d414ef0cb_::operator()(v269);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v213);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v214);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v204);
  wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
    &lpAttributeList,
    0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v221);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v201);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&InAccessToken);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v175);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpCommandLine);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18004e578  mov     [rsp-8+arg_10], rbx
0x18004e57d  push    rbp
0x18004e57e  push    rsi
0x18004e57f  push    rdi
0x18004e580  push    r12
0x18004e582  push    r13
0x18004e584  push    r14
0x18004e586  push    r15
0x18004e588  lea     rbp, [rsp-750h]
0x18004e590  sub     rsp, 850h
0x18004e597  mov     rax, cs:__security_cookie
0x18004e59e  xor     rax, rsp
0x18004e5a1  mov     [rbp+780h+var_40], rax
0x18004e5a8  mov     rax, [rbp+780h+arg_30]
0x18004e5af  mov     rdi, rcx
0x18004e5b2  mov     rbx, [rbp+780h+arg_50]
0x18004e5b9  mov     r12, [rbp+780h+arg_A0]
0x18004e5c0  mov     rsi, [rbp+780h+hToken]
0x18004e5c7  mov     r14, [rbp+780h+arg_70]
0x18004e5ce  mov     r15, [rbp+780h+arg_78]
0x18004e5d5  mov     r13, [rbp+780h+arg_80]
0x18004e5dc  mov     [rbp+780h+var_510], rax
0x18004e5e3  mov     rax, [rbp+780h+arg_58]
0x18004e5ea  mov     [rbp+780h+var_5C8], rax
0x18004e5f1  mov     rax, [rbp+780h+arg_68]
0x18004e5f8  mov     [rbp+780h+var_4F8], rax
0x18004e5ff  mov     rax, [rbp+780h+arg_88]
0x18004e606  mov     [rbp+780h+var_5C0], rax
0x18004e60d  mov     rax, [rbp+780h+arg_90]
0x18004e614  mov     [rbp+780h+var_5B8], rax
0x18004e61b  mov     rax, [rbp+780h+arg_98]
0x18004e622  mov     [rbp+780h+var_5B0], rax
0x18004e629  xor     eax, eax
0x18004e62b  mov     [rbp+780h+var_5DC], r8d
0x18004e632  mov     [rbp+780h+var_500], rcx
0x18004e639  lea     rcx, [rbp+780h+StartupInfo.lpReserved]; void *
0x18004e640  mov     [rbp+780h+var_790], rdx
0x18004e644  xor     edx, edx; Val
0x18004e646  lea     r8d, [rax+68h]; Size
0x18004e64a  mov     [rbp+780h+var_734], r9d
0x18004e64e  mov     [rbp+780h+var_508], rbx
0x18004e655  mov     [rbp+780h+var_5F8], r12
0x18004e65c  mov     [rbp+780h+lpCommandLine], rax
0x18004e660  mov     qword ptr [rbp+780h+StartupInfo.cb], rax
0x18004e667  call    memset_0
0x18004e66c  xor     ecx, ecx
0x18004e66e  xorps   xmm0, xmm0
0x18004e671  xor     eax, eax
0x18004e673  mov     [rbp+780h+InAccessToken], rcx
0x18004e677  movups  xmmword ptr [rbp+780h+ProcessInformation.hProcess], xmm0
0x18004e67e  mov     qword ptr [rbp+780h+ProcessInformation.dwProcessId], rax
0x18004e685  movups  xmmword ptr [rbp+780h+ProcessAttributes.nLength], xmm0
0x18004e68c  mov     qword ptr [rbp+780h+ProcessAttributes.bInheritHandle], rax
0x18004e693  mov     [rbp+780h+var_788], rcx
0x18004e697  mov     [rbp+780h+var_5E8], rcx
0x18004e69e  mov     [rbp+780h+var_6C0], rcx
0x18004e6a5  mov     [rbp+780h+packageFullName], rcx
0x18004e6a9  mov     [rbp+780h+lpAttributeList], rcx
0x18004e6ad  call    cs:__imp_GetCurrentProcess
0x18004e6b4  nop     dword ptr [rax+rax+00h]
0x18004e6b9  xor     edx, edx
0x18004e6bb  mov     rcx, rdi; this
0x18004e6be  mov     [rbp+780h+var_4F0], rax
0x18004e6c5  mov     [rbp+780h+var_530], rdx
0x18004e6cc  mov     [rbp+780h+var_5F0], rdx
0x18004e6d3  mov     [rbp+780h+var_770], rdx
0x18004e6d7  mov     [rbp+780h+var_728], rdx
0x18004e6db  mov     [rbp+780h+var_730], rdx
0x18004e6df  mov     [rbp+780h+hMem], rdx
0x18004e6e3  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x18004e6e8  mov     [rbp+780h+var_688], eax
0x18004e6ee  mov     [rbp+780h+var_7A8], dl
0x18004e6f1  mov     [rbp+780h+var_7E6], dl
0x18004e6f4  mov     [rbp+780h+var_690], rdx
0x18004e6fb  call    ?IsInteractiveUser@CClassData@@QEAAHXZ; CClassData::IsInteractiveUser(void)
0x18004e700  xor     edx, edx
0x18004e702  test    eax, eax
0x18004e704  jz      short loc_18004E718
0x18004e706  mov     rcx, rdi; this
0x18004e709  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x18004e70e  mov     [rbp+780h+var_7B7], 1
0x18004e712  bt      eax, 0Ch
0x18004e716  jb      short loc_18004E71B
0x18004e718  mov     [rbp+780h+var_7B7], dl
0x18004e71b  mov     r8d, 114h; Size
0x18004e721  lea     rcx, [rbp+780h+var_3C0]; void *
0x18004e728  call    memset_0
0x18004e72d  xor     edx, edx; Val
0x18004e72f  lea     rcx, [rbp+780h+var_210]; void *
0x18004e736  mov     r8d, 1D0h; Size
0x18004e73c  call    memset_0
0x18004e741  mov     rax, [rbp+780h+var_5C0]
0x18004e748  lea     rdx, [rbp+780h+var_700]; struct wil::details::IFailureCallback *
0x18004e74f  xor     ecx, ecx
0x18004e751  mov     [rbp+780h+var_5E0], 1D0h
0x18004e75b  mov     [rbp+780h+lpMem], rcx
0x18004e75f  mov     [rbp+780h+var_7F8], cl
0x18004e762  mov     [rbp+780h+var_628], ecx
0x18004e768  mov     [rbp+780h+hObject], rcx
0x18004e76c  mov     [rax], rcx
0x18004e76f  mov     rax, [rbp+780h+var_5B8]
0x18004e776  mov     [rbp+780h+var_4A8], rdi
0x18004e77d  mov     [rax], rcx
0x18004e780  mov     rax, [rbp+780h+var_5B0]
0x18004e787  mov     [rax], ecx
0x18004e789  lea     rax, [rbp+780h+var_7E6]
0x18004e78d  mov     [rbp+780h+var_4E0], rax
0x18004e794  lea     rax, [rbp+780h+packageFullName]
0x18004e798  mov     [rbp+780h+var_4D8], rax
0x18004e79f  lea     rax, [rbp+780h+var_628]
0x18004e7a6  mov     [rbp+780h+var_4D0], rax
0x18004e7ad  lea     rax, [rbp+780h+lpAttributeList]
0x18004e7b1  mov     [rbp+780h+var_4C8], rax
0x18004e7b8  lea     rax, [rbp+780h+var_5E8]
0x18004e7bf  mov     [r12], ecx
0x18004e7c3  xor     r12d, r12d
0x18004e7c6  mov     [rbp+780h+var_4C0], rax
0x18004e7cd  lea     rcx, [rbp+780h+var_6F8]; this
0x18004e7d4  lea     rax, [rbp+780h+var_690]
0x18004e7db  mov     [rbp+780h+var_6A0], r12d
0x18004e7e2  mov     [rbp+780h+var_4B8], rax
0x18004e7e9  lea     rax, [rbp+780h+var_6A0]
0x18004e7f0  mov     [rbp+780h+var_4B0], rax
0x18004e7f7  lea     rax, [rbp+780h+var_7F8]
0x18004e7fb  mov     [rbp+780h+var_4A0], rax
0x18004e802  lea     rax, [rbp+780h+ProcessInformation]
0x18004e809  mov     [rsp+880h+var_810], rax
0x18004e80e  lea     rax, [rbp+780h+var_6A0]
0x18004e815  mov     [rsp+880h+var_808], rax
0x18004e81a  lea     rax, off_180117CA8
0x18004e821  mov     [rbp+780h+var_700], rax
0x18004e828  mov     [rbp+780h+var_800], 1
0x18004e82c  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18004e831  lea     rax, [rbp+780h+var_6A0]
0x18004e838  mov     [rbp+780h+var_6C8], rax
0x18004e83f  test    rbx, rbx
0x18004e842  jz      short loc_18004E84A
0x18004e844  mov     [rbp+780h+var_7E5], 1
0x18004e848  jmp     short loc_18004E875
0x18004e84a  mov     rcx, [rdi+58h]
0x18004e84e  mov     rax, rcx
0x18004e851  mov     [rbp+780h+var_7E5], r12b
0x18004e855  neg     rax
0x18004e858  sbb     rax, rax
0x18004e85b  lea     rdx, [rcx+50h]
0x18004e85f  test    rdx, rax
0x18004e862  jz      short loc_18004E875
0x18004e864  neg     rcx
0x18004e867  sbb     rax, rax
0x18004e86a  and     rax, rdx
0x18004e86d  cmp     [rax+8], r12
0x18004e871  setnz   [rbp+780h+var_7E5]
0x18004e875  mov     ebx, [rbp+780h+var_734]
0x18004e878  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18004e87f  and     ebx, 4
0x18004e882  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18004e887  test    al, al
0x18004e889  jz      short loc_18004E89E
0x18004e88b  test    ebx, ebx
0x18004e88d  jz      short loc_18004E8DA
0x18004e88f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004e894  mov     edx, 9FEh
0x18004e899  jmp     loc_18004EA3F
0x18004e89e  test    ebx, ebx
0x18004e8a0  jz      short loc_18004E8DA
0x18004e8a2  mov     rdx, [rbp+780h+var_790]; struct CToken *
0x18004e8a6  mov     r8d, 1; int
0x18004e8ac  mov     rcx, rdi; this
0x18004e8af  call    ?PrivilegedLaunchIsActivateAsIUAllowedOld@CClassData@@QEAAJPEAVCToken@@H@Z; CClassData::PrivilegedLaunchIsActivateAsIUAllowedOld(CToken *,int)
0x18004e8b4  mov     ebx, eax
0x18004e8b6  test    eax, eax
0x18004e8b8  jns     short loc_18004E8DA
0x18004e8ba  mov     edx, 0A04h; void *
0x18004e8bf  mov     r9d, eax; char *
0x18004e8c2  mov     rcx, [rbp+788h]; this
0x18004e8c9  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18004e8d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e8d5  jmp     loc_180050BB9
0x18004e8da  test    r14, r14
0x18004e8dd  jnz     short loc_18004E8FC
0x18004e8df  test    r15, r15
0x18004e8e2  jnz     short loc_18004E8FC
0x18004e8e4  test    r13, r13
0x18004e8e7  jnz     short loc_18004E8FC
0x18004e8e9  mov     r13d, 410h
0x18004e8ef  mov     [rbp+780h+var_7B8], r12b
0x18004e8f3  mov     [rbp+780h+var_798], r13d
0x18004e8f7  jmp     loc_18004E983
0x18004e8fc  mov     rcx, rdi; this
0x18004e8ff  call    ?HasActivateAsPackage@CClassData@@QEBAHXZ; CClassData::HasActivateAsPackage(void)
0x18004e904  test    eax, eax
0x18004e906  jnz     short loc_18004E92B
0x18004e908  mov     edx, 0A0Bh; void *
0x18004e90d  mov     rcx, [rbp+788h]; this
0x18004e914  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18004e91b  mov     r9d, 80070005h; char *
0x18004e921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e926  jmp     loc_1800506AC
0x18004e92b  lea     rax, [r14-1]
0x18004e92f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e933  ja      loc_180050EB1
0x18004e939  lea     rax, [r15-1]
0x18004e93d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e941  ja      loc_180050EB1
0x18004e947  lea     rax, [r13-1]
0x18004e94b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e94f  ja      loc_180050EB1
0x18004e955  bts     [rbp+780h+StartupInfo.dwFlags], 8
0x18004e95d  mov     [rbp+780h+StartupInfo.hStdError], r13
0x18004e964  mov     r13d, 400h
0x18004e96a  mov     [rbp+780h+var_798], 400h
0x18004e971  mov     [rbp+780h+StartupInfo.hStdInput], r14
0x18004e978  mov     [rbp+780h+StartupInfo.hStdOutput], r15
0x18004e97f  mov     [rbp+780h+var_7B8], 1
0x18004e983  xor     ebx, ebx
0x18004e985  mov     rcx, rdi; this
0x18004e988  mov     [rbp+780h+var_7E7], bl
0x18004e98b  mov     [rbp+780h+var_7E4+3], bl
0x18004e98e  mov     [rbp+780h+var_7E4+2], bl
0x18004e991  mov     [rbp+780h+var_7E4+1], bl
0x18004e994  mov     [rbp+780h+var_7E4], bl
0x18004e997  mov     [rbp+780h+var_7E8], bl
0x18004e99a  call    ?HasActivateAsPackage@CClassData@@QEBAHXZ; CClassData::HasActivateAsPackage(void)
0x18004e99f  test    eax, eax
0x18004e9a1  jz      loc_18004ED0B
0x18004e9a7  mov     rcx, rdi; this
0x18004e9aa  call    ?ExecutionPackageName@CClassData@@QEBAPEBGXZ; CClassData::ExecutionPackageName(void)
0x18004e9af  mov     rcx, rdi
0x18004e9b2  mov     [rbp+780h+packageFullName], rax
0x18004e9b6  call    ?GetRuntimeBehavior@CClassData@@QEBA?AW4RuntimeBehavior@AppModel@@XZ; CClassData::GetRuntimeBehavior(void)
0x18004e9bb  test    eax, eax
0x18004e9bd  jnz     short loc_18004EA1B
0x18004e9bf  call    IsPrepareExclusiveResourceForPackageActivationPresent
0x18004e9c4  test    al, al
0x18004e9c6  jz      short loc_18004EA10
0x18004e9c8  mov     ebx, [rdi+84h]
0x18004e9ce  mov     rcx, rdi; this
0x18004e9d1  call    ?AppUserModelID@CClassData@@QEBAPEBGXZ; CClassData::AppUserModelID(void)
0x18004e9d6  mov     rcx, [rbp+780h+packageFullName]
0x18004e9da  lea     r9, [rbp+780h+var_5F0]
0x18004e9e1  mov     r8d, ebx
0x18004e9e4  mov     rdx, rax
0x18004e9e7  call    cs:__imp_PrepareExclusiveResourceForPackageActivation
0x18004e9ee  nop     dword ptr [rax+rax+00h]
0x18004e9f3  mov     ebx, eax
0x18004e9f5  test    eax, eax
0x18004e9f7  jns     short loc_18004EA03
0x18004e9f9  mov     edx, 0A4Dh
0x18004e9fe  jmp     loc_18004E8BF
0x18004ea03  xor     ebx, ebx
0x18004ea05  cmp     [rbp+780h+var_5F0], rbx
0x18004ea0c  setnz   [rbp+780h+var_7E6]
0x18004ea10  mov     r14d, 1
0x18004ea16  mov     r15b, r14b
0x18004ea19  jmp     short loc_18004EA58
0x18004ea1b  mov     rcx, rdi
0x18004ea1e  call    ?GetRuntimeBehavior@CClassData@@QEBA?AW4RuntimeBehavior@AppModel@@XZ; CClassData::GetRuntimeBehavior(void)
0x18004ea23  cmp     eax, 1
0x18004ea26  jz      short loc_18004EA4C
0x18004ea28  mov     rcx, rdi
0x18004ea2b  call    ?GetRuntimeBehavior@CClassData@@QEBA?AW4RuntimeBehavior@AppModel@@XZ; CClassData::GetRuntimeBehavior(void)
0x18004ea30  cmp     eax, 3
0x18004ea33  jz      short loc_18004EA4C
0x18004ea35  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004ea3a  mov     edx, 0A5Dh
0x18004ea3f  mov     ebx, 8000FFFFh
0x18004ea44  mov     r9d, ebx
0x18004ea47  jmp     loc_18004E8C2
0x18004ea4c  mov     r15b, 1
0x18004ea4f  mov     r14d, 2
0x18004ea55  mov     r12b, r15b
0x18004ea58  mov     rcx, rdi; this
0x18004ea5b  mov     [rbp+780h+var_780], r14d
0x18004ea5f  call    ?HasActivateAsPackage@CClassData@@QEBAHXZ; CClassData::HasActivateAsPackage(void)
0x18004ea64  test    eax, eax
0x18004ea66  jnz     short loc_18004EA6D
0x18004ea68  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004ea6d  mov     rax, [rdi+60h]
0x18004ea71  test    rax, rax
0x18004ea74  jz      short loc_18004EA7E
0x18004ea76  mov     ecx, [rax+0FCh]
0x18004ea7c  jmp     short loc_18004EA88
0x18004ea7e  mov     rax, [rdi+58h]
0x18004ea82  mov     ecx, [rax+12Ch]
0x18004ea88  cmp     ecx, 1
0x18004ea8b  jnz     loc_18004EC86
0x18004ea91  mov     rcx, rdi; this
0x18004ea94  call    ?GetAppTrustLevel@CClassData@@QEBA?AW4TrustLevel@AppModel@@XZ; CClassData::GetAppTrustLevel(void)
0x18004ea99  cmp     eax, 1
0x18004ea9c  jnz     loc_18004EC86
0x18004eaa2  mov     rcx, rdi; this
0x18004eaa5  call    ?GetAppTrustLevel@CClassData@@QEBA?AW4TrustLevel@AppModel@@XZ; CClassData::GetAppTrustLevel(void)
0x18004eaaa  cmp     eax, 1
0x18004eaad  jnz     loc_18004EC81
0x18004eab3  xor     edx, edx; Val
0x18004eab5  lea     rcx, [rbp+780h+packageFamilyName]; void *
0x18004eabc  mov     r8d, 82h; Size
0x18004eac2  call    memset_0
0x18004eac7  mov     rcx, [rbp+780h+packageFullName]; packageFullName
0x18004eacb  lea     r8, [rbp+780h+packageFamilyName]; packageFamilyName
  ... truncated ...
```
