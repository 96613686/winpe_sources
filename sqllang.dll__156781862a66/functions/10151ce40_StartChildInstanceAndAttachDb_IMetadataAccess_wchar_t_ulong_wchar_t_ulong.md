# StartChildInstanceAndAttachDb(IMetadataAccess *,wchar_t *,ulong,wchar_t *,ulong)

- ea: `0x10151ce40`
- end: `0x10151f11d`
- name: `?StartChildInstanceAndAttachDb@@YAJPEAVIMetadataAccess@@PEA_WK1K@Z`
- size: `8925`
- prototype: `__int64 __fastcall(struct IMetadataAccess *, wchar_t *, unsigned int, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x100f22fc0`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401433`
- `0x1004076a0`
- `0x100430960`
- `0x100430d60`
- `0x10043c390`
- `0x10043c470`
- `0x100453e90`
- `0x10058b8e0`
- `0x100754350`
- `0x100756e20`
- `0x100757670`
- `0x1007d40d0`
- `0x100a7cbd0`
- `0x10139b190`
- `0x10139bbf0`
- `0x101489380`
- `0x10151b5f0`
- `0x10151b7e0`
- `0x10151bbd0`
- `0x10151c0a0`
- `0x10151c240`
- `0x10151c3a0`
- `0x10151c4e0`
- `0x10151cc80`
- `0x10151ce40`

## import_xrefs

- `Secur32!LsaFreeReturnBuffer` at `0x10151e33d`
- `Secur32!LsaFreeReturnBuffer` at `0x10151e5ad`
- `Secur32!LsaFreeReturnBuffer` at `0x10151e6eb`
- `Secur32!LsaFreeReturnBuffer` at `0x10151e33d`
- `Secur32!LsaFreeReturnBuffer` at `0x10151e5ad`
- `Secur32!LsaFreeReturnBuffer` at `0x10151e6eb`
- `Secur32!LsaDeregisterLogonProcess` at `0x10151e354`
- `Secur32!LsaDeregisterLogonProcess` at `0x10151e5c4`
- `Secur32!LsaDeregisterLogonProcess` at `0x10151e702`
- `Secur32!LsaDeregisterLogonProcess` at `0x10151e354`
- `Secur32!LsaDeregisterLogonProcess` at `0x10151e5c4`
- `Secur32!LsaDeregisterLogonProcess` at `0x10151e702`
- `KERNEL32!TerminateProcess` at `0x10151e568`
- `KERNEL32!TerminateProcess` at `0x10151e568`
- `KERNEL32!ResumeThread` at `0x10151e527`
- `KERNEL32!ResumeThread` at `0x10151e527`
- `KERNEL32!GetLastError` at `0x10151d432`
- `KERNEL32!GetLastError` at `0x10151d581`
- `KERNEL32!GetLastError` at `0x10151d6c2`
- `KERNEL32!GetLastError` at `0x10151d806`
- `KERNEL32!GetLastError` at `0x10151d8a9`
- `KERNEL32!GetLastError` at `0x10151da29`
- `KERNEL32!GetLastError` at `0x10151daec`
- `KERNEL32!GetLastError` at `0x10151db0a`
- `KERNEL32!GetLastError` at `0x10151dc32`
- `KERNEL32!GetLastError` at `0x10151dce6`
- `KERNEL32!GetLastError` at `0x10151e2d6`
- `KERNEL32!GetLastError` at `0x10151eaba`
- `KERNEL32!GetLastError` at `0x10151efa7`
- `KERNEL32!GetLastError` at `0x10151d432`
- `KERNEL32!GetLastError` at `0x10151d581`
- `KERNEL32!GetLastError` at `0x10151d6c2`
- `KERNEL32!GetLastError` at `0x10151d806`
- `KERNEL32!GetLastError` at `0x10151d8a9`
- `KERNEL32!GetLastError` at `0x10151da29`
- `KERNEL32!GetLastError` at `0x10151daec`
- `KERNEL32!GetLastError` at `0x10151db0a`
- `KERNEL32!GetLastError` at `0x10151dc32`
- `KERNEL32!GetLastError` at `0x10151dce6`
- `KERNEL32!GetLastError` at `0x10151e2d6`
- `KERNEL32!GetLastError` at `0x10151eaba`
- `KERNEL32!GetLastError` at `0x10151efa7`
- `KERNEL32!CloseHandle` at `0x10151d173`
- `KERNEL32!CloseHandle` at `0x10151d191`
- `KERNEL32!CloseHandle` at `0x10151d487`
- `KERNEL32!CloseHandle` at `0x10151d5d6`
- `KERNEL32!CloseHandle` at `0x10151d717`
- `KERNEL32!CloseHandle` at `0x10151d863`
- `KERNEL32!CloseHandle` at `0x10151d8fe`
- `KERNEL32!CloseHandle` at `0x10151dc87`
- `KERNEL32!CloseHandle` at `0x10151dd3b`
- `KERNEL32!CloseHandle` at `0x10151e327`
- `KERNEL32!CloseHandle` at `0x10151e3cf`
- `KERNEL32!CloseHandle` at `0x10151e597`
- `KERNEL32!CloseHandle` at `0x10151e63f`
- `KERNEL32!CloseHandle` at `0x10151e6d5`
- `KERNEL32!CloseHandle` at `0x10151e937`
- `KERNEL32!CloseHandle` at `0x10151e9a9`
- `KERNEL32!CloseHandle` at `0x10151e9c1`
- `KERNEL32!CloseHandle` at `0x10151eaf0`
- `KERNEL32!CloseHandle` at `0x10151eb62`
- `KERNEL32!CloseHandle` at `0x10151eb7a`
- `KERNEL32!CloseHandle` at `0x10151ebb4`
- `KERNEL32!CloseHandle` at `0x10151ec26`
- `KERNEL32!CloseHandle` at `0x10151ec42`
- `KERNEL32!CloseHandle` at `0x10151ecac`
- `KERNEL32!CloseHandle` at `0x10151ed1e`
- `KERNEL32!CloseHandle` at `0x10151ed36`
- `KERNEL32!CloseHandle` at `0x10151ed77`
- `KERNEL32!CloseHandle` at `0x10151ede9`
- `KERNEL32!CloseHandle` at `0x10151ee01`
- `KERNEL32!CloseHandle` at `0x10151ee25`
- `KERNEL32!CloseHandle` at `0x10151eeba`
- `KERNEL32!CloseHandle` at `0x10151ef2c`
- `KERNEL32!CloseHandle` at `0x10151ef44`
- `KERNEL32!CloseHandle` at `0x10151effc`
- `KERNEL32!CloseHandle` at `0x10151d173`
- `KERNEL32!CloseHandle` at `0x10151d191`
- `KERNEL32!CloseHandle` at `0x10151d487`
- `KERNEL32!CloseHandle` at `0x10151d5d6`
- `KERNEL32!CloseHandle` at `0x10151d717`
- `KERNEL32!CloseHandle` at `0x10151d863`
- `KERNEL32!CloseHandle` at `0x10151d8fe`
- `KERNEL32!CloseHandle` at `0x10151dc87`
- `KERNEL32!CloseHandle` at `0x10151dd3b`
- `KERNEL32!CloseHandle` at `0x10151e327`
- `KERNEL32!CloseHandle` at `0x10151e3cf`
- `KERNEL32!CloseHandle` at `0x10151e597`
- `KERNEL32!CloseHandle` at `0x10151e63f`
- `KERNEL32!CloseHandle` at `0x10151e6d5`
- `KERNEL32!CloseHandle` at `0x10151e937`
- `KERNEL32!CloseHandle` at `0x10151e9a9`
- `KERNEL32!CloseHandle` at `0x10151e9c1`
- `KERNEL32!CloseHandle` at `0x10151eaf0`
- `KERNEL32!CloseHandle` at `0x10151eb62`
- `KERNEL32!CloseHandle` at `0x10151eb7a`
- `KERNEL32!CloseHandle` at `0x10151ebb4`
- `KERNEL32!CloseHandle` at `0x10151ec26`
- `KERNEL32!CloseHandle` at `0x10151ec42`
- `KERNEL32!CloseHandle` at `0x10151ecac`
- `KERNEL32!CloseHandle` at `0x10151ed1e`
- `KERNEL32!CloseHandle` at `0x10151ed36`
- `KERNEL32!CloseHandle` at `0x10151ed77`
- `KERNEL32!CloseHandle` at `0x10151ede9`
- `KERNEL32!CloseHandle` at `0x10151ee01`
- `KERNEL32!CloseHandle` at `0x10151ee25`
- `KERNEL32!CloseHandle` at `0x10151eeba`
- `KERNEL32!CloseHandle` at `0x10151ef2c`
- `KERNEL32!CloseHandle` at `0x10151ef44`
- `KERNEL32!CloseHandle` at `0x10151effc`
- `KERNEL32!GetProcAddress` at `0x10151d61b`
- `KERNEL32!GetProcAddress` at `0x10151d61b`
- `KERNEL32!LocalFree` at `0x10151e542`
- `KERNEL32!LocalFree` at `0x10151e551`
- `KERNEL32!LocalFree` at `0x10151e542`
- `KERNEL32!LocalFree` at `0x10151e551`
- `KERNEL32!WaitForMultipleObjects` at `0x10151e9ff`
- `KERNEL32!WaitForMultipleObjects` at `0x10151e9ff`
- `KERNEL32!GetFileAttributesExW` at `0x10151da1f`
- `KERNEL32!GetFileAttributesExW` at `0x10151da1f`
- `KERNEL32!CopyFileW` at `0x10151da49`
- `KERNEL32!CopyFileW` at `0x10151da49`
- `KERNEL32!GetProcessTimes` at `0x10151eaac`
- `KERNEL32!GetProcessTimes` at `0x10151eaac`
- `ADVAPI32!CreateProcessAsUserW` at `0x10151e2c8`
- `ADVAPI32!CreateProcessAsUserW` at `0x10151e2c8`
- `ADVAPI32!SetSecurityInfo` at `0x10151e517`
- `ADVAPI32!SetSecurityInfo` at `0x10151e517`
- `ADVAPI32!SetEntriesInAclW` at `0x10151e4ea`
- `ADVAPI32!SetEntriesInAclW` at `0x10151e4ea`
- `ADVAPI32!RevertToSelf` at `0x10151d41b`
- `ADVAPI32!RevertToSelf` at `0x10151d56a`
- `ADVAPI32!RevertToSelf` at `0x10151d6ab`
- `ADVAPI32!RevertToSelf` at `0x10151d7ef`
- `ADVAPI32!RevertToSelf` at `0x10151d892`
- `ADVAPI32!RevertToSelf` at `0x10151dad5`
- `ADVAPI32!RevertToSelf` at `0x10151dc1b`
- `ADVAPI32!RevertToSelf` at `0x10151dccf`
- `ADVAPI32!RevertToSelf` at `0x10151ef90`
- `ADVAPI32!RevertToSelf` at `0x10151d41b`
- `ADVAPI32!RevertToSelf` at `0x10151d56a`
- `ADVAPI32!RevertToSelf` at `0x10151d6ab`
- `ADVAPI32!RevertToSelf` at `0x10151d7ef`
- `ADVAPI32!RevertToSelf` at `0x10151d892`
- `ADVAPI32!RevertToSelf` at `0x10151dad5`
- `ADVAPI32!RevertToSelf` at `0x10151dc1b`
- `ADVAPI32!RevertToSelf` at `0x10151dccf`
- `ADVAPI32!RevertToSelf` at `0x10151ef90`
- `ADVAPI32!GetSecurityInfo` at `0x10151e480`
- `ADVAPI32!GetSecurityInfo` at `0x10151e480`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10151ced1`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10151cf3d`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10151cf63`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10151d4f3`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10151de8f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151d46c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151d5bb`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151d6fc`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151d840`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151d8e3`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151db44`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151dc6c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151dd20`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151efe1`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151d46c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151d5bb`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151d6fc`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151d840`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151d8e3`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151db44`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151dc6c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151dd20`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10151efe1`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151d509`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151d7b0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151d99c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151d9d7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151da7b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151dec0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151df58`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151d509`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151d7b0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151d99c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151d9d7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151da7b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151dec0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10151df58`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151d09c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151d0ea`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151d28d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151d461`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151d5b0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151d64b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151d6f1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151d835`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151d8d8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151db39`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151dc61`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151dd15`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10151efd6`

## string_xrefs

- `0x10151ef83`: `CUserInstanceHelper::FCopySysDB`
- `0x10151daf2`: `CopyFile`
- `0x10151e2f2`: `CreateProcessAsUser`
- `0x10151d69e`: `SHGetFolderPath`
- `0x10151d2c4`: `RegOpenKeyEx`
- `0x10151d611`: `SHGetFolderPathW`
- `0x10151d3b0`: `\Template Data`
- `0x10151e23f`: `SeIncreaseQuotaPrivilege`
- `0x10151e22e`: `SeCreateTokenPrivilege`
- `0x10151d25d`: `SHELL32.DLL`
- `0x10151e250`: `SeAssignPrimaryTokenPrivilege`
- `0x10151d641`: `lpSHGetFolderPath`
- `0x10151d283`: `hiDll`
- `0x10151d44e`: `sql\ntdbms\msql\security\inc\seccontext.h`
- `0x10151d59d`: `sql\ntdbms\msql\security\inc\seccontext.h`
- `0x10151d6de`: `sql\ntdbms\msql\security\inc\seccontext.h`
- `0x10151d822`: `sql\ntdbms\msql\security\inc\seccontext.h`
- `0x10151d8c5`: `sql\ntdbms\msql\security\inc\seccontext.h`
- `0x10151db26`: `sql\ntdbms\msql\security\inc\seccontext.h`
- `0x10151dc4e`: `sql\ntdbms\msql\security\inc\seccontext.h`
- `0x10151dd02`: `sql\ntdbms\msql\security\inc\seccontext.h`
- `0x10151efc3`: `sql\ntdbms\msql\security\inc\seccontext.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=46
__int64 __fastcall StartChildInstanceAndAttachDb(
        struct IMetadataAccess *a1,
        wchar_t *a2,
        __int64 a3,
        wchar_t *a4,
        unsigned int a5)
{
  int *v7; // r12
  __int64 v8; // rbx
  unsigned __int16 MasterDbId; // ax
  __int64 v10; // rax
  void *v11; // r13
  __int64 result; // rax
  void *v13; // rax
  unsigned int v14; // r8d
  int v15; // r14d
  int v16; // ecx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  SuperLatchInfo *v19; // rbx
  unsigned int ChildInstanceName; // r15d
  SuperLatchInfo *v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  HMODULE v24; // r15
  unsigned int v25; // eax
  const wchar_t *v26; // rcx
  __int64 v27; // rcx
  _WORD *v28; // rax
  __int64 v29; // rax
  unsigned int v30; // r8d
  __int64 v31; // r13
  __int64 v32; // rdx
  char *v33; // rcx
  __int64 v34; // rax
  signed __int64 v35; // r9
  __int16 v36; // r8
  char *v37; // rax
  DWORD LastError; // eax
  SuperLatchInfo *v39; // rbx
  __int64 v40; // rbx
  struct __crt_locale_pointers *DefaultLocale; // rax
  signed int v42; // eax
  DWORD v43; // eax
  unsigned int v44; // ebx
  void *v45; // rax
  unsigned int v46; // eax
  DWORD v47; // eax
  SuperLatchInfo *v48; // rbx
  __int64 v49; // rax
  struct __crt_locale_pointers *v50; // rax
  DWORD v51; // eax
  unsigned int v52; // eax
  DWORD v53; // eax
  __int64 *v54; // r15
  __int64 v55; // r12
  struct __crt_locale_pointers *v56; // rax
  signed int v57; // eax
  struct __crt_locale_pointers *v58; // rax
  int v59; // eax
  struct __crt_locale_pointers *v60; // rax
  signed int v61; // eax
  const wchar_t *v62; // rcx
  __int64 v63; // rcx
  __int16 *v64; // rax
  __int64 v65; // rax
  int v66; // ebx
  unsigned int v67; // r8d
  __int64 v68; // rdx
  char *v69; // rcx
  __int64 v70; // rax
  signed __int64 v71; // r9
  __int16 v72; // r8
  char *v73; // rax
  int v74; // r15d
  DWORD v75; // eax
  DWORD v76; // eax
  unsigned int v77; // eax
  SuperLatchInfo *v78; // rbx
  __int64 v79; // rcx
  WCHAR *v80; // rax
  __int64 v81; // rdi
  WCHAR *v82; // rcx
  char *v83; // rdx
  WCHAR v84; // ax
  WCHAR *v85; // rax
  __int64 v86; // rdi
  __int64 v87; // rbx
  struct __crt_locale_pointers *v88; // rax
  int v89; // eax
  __int64 v90; // rbx
  struct __crt_locale_pointers *v91; // rax
  unsigned int v92; // r8d
  const wchar_t *v93; // rcx
  SuperLatchInfo *v94; // rbx
  __int64 v95; // rbx
  __int64 v96; // rax
  __int64 v97; // rcx
  __int64 v98; // rbx
  __int64 v99; // rdx
  void *v100; // rax
  DWORD v101; // eax
  SuperLatchInfo *v102; // rbx
  DWORD SecurityInfo; // ebx
  SuperLatchInfo *v104; // rbx
  __int64 v105; // rbx
  __int64 v106; // rax
  __int64 v107; // rcx
  __int64 v108; // rbx
  __int64 v109; // rdx
  SuperLatchInfo *v110; // rbx
  char *v111; // rbx
  DWORD v112; // eax
  DWORD v113; // eax
  SuperLatchInfo *v114; // rbx
  SuperLatchInfo *v115; // rbx
  __int64 v116; // rdi
  PSID v117; // r15
  SuperLatchInfo *v118; // rbx
  unsigned int v119; // edi
  SuperLatchInfo *v120; // rbx
  SuperLatchInfo *v121; // rbx
  DWORD v122; // eax
  SuperLatchInfo *v123; // rbx
  SuperLatchInfo *v124; // rbx
  LPSECURITY_ATTRIBUTES lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  HKEY v126; // [rsp+70h] [rbp-90h] BYREF
  int *v127; // [rsp+78h] [rbp-88h]
  __int64 v128; // [rsp+80h] [rbp-80h] BYREF
  SuperLatchInfo *v129; // [rsp+88h] [rbp-78h]
  __int64 v130; // [rsp+90h] [rbp-70h]
  int v131; // [rsp+98h] [rbp-68h]
  __int64 *v132; // [rsp+A0h] [rbp-60h]
  __int64 v133; // [rsp+A8h] [rbp-58h]
  int v134; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE v135; // [rsp+B8h] [rbp-48h]
  char v136; // [rsp+C0h] [rbp-40h]
  unsigned int v137; // [rsp+C8h] [rbp-38h] BYREF
  int v138; // [rsp+D0h] [rbp-30h]
  HANDLE hObject; // [rsp+D8h] [rbp-28h]
  int v140; // [rsp+E0h] [rbp-20h]
  HANDLE hProcess; // [rsp+E8h] [rbp-18h]
  HANDLE v142; // [rsp+F0h] [rbp-10h] BYREF
  int v143; // [rsp+F8h] [rbp-8h]
  DWORD v144; // [rsp+FCh] [rbp-4h] BYREF
  PSID Sid; // [rsp+100h] [rbp+0h]
  int v146; // [rsp+108h] [rbp+8h]
  HANDLE v147; // [rsp+110h] [rbp+10h]
  char v148[8]; // [rsp+118h] [rbp+18h] BYREF
  int *v149; // [rsp+120h] [rbp+20h]
  DWORD v150; // [rsp+128h] [rbp+28h] BYREF
  PACL NewAcl; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *v152; // [rsp+138h] [rbp+38h] BYREF
  __int64 v153; // [rsp+140h] [rbp+40h]
  wchar_t *v154; // [rsp+148h] [rbp+48h]
  unsigned int v155; // [rsp+150h] [rbp+50h]
  int v156; // [rsp+154h] [rbp+54h]
  wchar_t *v157; // [rsp+158h] [rbp+58h]
  int v158; // [rsp+160h] [rbp+60h]
  DWORD dwProcessId[2]; // [rsp+164h] [rbp+64h] BYREF
  int v160; // [rsp+16Ch] [rbp+6Ch]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+170h] [rbp+70h] BYREF
  int v162; // [rsp+190h] [rbp+90h] BYREF
  __int64 v163; // [rsp+198h] [rbp+98h]
  int v164; // [rsp+1A0h] [rbp+A0h] BYREF
  int v165; // [rsp+1A4h] [rbp+A4h]
  __int64 v166; // [rsp+1A8h] [rbp+A8h]
  int v167; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v168; // [rsp+1B8h] [rbp+B8h]
  __int64 v169; // [rsp+1C0h] [rbp+C0h]
  __int64 v170; // [rsp+1C8h] [rbp+C8h]
  __int64 v171; // [rsp+1D0h] [rbp+D0h]
  bool v172; // [rsp+1E0h] [rbp+E0h]
  int v173; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v174; // [rsp+1F8h] [rbp+F8h]
  int v175; // [rsp+200h] [rbp+100h] BYREF
  int v176; // [rsp+204h] [rbp+104h]
  __int64 v177; // [rsp+208h] [rbp+108h]
  int v178; // [rsp+210h] [rbp+110h] BYREF
  __int64 v179; // [rsp+218h] [rbp+118h]
  __int64 v180; // [rsp+220h] [rbp+120h]
  __int64 v181; // [rsp+228h] [rbp+128h]
  __int64 v182; // [rsp+230h] [rbp+130h]
  bool v183; // [rsp+240h] [rbp+140h]
  PACL ppDacl; // [rsp+250h] [rbp+150h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+258h] [rbp+158h] BYREF
  struct _FILETIME CreationTime; // [rsp+260h] [rbp+160h] BYREF
  __int64 v187; // [rsp+268h] [rbp+168h]
  HANDLE Handles[2]; // [rsp+270h] [rbp+170h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+280h] [rbp+180h] BYREF
  struct _FILETIME ExitTime; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v191; // [rsp+2B8h] [rbp+1B8h]
  struct _FILETIME UserTime; // [rsp+2C0h] [rbp+1C0h] BYREF
  struct _FILETIME KernelTime; // [rsp+2C8h] [rbp+1C8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+2D0h] [rbp+1D0h] BYREF
  HANDLE v195; // [rsp+340h] [rbp+240h] BYREF
  int v196; // [rsp+348h] [rbp+248h]
  PVOID Buffer; // [rsp+350h] [rbp+250h]
  __int64 v198; // [rsp+358h] [rbp+258h]
  int v199; // [rsp+360h] [rbp+260h]
  HANDLE LsaHandle; // [rsp+368h] [rbp+268h]
  _OWORD FileInformation[2]; // [rsp+6D0h] [rbp+5D0h] BYREF
  int v202; // [rsp+6F0h] [rbp+5F0h]
  _QWORD v203[5]; // [rsp+6F8h] [rbp+5F8h] BYREF
  wchar_t Buf1[136]; // [rsp+720h] [rbp+620h] BYREF
  wchar_t PathName[264]; // [rsp+830h] [rbp+730h] BYREF
  _WORD v206[264]; // [rsp+A40h] [rbp+940h] BYREF
  WCHAR ApplicationName[264]; // [rsp+C50h] [rbp+B50h] BYREF
  __int16 v208; // [rsp+E60h] [rbp+D60h] BYREF
  char v209[526]; // [rsp+E62h] [rbp+D62h] BYREF
  wchar_t v210[264]; // [rsp+1070h] [rbp+F70h] BYREF
  WCHAR FileName[264]; // [rsp+1280h] [rbp+1180h] BYREF
  wchar_t v212[256]; // [rsp+1490h] [rbp+1390h] BYREF
  wchar_t v213[264]; // [rsp+1690h] [rbp+1590h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+18A0h] [rbp+17A0h] BYREF
  WCHAR CommandLine[1824]; // [rsp+1AB0h] [rbp+19B0h] BYREF

  v191 = -2;
  v7 = *(int **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset)
                           + 120LL)
               + 264LL);
  v149 = v7;
  v8 = (*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)a1 + 16LL))(a1);
  MasterDbId = GetMasterDbId();
  v10 = g_dbtableFactory[4](MasterDbId);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 280LL))(v8, *(_QWORD *)(v10 + 4624));
  v140 = 0;
  hProcess = (HANDLE)-1LL;
  v138 = 0;
  hObject = (HANDLE)-1LL;
  v142 = 0;
  memset_0(v209, 0, 0x208u);
  v137 = 0;
  v11 = (void *)(*(__int64 (__fastcall **)(int *, unsigned int *))(*(_QWORD *)v7 + 408LL))(v7, &v137);
  Sid = v11;
  LODWORD(v127) = 0;
  if ( !*(_WORD *)((*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf)
                 + 252) )
    return 15383;
  if ( *((_DWORD *)s_pServerConf + 2) != 3 )
    return 15376;
  v13 = (void *)(*(__int64 (__fastcall **)(int *))(*(_QWORD *)v7 + 376LL))(v7);
  result = FIsValidLoginForUserInstance(v13, v11, v14, 0);
  if ( !(_DWORD)result )
  {
    v208 = 0;
    v131 = 135;
    v129 = 0;
    v130 = 0;
    v128 = 0;
    v132 = &v128;
    v133 = 0x400000000LL;
    v15 = LatchBase::AcquireInternal(&v128, 4, 0xFFFFFFFFLL);
    LODWORD(v133) = v15;
    v187 = (*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)a1 + 128LL))(a1);
    v153 = 258;
    v156 = 0;
    *(_QWORD *)dwProcessId = 0;
    v160 = 0;
    v152 = Buf1;
    v154 = a4;
    v155 = a5;
    v157 = v210;
    v158 = 522;
    if ( (*(unsigned __int8 (__fastcall **)(__int64, wchar_t **, void *, _QWORD))(*(_QWORD *)v187 + 8LL))(
           v187,
           &v152,
           v11,
           v137) )
    {
      v16 = v153;
      if ( ((unsigned int)v153 & 0xFFFFFFFE) > 0x100 )
      {
        utassert_fail(1u, "(attrChildInst.cbInstName / sizeof(WCHAR)) <= (x_cwchMAXSSWNAME)", "secusrinst.cpp", 2145, 0);
        v16 = v153;
      }
      v17 = v16 & 0xFFFFFFFE;
      if ( v17 >= 0x102 )
        _report_rangecheckfailure();
      *(wchar_t *)((char *)Buf1 + v17) = 0;
      v18 = v155;
      if ( v155 >= a5 )
      {
        utassert_fail(1u, "(attrChildInst.cbInstPipeName) < (cbInstancePipeName)", "secusrinst.cpp", 2147, 0);
        v18 = v155;
      }
      a4[v18 >> 1] = 0;
      if ( (unsigned int)CUserInstanceHelper::FIsProcessAlive(dwProcessId[0], (struct SQLDATE *)&dwProcessId[1]) )
        goto LABEL_13;
    }
    else
    {
      ChildInstanceName = GenerateChildInstanceName(Buf1, 0x102u, a4, a5);
      if ( ChildInstanceName )
      {
        if ( v15 )
        {
          LatchBase::ReleaseInternal(&v128, 4);
          LODWORD(v133) = 0;
        }
        if ( (v130 & 0x40) != 0 )
        {
          v21 = v129;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
          {
            if ( *((_QWORD *)v21 + 1) )
              TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v21 + 2), v21);
            SuperLatchInfo::Destroy(v21);
          }
        }
        return ChildInstanceName;
      }
      v22 = -1;
      do
        ++v22;
      while ( Buf1[v22] );
      LODWORD(v153) = 2 * v22;
      v23 = -1;
      do
        ++v23;
      while ( a4[v23] );
      v155 = 2 * v23;
    }
    v126 = 0;
    v144 = 522;
    v150 = 522;
    v24 = DBLoadLibraryA("SHELL32.DLL", 1);
    if ( !v24 )
      utassert_fail(1u, "hiDll", "secusrinst.cpp", 2216, 0);
    v25 = IniRegOpenKeyExW(-2147483646, (int)qword_102ECFB00 + 44822, 0, 1, &v126);
    if ( v25 )
    {
      v26 = L"RegOpenKeyEx";
LABEL_45:
      CSECErrorRingBufferManager::StoreRecord(
        v26,
        L"StartChildInstanceAndAttachDb",
        v25,
        CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
        0);
      if ( v126 )
        IniRegCloseKey();
      if ( v15 )
      {
LABEL_185:
        LatchBase::ReleaseInternal(&v128, 4);
        LODWORD(v133) = 0;
      }
LABEL_186:
      if ( (v130 & 0x40) != 0 )
      {
        v78 = v129;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
        {
          if ( *((_QWORD *)v78 + 1) )
            TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v78 + 2), v78);
          SuperLatchInfo::Destroy(v78);
        }
      }
      return 15368;
    }
    v25 = IniRegQueryValueExW((int)v126, (int)L"SQLDataRoot", 0, 0, (LPBYTE)v206, &v150);
    if ( v25 )
    {
      v26 = L"RegQueryValueEx";
      goto LABEL_45;
    }
    v206[260] = 0;
    v27 = 261;
    v28 = v206;
    do
    {
      if ( !*v28 )
        break;
      ++v28;
      --v27;
    }
    while ( v27 );
    v29 = 261 - v27;
    if ( !v27 )
      v29 = 0;
    v30 = -2147024809;
    if ( !v27 )
      goto LABEL_443;
    v31 = 2147483646;
    v32 = 261 - v29;
    v33 = (char *)&v206[v29];
    if ( v29 != 261 )
    {
      v34 = 2147483646;
      v35 = (char *)L"\\Template Data" - v33;
      do
      {
        if ( !v34 )
          break;
        v36 = *(_WORD *)&v33[v35];
        if ( !v36 )
          break;
        *(_WORD *)v33 = v36;
        v33 += 2;
        --v34;
        --v32;
      }
      while ( v32 );
    }
    v37 = v33 - 2;
    if ( v32 )
      v37 = v33;
    *(_WORD *)v37 = 0;
    v30 = -2147024774;
    if ( v32 )
    {
      v134 = 0;
      v135 = (HANDLE)-1LL;
      v136 = 0;
      if ( !(unsigned int)CSECAutoImpersonate::Impersonate((CSECAutoImpersonate *)&v134) )
      {
        if ( RevertToSelf() )
        {
          SOS_Task::MaintainToken(0);
          v136 = 0;
        }
        else
        {
          LastError = GetLastError();
          utassert_fail(
            1u,
            "false",
            `CSECAutoImpersonate::Revert'::`7'::szAssertFilename,
            631,
            "RevertToSelf failed: %d",
            LastError);
          SQLExit(388);
        }
        if ( v134 && (char *)v135 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          CloseHandle(v135);
          v134 = 0;
        }
        if ( v126 )
          IniRegCloseKey();
        if ( v15 )
        {
          LatchBase::ReleaseInternal(&v128, 4);
          LODWORD(v133) = 0;
        }
        if ( (v130 & 0x40) != 0 )
        {
          v39 = v129;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
          {
            if ( *((_QWORD *)v39 + 1) )
              TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v39 + 2), v39);
            SuperLatchInfo::Destroy(v39);
          }
        }
        return 15369;
      }
      v40 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
      DefaultLocale = GetDefaultLocale();
      v42 = StringCchPrintf_lW(v213, 0x105u, L"%s\\%s", DefaultLocale, L"Microsoft\\Microsoft SQL Server Data", v40);
      if ( v42 < 0 )
      {
        _mm_lfence();
        CSECErrorRingBufferManager::StoreRecord(
          L"StringCchPrintf",
          L"StartChildInstanceAndAttachDb",
          v42,
          CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
          0);
        if ( RevertToSelf() )
        {
LABEL_84:
          SOS_Task::MaintainToken(0);
          v136 = 0;
        }
        else
        {
LABEL_85:
          v43 = GetLastError();
          utassert_fail(
            1u,
            "false",
            `CSECAutoImpersonate::Revert'::`7'::szAssertFilename,
            631,
            "RevertToSelf failed: %d",
            v43);
          SQLExit(388);
        }
        if ( v134 && (char *)v135 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          CloseHandle(v135);
          v134 = 0;
        }
        if ( v126 )
          IniRegCloseKey();
        if ( !v15 )
          goto LABEL_448;
        goto LABEL_447;
      }
      lpSHGetFolderPath = (int (*)(struct HWND__ *, int, void *, unsigned int, wchar_t *))GetProcAddress(
                                                                                            v24,
                                                                                            "SHGetFolderPathW");
      v44 = 0;
      if ( !lpSHGetFolderPath )
        utassert_fail(1u, "lpSHGetFolderPath", "secusrinst.cpp", 2283, 0);
      v45 = (void *)(*(__int64 (__fastcall **)(int *))(*(_QWORD *)v7 + 376LL))(v7);
      v46 = lpSHGetFolderPath(0, 32796, v45, 0, v210);
      if ( v46 )
      {
        CSECErrorRingBufferManager::StoreRecord(
          L"SHGetFolderPath",
          L"StartChildInstanceAndAttachDb",
          v46,
          CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
          0);
        if ( RevertToSelf() )
        {
          SOS_Task::MaintainToken(0);
          v136 = 0;
        }
        else
        {
          v47 = GetLastError();
          utassert_fail(
            1u,
            "false",
            `CSECAutoImpersonate::Revert'::`7'::szAssertFilename,
            631,
            "RevertToSelf failed: %d",
            v47);
          SQLExit(388);
        }
        if ( v134 && (char *)v135 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          CloseHandle(v135);
          v134 = 0;
        }
        if ( v126 )
          IniRegCloseKey();
        if ( v15 )
        {
          LatchBase::ReleaseInternal(&v128, 4);
          LODWORD(v133) = 0;
        }
        if ( (v130 & 0x40) != 0 )
        {
          v48 = v129;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
          {
            if ( *((_QWORD *)v48 + 1) )
              TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v48 + 2), v48);
            SuperLatchInfo::Destroy(v48);
          }
        }
        return 15382;
      }
      v157 = v210;
      v49 = -1;
      do
        ++v49;
      while ( v210[v49] );
      v158 = 2 * v49;
      v50 = GetDefaultLocale();
      if ( (int)StringCchPrintf_lW(PathName, 0x105u, L"%s\\%s", v50, v210, v213) >= 0 )
      {
        v52 = CUserInstanceHelper::FCreateDirAndSubDir(PathName, 0);
        if ( v52 && v52 != 183 )
        {
          if ( RevertToSelf() )
          {
            SOS_Task::MaintainToken(0);
            v136 = 0;
          }
          else
          {
            v53 = GetLastError();
            utassert_fail(
              1u,
              "false",
              `CSECAutoImpersonate::Revert'::`7'::szAssertFilename,
              631,
              "RevertToSelf failed: %d",
              v53);
            SQLExit(388);
          }
          if ( v134 && (char *)v135 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            CloseHandle(v135);
            v134 = 0;
          }
          if ( v126 )
            IniRegCloseKey();
          if ( v15 )
          {
LABEL_436:
            LatchBase::ReleaseInternal(&v128, 4);
            LODWORD(v133) = 0;
          }
LABEL_437:
          if ( (v130 & 0x40) != 0 )
          {
            v123 = v129;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
            {
              if ( *((_QWORD *)v123 + 1) )
                TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v123 + 2), v123);
              SuperLatchInfo::Destroy(v123);
            }
          }
          return 15370;
        }
        v203[0] = L"master.mdf";
        v203[1] = L"mastlog.ldf";
        v203[2] = L"msdbdata.mdf";
        v203[3] = L"msdblog.ldf";
        v143 = 0;
        v54 = v203;
        while ( 1 )
        {
          memset(FileInformation, 0, sizeof(FileInformation));
          v202 = 0;
          v55 = *v54;
          v56 = GetDefaultLocale();
          v57 = StringCchPrintf_lW(ExistingFileName, 0x105u, L"%s\\%s", v56, v206, v55);
          _mm_lfence();
          if ( v57 < 0 )
            goto LABEL_426;
          v58 = GetDefaultLocale();
          v57 = StringCchPrintf_lW(FileName, 0x105u, L"%s\\%s", v58, PathName, v55);
          if ( v57 < 0 )
          {
            _mm_lfence();
LABEL_426:
            v62 = L"StringCchPrintf";
            goto LABEL_427;
          }
          if ( GetFileAttributesExW(FileName, GetFileExInfoStandard, FileInformation) )
          {
            v59 = v143;
          }
          else
          {
            v57 = GetLastError();
            if ( v57 != 2 )
            {
              v62 = L"GetFileAttributesEx";
LABEL_427:
              CSECErrorRingBufferManager::StoreRecord(
                v62,
                L"CUserInstanceHelper::FCopySysDB",
                v57,
                CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
                0);
              if ( RevertToSelf() )
              {
                SOS_Task::MaintainToken(0);
                v136 = 0;
              }
              else
              {
                v122 = GetLastError();
                utassert_fail(
                  1u,
                  "false",
                  `CSECAutoImpersonate::Revert'::`7'::szAssertFilename,
                  631,
                  "RevertToSelf failed: %d",
                  v122);
                SQLExit(388);
              }
              if ( v134 && (char *)v135 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(v135);
                v134 = 0;
              }
              if ( v126 )
                IniRegCloseKey();
              if ( !v15 )
                goto LABEL_437;
              goto LABEL_436;
            }
            if ( !CopyFileW(ExistingFileName, FileName, 0) )
            {
              v57 = GetLastError();
              v62 = L"CopyFile";
              goto LABEL_427;
            }
            v59 = 1;
            v143 = 1;
          }
          ++v44;
          ++v54;
          if ( v44 >= 4 )
          {
            if ( v59 )
            {
              v60 = GetDefaultLocale();
              LODWORD(lpThreadAttributes) = 1617;
              v61 = StringCchPrintf_lW(v212, 0x100u, L" -T%d", v60, lpThreadAttributes);
              if ( v61 < 0 )
              {
                _mm_lfence();
                CSECErrorRingBufferManager::StoreRecord(
                  L"StringCchPrintf",
                  L"StartChildInstanceAndAttachDb",
                  v61,
                  CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
                  0);
                if ( !RevertToSelf() )
                  goto LABEL_85;
                goto LABEL_84;
              }
              v63 = 261;
              v64 = &v208;
              do
              {
                if ( !*v64 )
                  break;
                ++v64;
                --v63;
              }
              while ( v63 );
              v65 = 261 - v63;
              if ( !v63 )
                v65 = 0;
              v66 = -2147024809;
              v67 = -2147024809;
              if ( v63 )
              {
                v68 = 261 - v65;
                v69 = &v209[2 * v65 - 2];
                if ( v65 != 261 )
                {
                  v70 = 2147483646;
                  v71 = (char *)v212 - v69;
                  do
                  {
                    if ( !v70 )
                      break;
                    v72 = *(_WORD *)&v69[v71];
                    if ( !v72 )
                      break;
                    *(_WORD *)v69 = v72;
                    v69 += 2;
                    --v70;
                    --v68;
                  }
                  while ( v68 );
                }
                v73 = v69 - 2;
                if ( v68 )
                  v73 = v69;
                *(_WORD *)v73 = 0;
                v67 = -2147024774;
                if ( v68 )
                {
                  v74 = 1;
                  goto LABEL_175;
                }
              }
              _mm_lfence();
              CSECErrorRingBufferManager::StoreRecord(
                L"StringCchCat",
                L"StartChildInstanceAndAttachDb",
                v67,
                CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
                0);
              if ( RevertToSelf() )
              {
                SOS_Task::MaintainToken(0);
                v136 = 0;
              }
              else
              {
                v75 = GetLastError();
                utassert_fail(
                  1u,
                  "false",
                  `CSECAutoImpersonate::Revert'::`7'::szAssertFilename,
                  631,
                  "RevertToSelf failed: %d",
                  v75);
                SQLExit(388);
              }
              if ( v134 && (char *)v135 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(v135);
                v134 = 0;
              }
LABEL_170:
              if ( v126 )
                IniRegCloseKey();
              if ( !v15 )
                goto LABEL_448;
              goto LABEL_447;
            }
            v66 = -2147024809;
            v74 = (int)v127;
LABEL_175:
            if ( RevertToSelf() )
            {
              SOS_Task::MaintainToken(0);
              v136 = 0;
            }
            else
            {
              v76 = GetLastError();
              utassert_fail(
                1u,
                "false",
                `CSECAutoImpersonate::Revert'::`7'::szAssertFilename,
                631,
                "RevertToSelf failed: %d",
                v76);
              SQLExit(388);
            }
            if ( v134 && (char *)v135 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            {
              CloseHandle(v135);
              v134 = 0;
            }
            v77 = IniRegQueryValueExW((int)v126, (int)L"SQLBinRoot", 0, 0, (LPBYTE)ApplicationName, &v144);
            if ( v77 )
            {
              CSECErrorRingBufferManager::StoreRecord(
                L"RegQueryValueEx",
                L"StartChildInstanceAndAttachDb",
                v77,
                CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
                0);
              if ( v126 )
                IniRegCloseKey();
              if ( !v15 )
                goto LABEL_186;
              goto LABEL_185;
            }
            ApplicationName[260] = 0;
            v79 = 261;
            v80 = ApplicationName;
            do
            {
              if ( !*v80 )
                break;
              ++v80;
              --v79;
            }
            while ( v79 );
            if ( !v79 )
              goto LABEL_424;
            v81 = v79;
            v82 = &ApplicationName[261 - v79];
            v83 = (char *)((char *)L"\\sqlservr.exe" - (char *)v82);
            do
            {
              if ( !v31 )
                break;
              v84 = *(_WORD *)&v83[(_QWORD)v82];
              if ( !v84 )
                break;
              *v82++ = v84;
              --v31;
              --v81;
            }
            while ( v81 );
            v85 = v82 - 1;
            if ( v81 )
              v85 = v82;
            *v85 = 0;
            v66 = -2147024774;
            if ( !v81 )
            {
LABEL_424:
              v92 = v66;
              v93 = L"StringCchCat";
              goto LABEL_208;
            }
            if ( v74 )
            {
              v86 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
              v87 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
              v88 = GetDefaultLocale();
              v89 = StringCchPrintf_lW(
                      CommandLine,
                      0x71Du,
                      L"\"%s\" -U\"%s\" -d\"%s\"\\master.mdf -l\"%s\"\\mastlog.ldf -e\"%s\"\\error.log -c -K -S%s -s%s -w%u %s",
                      v88,
                      ApplicationName,
                      v206,
                      PathName,
                      PathName,
                      PathName,
                      v86,
                      Buf1,
                      *(_DWORD *)(v87 + 244),
                      &v208);
            }
            else
            {
              v90 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
              v91 = GetDefaultLocale();
              v89 = StringCchPrintf_lW(
                      CommandLine,
                      0x71Du,
                      L"\"%s\" -U\"%s\" -d\"%s\"\\master.mdf -l\"%s\"\\mastlog.ldf -e\"%s\"\\error.log -c -S%s -s%s %s",
                      v91,
                      ApplicationName,
                      v206,
                      PathName,
                      PathName,
                      PathName,
                      v90,
                      Buf1,
                      &v208);
            }
            if ( v89 < 0 )
            {
              v92 = v89;
              v93 = L"StringCchPrintf";
LABEL_208:
              _mm_lfence();
              CSECErrorRingBufferManager::StoreRecord(
                v93,
                L"StartChildInstanceAndAttachDb",
                v92,
                CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
                0);
              goto LABEL_170;
            }
            *(_OWORD *)&StartupInfo.cb = 0;
            memset(&StartupInfo.lpTitle, 0, 80);
            StartupInfo.cb = 104;
            StartupInfo.lpDesktop = (LPWSTR)&szPassword;
            if ( !(unsigned int)CreateUserInstanceEvent(Buf1, &v142) )
            {
              if ( v126 )
                IniRegCloseKey();
              if ( v15 )
              {
                LatchBase::ReleaseInternal(&v128, 4);
                LODWORD(v133) = 0;
              }
              if ( (v130 & 0x40) != 0 )
              {
                v94 = v129;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
                {
                  if ( *((_QWORD *)v94 + 1) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v94 + 2), v94);
                  SuperLatchInfo::Destroy(v94);
                }
              }
              return 15371;
            }
            v146 = 1;
            v147 = v142;
            Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v162, 1);
            v127 = &v164;
            v167 = 536871408;
            v168 = 0;
            v170 = 0;
            v169 = 0;
            v171 = 0;
            v172 = 0;
            v95 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v96 = *(_QWORD *)(v95 + 256);
            if ( !v96 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v96 = *(_QWORD *)(v95 + 256);
            }
            v97 = *(_QWORD *)(v96 + 600);
            if ( v97 )
              v172 = (unsigned int)SOS_Task::PushWait(v97, &v167) == 0;
            v98 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v99 = *(_QWORD *)(v98 + 256);
            if ( !v99 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v99 = *(_QWORD *)(v98 + 256);
            }
            v166 = v99;
            v165 = (*(_DWORD *)(v99 + 800) >> 11) & 1;
            if ( v165 || (*(_BYTE *)(v99 + 800) & 4) == 0 )
            {
              v164 = 1;
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v99 + 608) + 8LL))(*(_QWORD *)(v99 + 608));
            }
            else
            {
              v164 = 0;
            }
            v195 = (HANDLE)-1LL;
            v196 = 0;
            Buffer = 0;
            v198 = 0;
            v199 = 0;
            LsaHandle = (HANDLE)-1LL;
            CAutoLogin::SetPrivilege(L"SeCreateTokenPrivilege", 1);
            CAutoLogin::SetPrivilege(L"SeIncreaseQuotaPrivilege", 1);
            CAutoLogin::SetPrivilege(L"SeAssignPrimaryTokenPrivilege", 1);
            SOS_AutoUnhookDebugBreak::SOS_AutoUnhookDebugBreak(v148, 1);
            SOS_AutoUnhookDebugBreak::Unhook(v148);
            v100 = (void *)(*(__int64 (__fastcall **)(int *))(*(_QWORD *)v149 + 376LL))(v149);
            if ( !CreateProcessAsUserW(
                    v100,
                    ApplicationName,
                    CommandLine,
                    0,
                    0,
                    0,
                    0x8000004u,
                    0,
                    0,
                    &StartupInfo,
                    &ProcessInformation) )
            {
              v101 = GetLastError();
              CSECErrorRingBufferManager::StoreRecord(
                L"CreateProcessAsUser",
                L"StartChildInstanceAndAttachDb",
                v101,
                CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
                0);
              SOS_AutoUnhookDebugBreak::~SOS_AutoUnhookDebugBreak((SOS_AutoUnhookDebugBreak *)v148);
              CAutoLogin::Revert((CAutoLogin *)&v195);
              if ( (char *)v195 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(v195);
              if ( (_DWORD)v198 )
                LsaFreeReturnBuffer(Buffer);
              if ( (char *)LsaHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                LsaDeregisterLogonProcess(LsaHandle);
              Sid = &v164;
              if ( v164 )
              {
                if ( v165 )
                  *(_DWORD *)(v166 + 800) |= 0x800u;
                else
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v166 + 608) + 16LL))(
                    *(_QWORD *)(v166 + 608),
                    v166,
                    1);
              }
              SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v167);
              *(_DWORD *)(v163 + 616) &= ~v162;
              if ( (char *)v142 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(v142);
                v146 = 0;
              }
              if ( v126 )
                IniRegCloseKey();
              if ( v15 )
              {
                LatchBase::ReleaseInternal(&v128, 4);
                LODWORD(v133) = 0;
              }
              if ( (v130 & 0x40) != 0 )
              {
                v102 = v129;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
                {
                  if ( *((_QWORD *)v102 + 1) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v102 + 2), v102);
                  SuperLatchInfo::Destroy(v102);
                }
              }
              return 15372;
            }
            ppDacl = 0;
            NewAcl = 0;
            ppSecurityDescriptor = 0;
            SecurityInfo = GetSecurityInfo(
                             ProcessInformation.hProcess,
                             SE_KERNEL_OBJECT,
                             4u,
                             0,
                             0,
                             &ppDacl,
                             0,
                             &ppSecurityDescriptor);
            if ( !SecurityInfo )
            {
              memset(&pListOfExplicitEntries.grfInheritance, 0, 20);
              *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 0;
              pListOfExplicitEntries.grfAccessPermissions = 4096;
              pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
              pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_NAME;
              pListOfExplicitEntries.Trustee.ptstrName = L"CURRENT_USER";
              SecurityInfo = SetEntriesInAclW(1u, &pListOfExplicitEntries, ppDacl, &NewAcl);
              if ( !SecurityInfo )
              {
                SecurityInfo = SetSecurityInfo(ProcessInformation.hProcess, SE_KERNEL_OBJECT, 4u, 0, 0, NewAcl, 0);
                if ( !SecurityInfo )
                {
                  SecurityInfo = ResumeThread(ProcessInformation.hThread);
                  if ( SecurityInfo != -1 )
                    SecurityInfo = 0;
                }
              }
            }
            if ( ppSecurityDescriptor )
              LocalFree(ppSecurityDescriptor);
            if ( NewAcl )
              LocalFree(NewAcl);
            if ( SecurityInfo )
            {
              TerminateProcess(ProcessInformation.hProcess, 1u);
              SOS_AutoUnhookDebugBreak::~SOS_AutoUnhookDebugBreak((SOS_AutoUnhookDebugBreak *)v148);
              CAutoLogin::Revert((CAutoLogin *)&v195);
              if ( (char *)v195 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(v195);
              if ( (_DWORD)v198 )
                LsaFreeReturnBuffer(Buffer);
              if ( (char *)LsaHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                LsaDeregisterLogonProcess(LsaHandle);
              Sid = &v164;
              if ( v164 )
              {
                if ( v165 )
                  *(_DWORD *)(v166 + 800) |= 0x800u;
                else
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v166 + 608) + 16LL))(
                    *(_QWORD *)(v166 + 608),
                    v166,
                    1);
              }
              SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v167);
              *(_DWORD *)(v163 + 616) &= ~v162;
              if ( (char *)v142 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(v142);
                v146 = 0;
              }
              if ( v126 )
                IniRegCloseKey();
              if ( v15 )
              {
                LatchBase::ReleaseInternal(&v128, 4);
                LODWORD(v133) = 0;
              }
              if ( (v130 & 0x40) != 0 )
              {
                v104 = v129;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
                {
                  if ( *((_QWORD *)v104 + 1) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v104 + 2), v104);
                  SuperLatchInfo::Destroy(v104);
                }
              }
              return 43;
            }
            SOS_AutoUnhookDebugBreak::~SOS_AutoUnhookDebugBreak((SOS_AutoUnhookDebugBreak *)v148);
            CAutoLogin::Revert((CAutoLogin *)&v195);
            if ( (char *)v195 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(v195);
            if ( (_DWORD)v198 )
              LsaFreeReturnBuffer(Buffer);
            if ( (char *)LsaHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              LsaDeregisterLogonProcess(LsaHandle);
            v149 = &v164;
            if ( v164 )
            {
              if ( v165 )
                *(_DWORD *)(v166 + 800) |= 0x800u;
              else
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v166 + 608) + 16LL))(
                  *(_QWORD *)(v166 + 608),
                  v166,
                  1);
            }
            SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v167);
            *(_DWORD *)(v163 + 616) &= ~v162;
            hObject = ProcessInformation.hThread;
            v138 = 1;
            hProcess = ProcessInformation.hProcess;
            v140 = 1;
            Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v173, 1);
            v149 = &v175;
            v178 = 536871408;
            v179 = 0;
            v181 = 0;
            v180 = 0;
            v182 = 0;
            v183 = 0;
            v105 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            v106 = *(_QWORD *)(v105 + 256);
            if ( !v106 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v106 = *(_QWORD *)(v105 + 256);
            }
            v107 = *(_QWORD *)(v106 + 600);
            if ( v107 )
              v183 = (unsigned int)SOS_Task::PushWait(v107, &v178) == 0;
            v108 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            v109 = *(_QWORD *)(v108 + 256);
            if ( !v109 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v109 = *(_QWORD *)(v108 + 256);
            }
            v177 = v109;
            v176 = (*(_DWORD *)(v109 + 800) >> 11) & 1;
            if ( v176 || (*(_BYTE *)(v109 + 800) & 4) == 0 )
            {
              v175 = 1;
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v109 + 608) + 8LL))(*(_QWORD *)(v109 + 608));
            }
            else
            {
              v175 = 0;
            }
            if ( !(unsigned int)CUserInstanceHelper::FModifySDonChildProcess(ProcessInformation.hProcess) )
            {
              Sid = &v175;
              if ( v175 )
              {
                if ( v176 )
                  *(_DWORD *)(v177 + 800) |= 0x800u;
                else
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v177 + 608) + 16LL))(
                    *(_QWORD *)(v177 + 608),
                    v177,
                    1);
              }
              SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v178);
              *(_DWORD *)(v174 + 616) &= ~v173;
              if ( (char *)v142 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(v142);
                v146 = 0;
              }
              if ( v126 )
                IniRegCloseKey();
              if ( v15 )
              {
                LatchBase::ReleaseInternal(&v128, 4);
                LODWORD(v133) = 0;
              }
              if ( (v130 & 0x40) != 0 )
              {
                v110 = v129;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
                {
                  if ( *((_QWORD *)v110 + 1) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v110 + 2), v110);
                  SuperLatchInfo::Destroy(v110);
                }
              }
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hObject);
                v138 = 0;
              }
              if ( (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hProcess);
                v140 = 0;
              }
              return 15381;
            }
            Handles[0] = ProcessInformation.hProcess;
            v111 = (char *)v142;
            Handles[1] = v142;
            v112 = WaitForMultipleObjects(2u, Handles, 0, 0xEA60u);
            if ( v112 == 258 || !v112 )
            {
              Sid = &v175;
              if ( v175 )
              {
                if ( v176 )
                  *(_DWORD *)(v177 + 800) |= 0x800u;
                else
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v177 + 608) + 16LL))(
                    *(_QWORD *)(v177 + 608),
                    v177,
                    1);
              }
              SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v178);
              *(_DWORD *)(v174 + 616) &= ~v173;
              if ( (unsigned __int64)(v111 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                CloseHandle(v111);
                v146 = 0;
              }
              if ( v126 )
                IniRegCloseKey();
              if ( v15 )
              {
                LatchBase::ReleaseInternal(&v128, 4);
                LODWORD(v133) = 0;
              }
              if ( (v130 & 0x40) != 0 )
              {
                v121 = v129;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
                {
                  if ( *((_QWORD *)v121 + 1) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v121 + 2), v121);
                  SuperLatchInfo::Destroy(v121);
                }
              }
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hObject);
                v138 = 0;
              }
              if ( (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hProcess);
                v140 = 0;
              }
              return 15372;
            }
            v149 = &v175;
            if ( v175 )
            {
              if ( v176 )
                *(_DWORD *)(v177 + 800) |= 0x800u;
              else
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v177 + 608) + 16LL))(
                  *(_QWORD *)(v177 + 608),
                  v177,
                  1);
            }
            SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v178);
            *(_DWORD *)(v174 + 616) &= ~v173;
            dwProcessId[0] = ProcessInformation.dwProcessId;
            if ( !GetProcessTimes(ProcessInformation.hProcess, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
            {
              v113 = GetLastError();
              CSECErrorRingBufferManager::StoreRecord(
                L"GetProcessTimes",
                L"StartChildInstanceAndAttachDb",
                v113,
                CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
                0);
              if ( (unsigned __int64)(v111 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                CloseHandle(v111);
                v146 = 0;
              }
              if ( v126 )
                IniRegCloseKey();
              if ( v15 )
              {
                LatchBase::ReleaseInternal(&v128, 4);
                LODWORD(v133) = 0;
              }
              if ( (v130 & 0x40) != 0 )
              {
                v114 = v129;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
                {
                  if ( *((_QWORD *)v114 + 1) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v114 + 2), v114);
                  SuperLatchInfo::Destroy(v114);
                }
              }
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hObject);
                v138 = 0;
              }
              if ( (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hProcess);
                v140 = 0;
              }
              return 15373;
            }
            if ( SQLDATE::ConvertFromFileTime((SQLDATE *)&dwProcessId[1], &CreationTime) )
            {
              if ( (unsigned __int64)(v111 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                CloseHandle(v111);
                v146 = 0;
              }
              if ( v126 )
                IniRegCloseKey();
              if ( v15 )
              {
                LatchBase::ReleaseInternal(&v128, 4);
                LODWORD(v133) = 0;
              }
              if ( (v130 & 0x40) != 0 )
              {
                v115 = v129;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
                {
                  if ( *((_QWORD *)v115 + 1) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v115 + 2), v115);
                  SuperLatchInfo::Destroy(v115);
                }
              }
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hObject);
                v138 = 0;
              }
              if ( (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hProcess);
                v140 = 0;
              }
              return 15366;
            }
            v116 = v187;
            v117 = Sid;
            if ( !(*(unsigned __int8 (__fastcall **)(__int64, PSID, _QWORD, wchar_t **))(*(_QWORD *)v187 + 32LL))(
                    v187,
                    Sid,
                    v137,
                    &v152)
              && !(*(unsigned __int8 (__fastcall **)(__int64, PSID, _QWORD, __int64, wchar_t **))(*(_QWORD *)v116 + 48LL))(
                    v116,
                    v117,
                    v137,
                    28,
                    &v152) )
            {
              if ( (unsigned __int64)(v111 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                CloseHandle(v111);
                v146 = 0;
              }
              if ( v126 )
                IniRegCloseKey();
              if ( v15 )
              {
                LatchBase::ReleaseInternal(&v128, 4);
                LODWORD(v133) = 0;
              }
              if ( (v130 & 0x40) != 0 )
              {
                v118 = v129;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
                {
                  if ( *((_QWORD *)v118 + 1) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v118 + 2), v118);
                  SuperLatchInfo::Destroy(v118);
                }
              }
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hObject);
                v138 = 0;
              }
              if ( (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hProcess);
                v140 = 0;
              }
              return 15374;
            }
            v119 = PopulateUserInstanceInfoInRegistry(v117, v137, (struct MDAttrChildInst *)&v152, CreationTime);
            if ( v119 )
            {
              if ( (unsigned __int64)(v111 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                CloseHandle(v111);
                v146 = 0;
              }
              if ( v126 )
                IniRegCloseKey();
              if ( v15 )
              {
                LatchBase::ReleaseInternal(&v128, 4);
                LODWORD(v133) = 0;
              }
              if ( (v130 & 0x40) != 0 )
              {
                v120 = v129;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
                {
                  if ( *((_QWORD *)v120 + 1) )
                    TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v120 + 2), v120);
                  SuperLatchInfo::Destroy(v120);
                }
              }
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hObject);
                v138 = 0;
              }
              if ( (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hProcess);
                v140 = 0;
              }
              return v119;
            }
            StartSQLWriterService();
            if ( (unsigned __int64)(v111 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              CloseHandle(v111);
              v146 = 0;
            }
            if ( v126 )
              IniRegCloseKey();
LABEL_13:
            if ( v15 )
            {
              LatchBase::ReleaseInternal(&v128, 4);
              LODWORD(v133) = 0;
            }
            if ( (v130 & 0x40) != 0 )
            {
              v19 = v129;
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
              {
                if ( *((_QWORD *)v19 + 1) )
                  TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v19 + 2), v19);
                SuperLatchInfo::Destroy(v19);
              }
            }
            if ( v138 && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            {
              CloseHandle(hObject);
              v138 = 0;
            }
            if ( v140 )
            {
              if ( (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                CloseHandle(hProcess);
                v140 = 0;
              }
            }
            return 0;
          }
        }
      }
      if ( RevertToSelf() )
      {
        SOS_Task::MaintainToken(0);
        v136 = 0;
      }
      else
      {
        v51 = GetLastError();
        utassert_fail(
          1u,
          "false",
          `CSECAutoImpersonate::Revert'::`7'::szAssertFilename,
          631,
          "RevertToSelf failed: %d",
          v51);
        SQLExit(388);
      }
      if ( v134 && (char *)v135 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(v135);
        v134 = 0;
      }
    }
    else
    {
LABEL_443:
      _mm_lfence();
      CSECErrorRingBufferManager::StoreRecord(
        L"StringCchCat",
        L"StartChildInstanceAndAttachDb",
        v30,
        CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
        0);
    }
    if ( v126 )
      IniRegCloseKey();
    if ( !v15 )
    {
LABEL_448:
      if ( (v130 & 0x40) != 0 )
      {
        v124 = v129;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v129 + 6, 0xFFFFFFFF) == 1 )
        {
          if ( *((_QWORD *)v124 + 1) )
            TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*((_QWORD *)v124 + 2), v124);
          SuperLatchInfo::Destroy(v124);
        }
      }
      return 15366;
    }
LABEL_447:
    LatchBase::ReleaseInternal(&v128, 4);
    LODWORD(v133) = 0;
    goto LABEL_448;
  }
  return result;
}

```

## disassembly

```asm
0x10151ce40  push    rbp
0x10151ce42  push    rsi
0x10151ce43  push    rdi
0x10151ce44  push    r12
0x10151ce46  push    r13
0x10151ce48  push    r14
0x10151ce4a  push    r15
0x10151ce4c  lea     rbp, [rsp-2800h]
0x10151ce54  mov     eax, 2900h
0x10151ce59  call    _alloca_probe
0x10151ce5e  sub     rsp, rax
0x10151ce61  mov     [rbp+2830h+var_2678], 0FFFFFFFFFFFFFFFEh
0x10151ce6c  mov     [rsp+2930h+arg_8], rbx
0x10151ce74  mov     rax, cs:__security_cookie
0x10151ce7b  xor     rax, rsp
0x10151ce7e  mov     [rbp+2830h+var_40], rax
0x10151ce85  mov     rdi, r9
0x10151ce88  mov     r15, rcx
0x10151ce8b  mov     rdx, gs:58h
0x10151ce94  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10151ce9b  mov     ecx, [rax]
0x10151ce9d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10151cea4  mov     eax, [rax]
0x10151cea6  add     rax, [rdx+rcx*8]
0x10151ceaa  mov     rax, [rax]
0x10151cead  mov     rcx, [rax+78h]
0x10151ceb1  mov     r12, [rcx+108h]
0x10151ceb8  mov     [rbp+2830h+var_2810], r12
0x10151cebc  mov     rax, [r15]
0x10151cebf  mov     rcx, r15
0x10151cec2  call    qword ptr [rax+10h]
0x10151cec5  mov     rbx, rax
0x10151cec8  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x10151cece  movzx   ecx, ax
0x10151ced1  mov     rdx, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x10151ced8  call    qword ptr [rdx+20h]
0x10151cedb  mov     r8, [rbx]
0x10151cede  mov     rdx, [rax+1210h]
0x10151cee5  mov     rcx, rbx
0x10151cee8  call    qword ptr [r8+118h]
0x10151ceef  xor     ebx, ebx
0x10151cef1  mov     [rbp+2830h+var_2850], ebx
0x10151cef4  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x10151cefb  mov     [rbp+2830h+var_2848], rsi
0x10151ceff  mov     [rbp+2830h+var_2860], ebx
0x10151cf02  mov     [rbp+2830h+hObject], rsi
0x10151cf06  mov     [rbp+2830h+var_2840], rbx
0x10151cf0a  xor     edx, edx; Val
0x10151cf0c  mov     r8d, 208h; Size
0x10151cf12  lea     rcx, [rbp+2830h+var_1ACE]; void *
0x10151cf19  call    memset_0
0x10151cf1e  mov     [rbp+2830h+var_2868], ebx
0x10151cf21  mov     rax, [r12]
0x10151cf25  lea     rdx, [rbp+2830h+var_2868]
0x10151cf29  mov     rcx, r12
0x10151cf2c  call    qword ptr [rax+198h]
0x10151cf32  mov     r13, rax
0x10151cf35  mov     [rbp+2830h+Sid], rax
0x10151cf39  mov     dword ptr [rsp+2930h+var_28B8], ebx
0x10151cf3d  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10151cf44  mov     rcx, [rcx]
0x10151cf47  mov     rdx, [rcx]
0x10151cf4a  call    qword ptr [rdx+1F8h]
0x10151cf50  cmp     [rax+0FCh], bx
0x10151cf57  jnz     short loc_10151CF63
0x10151cf59  mov     eax, 3C17h
0x10151cf5e  jmp     loc_10151F0EA
0x10151cf63  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10151cf6a  mov     rcx, [rax]
0x10151cf6d  cmp     dword ptr [rcx+8], 3
0x10151cf71  jz      short loc_10151CF7D
0x10151cf73  mov     eax, 3C10h
0x10151cf78  jmp     loc_10151F0EA
0x10151cf7d  mov     rax, [r12]
0x10151cf81  mov     rcx, r12
0x10151cf84  call    qword ptr [rax+178h]
0x10151cf8a  xor     r9d, r9d; int
0x10151cf8d  mov     rdx, r13; pSid
0x10151cf90  mov     rcx, rax; TokenHandle
0x10151cf93  call    ?FIsValidLoginForUserInstance@@YAJPEAXPEBEKH@Z; FIsValidLoginForUserInstance(void *,uchar const *,ulong,int)
0x10151cf98  test    eax, eax
0x10151cf9a  jz      short loc_10151CFA1
0x10151cf9c  jmp     loc_10151F0EA
0x10151cfa1  mov     [rbp+2830h+var_1AD0], bx
0x10151cfa8  mov     [rbp+2830h+var_2898], 87h
0x10151cfaf  mov     [rbp+2830h+var_28A8], rbx
0x10151cfb3  mov     [rbp+2830h+var_28A0], rbx
0x10151cfb7  mov     [rbp+2830h+var_28B0], rbx
0x10151cfbb  lea     rax, [rbp+2830h+var_28B0]
0x10151cfbf  mov     [rbp+2830h+var_2890], rax
0x10151cfc3  mov     [rbp+2830h+var_2888], rbx
0x10151cfc7  mov     dword ptr [rbp+2830h+var_2888+4], 4
0x10151cfce  mov     dword ptr [rsp+2930h+lpCurrentDirectory], ebx
0x10151cfd2  mov     [rsp+2930h+lpEnvironment], rbx
0x10151cfd7  mov     qword ptr [rsp+2930h+dwCreationFlags], rbx
0x10151cfdc  mov     [rsp+2930h+bInheritHandles], ebx
0x10151cfe0  mov     [rsp+2930h+lpThreadAttributes], rbx
0x10151cfe5  xor     r9d, r9d
0x10151cfe8  lea     edx, [r9+4]
0x10151cfec  mov     r8d, 0FFFFFFFFh
0x10151cff2  lea     rcx, [rbp+2830h+var_28B0]
0x10151cff6  call    cs:__imp_?AcquireInternal@LatchBase@@AEAA?AW4AcquireResult@1@W4LATCH_TYPE@1@KPEAVLatchSuspendInfo@@PEAUSubLatchInfo@1@W4Releasor@1@PEA_KPEAVSOS_LsAccessCache@@W4LatchYieldBehavior@1@@Z; LatchBase::AcquireInternal(LatchBase::LATCH_TYPE,ulong,LatchSuspendInfo *,LatchBase::SubLatchInfo *,LatchBase::Releasor,unsigned __int64 *,SOS_LsAccessCache *,LatchBase::LatchYieldBehavior)
0x10151cffc  mov     r14d, eax
0x10151cfff  mov     dword ptr [rbp+2830h+var_2888], eax
0x10151d002  mov     rdx, [r15]
0x10151d005  mov     rcx, r15
0x10151d008  call    qword ptr [rdx+80h]
0x10151d00e  mov     rcx, rax
0x10151d011  mov     [rbp+2830h+var_26C8], rax
0x10151d018  mov     [rbp+2830h+var_27F0], 102h
0x10151d020  mov     [rbp+2830h+var_27DC], ebx
0x10151d023  mov     qword ptr [rbp+2830h+dwProcessId], rbx
0x10151d027  mov     [rbp+2830h+var_27C4], ebx
0x10151d02a  lea     rax, [rbp+2830h+Buf1]
0x10151d031  mov     [rbp+2830h+var_27F8], rax
0x10151d035  mov     [rbp+2830h+var_27E8], rdi
0x10151d039  mov     ebx, [rbp+2830h+arg_20]
0x10151d03f  mov     [rbp+2830h+var_27E0], ebx
0x10151d042  lea     rax, [rbp+2830h+var_18C0]
0x10151d049  mov     [rbp+2830h+var_27D8], rax
0x10151d04d  mov     [rbp+2830h+var_27D0], 20Ah
0x10151d054  mov     rax, [rcx]
0x10151d057  mov     r9d, [rbp+2830h+var_2868]
0x10151d05b  mov     r8, r13
0x10151d05e  lea     rdx, [rbp+2830h+var_27F8]
0x10151d062  call    qword ptr [rax+8]
0x10151d065  test    al, al
0x10151d067  jz      loc_10151D1A2
0x10151d06d  mov     ecx, dword ptr [rbp+2830h+var_27F0]
0x10151d070  mov     eax, ecx
0x10151d072  and     eax, 0FFFFFFFEh
0x10151d075  cmp     eax, 100h
0x10151d07a  jbe     short loc_10151D0A7
0x10151d07c  xor     r13d, r13d
0x10151d07f  mov     [rsp+2930h+lpThreadAttributes], r13
0x10151d084  mov     r9d, 861h
0x10151d08a  lea     r8, aSecusrinstCpp; "secusrinst.cpp"
0x10151d091  lea     rdx, aAttrchildinstC; "(attrChildInst.cbInstName / sizeof(WCHA"...
0x10151d098  lea     ecx, [r13+1]
0x10151d09c  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10151d0a2  mov     ecx, dword ptr [rbp+2830h+var_27F0]
0x10151d0a5  jmp     short loc_10151D0AA
0x10151d0a7  xor     r13d, r13d
0x10151d0aa  mov     eax, ecx
0x10151d0ac  and     rax, 0FFFFFFFFFFFFFFFEh
0x10151d0b0  cmp     rax, 102h
0x10151d0b6  jnb     loc_10151F114
0x10151d0bc  mov     [rbp+rax+2830h+Buf1], r13w
0x10151d0c5  mov     eax, [rbp+2830h+var_27E0]
0x10151d0c8  cmp     eax, ebx
0x10151d0ca  jb      short loc_10151D0F5
0x10151d0cc  xor     ebx, ebx
0x10151d0ce  mov     [rsp+2930h+lpThreadAttributes], rbx
0x10151d0d3  mov     r9d, 863h
0x10151d0d9  lea     r8, aSecusrinstCpp; "secusrinst.cpp"
0x10151d0e0  lea     rdx, aAttrchildinstC_0; "(attrChildInst.cbInstPipeName) < (cbIns"...
0x10151d0e7  lea     ecx, [rbx+1]
0x10151d0ea  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10151d0f0  mov     eax, [rbp+2830h+var_27E0]
0x10151d0f3  jmp     short loc_10151D0F7
0x10151d0f5  xor     ebx, ebx
0x10151d0f7  shr     rax, 1
0x10151d0fa  mov     [rdi+rax*2], bx
0x10151d0fe  lea     rdx, [rbp+2830h+dwProcessId+4]; struct SQLDATE *
0x10151d102  mov     ecx, [rbp+2830h+dwProcessId]; dwProcessId
0x10151d105  call    ?FIsProcessAlive@CUserInstanceHelper@@SAHKAEAUSQLDATE@@@Z; CUserInstanceHelper::FIsProcessAlive(ulong,SQLDATE &)
0x10151d10a  test    eax, eax
0x10151d10c  jz      loc_10151D245
0x10151d112  xor     r12d, r12d
0x10151d115  test    r14d, r14d
0x10151d118  jz      short loc_10151D12D
0x10151d11a  mov     edx, 4
0x10151d11f  lea     rcx, [rbp+2830h+var_28B0]
0x10151d123  call    cs:__imp_?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x10151d129  mov     dword ptr [rbp+2830h+var_2888], r12d
0x10151d12d  mov     rax, [rbp+2830h+var_28A0]
0x10151d131  test    al, 40h
0x10151d133  jz      short loc_10151D15F
0x10151d135  mov     rbx, [rbp+2830h+var_28A8]
0x10151d139  lock xadd [rbx+18h], esi
0x10151d13e  cmp     esi, 1
0x10151d141  jnz     short loc_10151D15F
0x10151d143  cmp     qword ptr [rbx+8], 0
0x10151d148  jz      short loc_10151D156
0x10151d14a  mov     rdx, rbx
0x10151d14d  mov     rcx, [rbx+10h]
0x10151d151  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x10151d156  mov     rcx, rbx; this
0x10151d159  call    ?Destroy@SuperLatchInfo@@AEAAXXZ; SuperLatchInfo::Destroy(void)
0x10151d15e  nop
0x10151d15f  cmp     [rbp+2830h+var_2860], 0
0x10151d163  jz      short loc_10151D17D
0x10151d165  mov     rcx, [rbp+2830h+hObject]; hObject
0x10151d169  lea     rax, [rcx-1]
0x10151d16d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x10151d171  ja      short loc_10151D17D
0x10151d173  call    cs:__imp_CloseHandle
0x10151d179  mov     [rbp+2830h+var_2860], r12d
0x10151d17d  cmp     [rbp+2830h+var_2850], 0
0x10151d181  jz      short loc_10151D19B
0x10151d183  mov     rcx, [rbp+2830h+var_2848]; hObject
0x10151d187  lea     rax, [rcx-1]
0x10151d18b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x10151d18f  ja      short loc_10151D19B
0x10151d191  call    cs:__imp_CloseHandle
0x10151d197  mov     [rbp+2830h+var_2850], r12d
0x10151d19b  xor     eax, eax
0x10151d19d  jmp     loc_10151F0EA
0x10151d1a2  mov     r9d, ebx; unsigned int
0x10151d1a5  mov     r8, rdi; wchar_t *
0x10151d1a8  mov     edx, 102h; unsigned int
0x10151d1ad  lea     rcx, [rbp+2830h+Buf1]; Buf1
0x10151d1b4  call    ?GenerateChildInstanceName@@YAJPEA_WK0K@Z; GenerateChildInstanceName(wchar_t *,ulong,wchar_t *,ulong)
0x10151d1b9  mov     r15d, eax
0x10151d1bc  test    eax, eax
0x10151d1be  jz      short loc_10151D215
0x10151d1c0  test    r14d, r14d
0x10151d1c3  jz      short loc_10151D1DB
0x10151d1c5  mov     edx, 4
0x10151d1ca  lea     rcx, [rbp+2830h+var_28B0]
0x10151d1ce  call    cs:__imp_?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x10151d1d4  xor     r13d, r13d
0x10151d1d7  mov     dword ptr [rbp+2830h+var_2888], r13d
0x10151d1db  mov     rax, [rbp+2830h+var_28A0]
0x10151d1df  test    al, 40h
0x10151d1e1  jz      short loc_10151D20D
0x10151d1e3  mov     rbx, [rbp+2830h+var_28A8]
0x10151d1e7  lock xadd [rbx+18h], esi
0x10151d1ec  cmp     esi, 1
0x10151d1ef  jnz     short loc_10151D20D
0x10151d1f1  cmp     qword ptr [rbx+8], 0
0x10151d1f6  jz      short loc_10151D204
0x10151d1f8  mov     rdx, rbx
0x10151d1fb  mov     rcx, [rbx+10h]
0x10151d1ff  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x10151d204  mov     rcx, rbx; this
0x10151d207  call    ?Destroy@SuperLatchInfo@@AEAAXXZ; SuperLatchInfo::Destroy(void)
0x10151d20c  nop
0x10151d20d  mov     eax, r15d
0x10151d210  jmp     loc_10151F0EA
0x10151d215  lea     rcx, [rbp+2830h+Buf1]
0x10151d21c  mov     rax, rsi
0x10151d21f  nop
0x10151d220  inc     rax
0x10151d223  cmp     word ptr [rcx+rax*2], 0
0x10151d228  jnz     short loc_10151D220
0x10151d22a  add     rax, rax
0x10151d22d  mov     dword ptr [rbp+2830h+var_27F0], eax
0x10151d230  mov     rax, rsi
0x10151d233  inc     rax
0x10151d236  cmp     word ptr [rdi+rax*2], 0
0x10151d23b  jnz     short loc_10151D233
0x10151d23d  add     rax, rax
0x10151d240  mov     [rbp+2830h+var_27E0], eax
0x10151d243  xor     ebx, ebx
0x10151d245  mov     [rsp+2930h+var_28C0], rbx
0x10151d24a  mov     [rbp+2830h+var_2834], 20Ah
0x10151d251  mov     [rbp+2830h+var_2808], 20Ah
0x10151d258  mov     edx, 1; int
0x10151d25d  lea     rcx, aShell32Dll_1; "SHELL32.DLL"
0x10151d264  call    ?DBLoadLibraryA@@YAPEAUHINSTANCE__@@PEBDH@Z; DBLoadLibraryA(char const *,int)
0x10151d269  mov     r15, rax
0x10151d26c  test    rax, rax
0x10151d26f  jnz     short loc_10151D293
0x10151d271  mov     [rsp+2930h+lpThreadAttributes], rbx
0x10151d276  mov     r9d, 8A8h
0x10151d27c  lea     r8, aSecusrinstCpp; "secusrinst.cpp"
0x10151d283  lea     rdx, aHidll; "hiDll"
0x10151d28a  lea     ecx, [rax+1]
0x10151d28d  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10151d293  mov     rdx, cs:qword_102ECFB00
0x10151d29a  add     rdx, 0AF16h; int
0x10151d2a1  lea     rax, [rsp+2930h+var_28C0]
0x10151d2a6  mov     [rsp+2930h+lpThreadAttributes], rax; PHKEY
0x10151d2ab  mov     r9d, 1; int
0x10151d2b1  xor     r8d, r8d; int
0x10151d2b4  mov     rcx, 0FFFFFFFF80000002h; int
0x10151d2bb  call    IniRegOpenKeyExW
0x10151d2c0  test    eax, eax
0x10151d2c2  jz      short loc_10151D316
0x10151d2c4  lea     rcx, ?wszRegOpenKeyEx@CSECErrorAPI@@2QB_WB; "RegOpenKeyEx"
0x10151d2cb  mov     dword ptr [rsp+2930h+lpThreadAttributes], ebx; int
0x10151d2cf  mov     r9, cs:?sm_CSECCryptoErrorToWideNames@CSECErrorRingBufferManager@@2PAPEA_WA; wchar_t *
0x10151d2d6  mov     r8d, eax; unsigned int
0x10151d2d9  lea     rdx, ?wszStartChildInstanceAndAttachDb@CSECErrorAPI@@2QB_WB; "StartChildInstanceAndAttachDb"
0x10151d2e0  call    ?StoreRecord@CSECErrorRingBufferManager@@SAXPEB_W0KPEA_WH@Z; CSECErrorRingBufferManager::StoreRecord(wchar_t const *,wchar_t const *,ulong,wchar_t *,int)
0x10151d2e5  nop
0x10151d2e6  mov     rcx, [rsp+2930h+var_28C0]
0x10151d2eb  test    rcx, rcx
0x10151d2ee  jz      short loc_10151D2F6
0x10151d2f0  call    IniRegCloseKey
0x10151d2f5  nop
0x10151d2f6  test    r14d, r14d
0x10151d2f9  jz      loc_10151DDC4
0x10151d2ff  mov     edx, 4
0x10151d304  lea     rcx, [rbp+2830h+var_28B0]
0x10151d308  call    cs:__imp_?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x10151d30e  mov     dword ptr [rbp+2830h+var_2888], ebx
0x10151d311  jmp     loc_10151DDC4
0x10151d316  lea     rax, [rbp+2830h+var_2808]
  ... truncated ...
```
