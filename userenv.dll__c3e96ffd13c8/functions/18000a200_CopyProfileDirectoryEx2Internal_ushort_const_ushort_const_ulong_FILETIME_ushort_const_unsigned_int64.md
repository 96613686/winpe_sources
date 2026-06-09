# CopyProfileDirectoryEx2Internal(ushort const *,ushort const *,ulong,_FILETIME *,ushort const *,unsigned __int64)

- ea: `0x18000a200`
- end: `0x18000b233`
- name: `?CopyProfileDirectoryEx2Internal@@YAHPEBG0KPEAU_FILETIME@@0_K@Z`
- size: `4147`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct _FILETIME *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800144a0`

## callees

- `0x1800061d4`
- `0x180006904`
- `0x180006e50`
- `0x180006e90`
- `0x1800072a0`
- `0x18000804c`
- `0x1800080b4`
- `0x1800080ec`
- `0x1800085b0`
- `0x180008acc`
- `0x180009510`
- `0x1800098c4`
- `0x18000a200`
- `0x18000b23c`
- `0x18000b2d0`
- `0x18000bdd8`
- `0x18000c18c`
- `0x18000cdf0`
- `0x18000d178`
- `0x18000d9b0`
- `0x18000e330`
- `0x180017a94`
- `0x180019748`
- `0x1800198ac`
- `0x18001992c`
- `0x180019b78`
- `0x180019c00`
- `0x180019c58`
- `0x180019cb0`
- `0x180019e5c`
- `0x180019f0c`
- `0x18001a144`
- `0x18001a200`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a403`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a3e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a3e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a42d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a42d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a41a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a41a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b1f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b208`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b1f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a40d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a79c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a85e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a95a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ace8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a40d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a79c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a85e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a95a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ace8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b07f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b10c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b07f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b10c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a653`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a669`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a653`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a669`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b122`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b130`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b146`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b15c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b16f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b185`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b122`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b130`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b146`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b15c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b16f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b185`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000aca6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ad69`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000aca6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ad69`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000aadb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000aadb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b045`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b045`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000b060`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000b060`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000ae29`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000ae29`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18000a950`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18000a950`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000ade4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000ade4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000adb6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000b016`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000b0a0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000adb6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000b016`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000b0a0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000ad97`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000ad97`

## string_xrefs

- `0x18000a37c`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000a501`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000a5a0`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000a602`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000a7dc`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000a968`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000acf6`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000ae08`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000ae6b`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000af7f`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000b0e2`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall CopyProfileDirectoryEx2Internal(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _FILETIME *a4,
        unsigned __int16 *a5,
        unsigned __int64 a6)
{
  const char *LastError; // rdi
  int v10; // ebx
  unsigned __int64 v11; // r10
  __int64 v12; // rdx
  DWORD v13; // ecx
  int v14; // ecx
  HANDLE CurrentThread; // rax
  struct _SECURITY_ATTRIBUTES *v16; // rdx
  unsigned int v17; // r8d
  const char *v18; // r9
  HANDLE CurrentProcess; // rax
  int v20; // r13d
  int v21; // eax
  unsigned int v22; // ebx
  __int64 v23; // rcx
  __int64 *v24; // rdx
  unsigned __int16 *v25; // rbx
  unsigned int v26; // esi
  int v27; // eax
  int NestedDirectory; // eax
  WCHAR *v29; // r14
  WCHAR *v30; // rax
  unsigned __int16 *v31; // r13
  unsigned int v32; // ebx
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdx
  const char *v37; // r9
  __int64 v38; // rcx
  struct _FILETIME v39; // r14
  _ULARGE_INTEGER v40; // r13
  bool v41; // zf
  int v42; // edx
  __int64 v43; // rcx
  char v44; // al
  __int64 *v45; // rdx
  struct _FILETIME *v46; // rbx
  unsigned int v47; // r14d
  const unsigned __int16 *v48; // r8
  unsigned __int16 *v49; // rbx
  unsigned __int16 *v50; // r13
  HANDLE FirstFileW; // r15
  __int64 v52; // rcx
  __int64 v53; // r8
  WCHAR *cFileName; // r8
  __int64 StringLengthHr; // rax
  unsigned int v56; // ebx
  __int64 v57; // rdi
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rcx
  const char *v61; // rbx
  __int64 v62; // rcx
  DWORD FileAttributesW; // eax
  unsigned int v64; // r8d
  const char *v65; // r9
  __int64 v66; // rdx
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // r8
  struct _FILEINFO *i; // rbx
  int v72; // eax
  __int64 v73; // rcx
  __int64 v74; // r8
  unsigned int v75; // eax
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // r8
  struct _FILEINFO *j; // rbx
  HANDLE FileW; // rax
  unsigned int v81; // r8d
  const char *v82; // r9
  void *v83; // rsi
  unsigned int v84; // r8d
  const char *v85; // r9
  __int64 v86; // rdx
  __int64 v87; // rcx
  void *dwCreationDisposition; // [rsp+20h] [rbp-3C8h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-3C8h]
  WCHAR *lpDirectoryName; // [rsp+68h] [rbp-380h]
  int v92; // [rsp+70h] [rbp-378h] BYREF
  int v93; // [rsp+74h] [rbp-374h] BYREF
  unsigned int v94; // [rsp+78h] [rbp-370h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-368h] BYREF
  unsigned int v96[2]; // [rsp+88h] [rbp-360h] BYREF
  struct _FILEINFO *v97; // [rsp+90h] [rbp-358h] BYREF
  unsigned __int16 *v98; // [rsp+98h] [rbp-350h] BYREF
  unsigned int v99[2]; // [rsp+A0h] [rbp-348h] BYREF
  struct _FILEINFO *v100; // [rsp+A8h] [rbp-340h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-338h] BYREF
  struct _FILETIME v102; // [rsp+B8h] [rbp-330h] BYREF
  unsigned __int64 v103; // [rsp+C0h] [rbp-328h] BYREF
  struct _FILEINFO *v104; // [rsp+C8h] [rbp-320h] BYREF
  unsigned __int64 v105; // [rsp+D0h] [rbp-318h] BYREF
  _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+D8h] [rbp-310h] BYREF
  LPCWSTR lpFileName; // [rsp+E0h] [rbp-308h]
  HLOCAL hMem; // [rsp+E8h] [rbp-300h] BYREF
  HLOCAL v109; // [rsp+F0h] [rbp-2F8h] BYREF
  HLOCAL v110; // [rsp+F8h] [rbp-2F0h] BYREF
  HLOCAL v111; // [rsp+100h] [rbp-2E8h] BYREF
  struct _FILEINFO *v112; // [rsp+108h] [rbp-2E0h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+110h] [rbp-2D8h] BYREF
  unsigned __int64 v114; // [rsp+118h] [rbp-2D0h]
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+120h] [rbp-2C8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+130h] [rbp-2B8h] BYREF
  unsigned __int64 v117[2]; // [rsp+380h] [rbp-68h] BYREF
  unsigned __int16 *v118[2]; // [rsp+390h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+0h]

  v114 = (unsigned __int64)a4;
  hMem = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v97 = 0;
  v104 = 0;
  v100 = 0;
  v112 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v102 = 0;
  v117[0] = 0;
  v105 = 0;
  FreeBytesAvailableToCaller.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  TokenHandle = 0;
  v103 = 0;
  SystemTimeAsFileTime = 0;
  v96[0] = 0;
  v99[0] = 0;
  v93 = 0;
  LODWORD(LastError) = GetLastError();
  if ( !a1 || !a2 )
  {
    v13 = 87;
    goto LABEL_180;
  }
  v10 = StringCchLengthW(a1, 0x104u, &v103);
  if ( v10 < 0 )
  {
    v12 = 627;
LABEL_5:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)(unsigned int)v10,
      (int)dwCreationDisposition);
    v13 = (unsigned __int16)v10;
LABEL_180:
    SetLastError(v13);
    return 0;
  }
  v92 = StringCchLengthW(a2, v11, (unsigned __int64 *)&SystemTimeAsFileTime);
  v10 = v92;
  if ( v92 < 0 )
  {
    v12 = 635;
    goto LABEL_5;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
  {
    McTemplateU0zzd_EventWriteTransfer(
      v14,
      (unsigned int)EVENT_COPY_PROFILE_DIRECTORY_START,
      (_DWORD)a1,
      (_DWORD)a2,
      a3);
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008
      || (CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle)) )
    {
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x292, v17, v18);
      return 0;
    }
  }
  lpFileName = 0;
  if ( (a3 & 0x800) == 0 || !a5 )
    goto LABEL_30;
  v98 = 0;
  v10 = StringCchLengthW(a5, 0x7FFFFFFFu, (unsigned __int64 *)&v98);
  if ( v10 < 0 )
  {
    v12 = 674;
    goto LABEL_5;
  }
  v20 = (int)v98;
  v94 = 0;
  v21 = AllocateAndExpandExclusionList(a1, (int)v103 + 1, a5, (int)v98 + 1, (unsigned __int16 **)&v110, &v94);
  v92 = v21;
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( (a3 & 0x2000) == 0 )
    {
      v94 = 0;
      v27 = AllocateAndExpandExclusionList(
              a2,
              SystemTimeAsFileTime.dwLowDateTime + 1,
              a5,
              v20 + 1,
              (unsigned __int16 **)&v111,
              &v94);
      v92 = v27;
      v22 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2D1,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
          (const char *)(unsigned int)v27,
          (int)dwCreationDisposition);
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
          || (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) == 0 )
        {
          goto LABEL_24;
        }
        v24 = EVENT_COPY_PROFILE_DIRECTORY_EXCLUSION_DEST_FAILED;
        goto LABEL_23;
      }
    }
LABEL_30:
    if ( (a3 & 0x200000) == 0 )
    {
      NestedDirectory = CreateNestedDirectory(a2, v16);
      v92 = NestedDirectory;
      v22 = NestedDirectory;
      if ( NestedDirectory < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2ED,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
          (const char *)(unsigned int)NestedDirectory,
          (int)dwCreationDisposition);
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
          || (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) == 0 )
        {
          goto LABEL_24;
        }
        v24 = EVENT_COPY_PROFILE_DIRECTORY_CREATEDIR_FAILED;
        goto LABEL_23;
      }
    }
    v29 = (WCHAR *)LocalAlloc(0x40u, 0x410u);
    lpFileName = v29;
    v30 = (WCHAR *)LocalAlloc(0x40u, 0x410u);
    lpDirectoryName = v30;
    v31 = v30;
    if ( !v29 || !v30 )
    {
      LastError = (const char *)GetLastError();
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x304,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        LastError,
        (unsigned int)dwCreationDisposition);
      v25 = v31;
      goto LABEL_152;
    }
    v32 = 520;
    v94 = a3 & 0x20;
    StringCchCopyW(v29, 0x208u, a1);
    StringCchCopyW(v31, 0x208u, a2);
    v98 = CheckSlash(v29, 0x208u, v96);
    v118[0] = CheckSlash(v31, 0x208u, v99);
    LODWORD(v103) = a3 & 0x200;
    if ( (a3 & 0x200) == 0 )
    {
      if ( (int)_CreateLongPathBuffer(v29, v33, (unsigned __int16 **)&hMem) >= 0
        && (int)_CreateLongPathBuffer(v31, v34, (unsigned __int16 **)&v109) >= 0 )
      {
        v29 = (WCHAR *)hMem;
        v32 = 0x8000;
        v31 = (unsigned __int16 *)v109;
      }
      if ( !(unsigned int)RecurseDirectory(
                            TokenHandle,
                            v29,
                            v32,
                            v31,
                            v32,
                            a3,
                            &v100,
                            &v97,
                            1,
                            (unsigned __int16 *)v110,
                            0,
                            (struct CCopyError *)&v93) )
      {
        LODWORD(LastError) = GetLastError();
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
          && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
        {
          McTemplateU0d_EventWriteTransfer(
            v35,
            EVENT_COPY_PROFILE_DIRECTORY_RECURSE_SOURCE_FAILED,
            (unsigned int)LastError);
        }
        v36 = 860;
LABEL_46:
        v37 = (const char *)(unsigned int)LastError;
LABEL_47:
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)v36,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
          v37,
          (unsigned int)dwCreationDisposition);
LABEL_48:
        v25 = lpDirectoryName;
LABEL_152:
        v26 = 0;
        goto LABEL_153;
      }
      if ( v94
        && !(unsigned int)RecurseDirectory(
                            TokenHandle,
                            v31,
                            v32,
                            v29,
                            v32,
                            a3,
                            &v112,
                            &v104,
                            1,
                            (unsigned __int16 *)v111,
                            1,
                            (struct CCopyError *)&v93) )
      {
        LODWORD(LastError) = GetLastError();
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
          && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
        {
          McTemplateU0d_EventWriteTransfer(
            v38,
            EVENT_COPY_PROFILE_DIRECTORY_RECURSE_DEST_FAILED,
            (unsigned int)LastError);
        }
        v36 = 889;
        goto LABEL_46;
      }
    }
    if ( FindDirectorySize(v97, a3, &v105, (unsigned __int64 *)&v102) )
    {
      LastError = (const char *)GetLastError();
      v37 = LastError;
      v36 = 903;
      goto LABEL_47;
    }
    if ( FindDirectorySize(v104, a3, 0, v117) )
    {
      LastError = (const char *)GetLastError();
      v37 = LastError;
      v36 = 910;
      goto LABEL_47;
    }
    v39 = v102;
    v25 = lpDirectoryName;
    v40.QuadPart = FindTotalDiskSpaceNeeded(*(_QWORD *)&v102, v117[0], v105, v97);
    if ( !GetDiskFreeSpaceExW(
            lpDirectoryName,
            &FreeBytesAvailableToCaller,
            &TotalNumberOfBytes,
            &TotalNumberOfFreeBytes) )
    {
      LastError = (const char *)GetLastError();
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x3A7,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        LastError,
        (unsigned int)dwCreationDisposition);
      goto LABEL_152;
    }
    v41 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl) == 0;
    v44 = Microsoft_Windows_User_Profiles_GeneralEnableBits;
    if ( !v41 && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
    {
      McTemplateU0xxxxxxx_EventWriteTransfer(
        v43,
        v42,
        FreeBytesAvailableToCaller.LowPart,
        v40.LowPart,
        v39.dwLowDateTime,
        v117[0],
        v105,
        a6,
        TotalNumberOfFreeBytes.LowPart);
      v44 = Microsoft_Windows_User_Profiles_GeneralEnableBits;
    }
    if ( a6 && *(_QWORD *)&v39 > a6 )
    {
      LODWORD(LastError) = 1295;
      if ( (v44 & 1) == 0 )
        goto LABEL_48;
      v45 = EVENT_EXCEED_QUOTA;
LABEL_68:
      McTemplateU0zz_EventWriteTransfer(v43, v45, a1, a2);
      goto LABEL_48;
    }
    if ( v40.QuadPart > FreeBytesAvailableToCaller.QuadPart )
    {
      LODWORD(LastError) = 112;
      if ( (v44 & 1) == 0 )
        goto LABEL_48;
      v45 = EVENT_DISK_FULL;
      goto LABEL_68;
    }
    if ( v94 )
    {
      v46 = (struct _FILETIME *)(v114 & -(__int64)((a3 & 0x400) != 0));
      SyncItems(v97, v104, 1, v46);
      SyncItems(v100, v112, 0, v46);
    }
    if ( (a3 & 4) == 0 )
    {
      v47 = v96[0];
      v48 = L"user.*";
      v49 = v98;
      if ( (a3 & 8) == 0 )
        v48 = L"ntuser.*";
      StringCchCopyW(v98, v96[0], v48);
      v50 = (unsigned __int16 *)lpFileName;
      FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        while ( 1 )
        {
          if ( !(unsigned int)_IsRegistryTransactionFile(FindFileData.cFileName) )
          {
            if ( (a3 & 0x100000) != 0
              && (StringIsEqual(FindFileData.cFileName, L"ntuser.man")
               || StringIsEqual(FindFileData.cFileName, L"ntuser.dat")) )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
                && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x10) != 0 )
              {
                dwCreationDisposition = v117;
                McGenEventWrite_EventWriteTransfer(v52, EVENT_COPY_PROFILE_DIRECTORY_TEMP_HIVE, v53, 1);
              }
              cFileName = (WCHAR *)L"ntuser.tmp";
            }
            else
            {
              cFileName = FindFileData.cFileName;
            }
            StringCchCopyW(v49, v47, cFileName);
            StringCchCopyW(v118[0], v99[0], FindFileData.cFileName);
            StringLengthHr = anonymous_namespace_::_GetStringLengthHr(&v92, FindFileData.cFileName);
            v56 = v92;
            v57 = StringLengthHr;
            if ( v92 < 0 )
            {
              v67 = 1052;
              goto LABEL_112;
            }
            v58 = anonymous_namespace_::_GetStringLengthHr(&v92, L".log");
            v56 = v92;
            if ( v92 < 0 )
            {
              v67 = 1059;
LABEL_112:
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)v67,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                (const char *)v56,
                (int)dwCreationDisposition);
              LODWORD(LastError) = (unsigned __int16)v56;
              goto LABEL_48;
            }
            if ( (a3 & 0x100000) == 0 || !StringIsEqual(&FindFileData.cFileName[v57 - v58], L".log") )
            {
              if ( StringIsEqual(FindFileData.cFileName, L"ntuser.tmp") )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
                  && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
                {
                  McTemplateU0z_EventWriteTransfer(
                    v59,
                    EVENT_COPY_PROFILE_DIRECTORY_TEMP_HIVE_SKIPPED,
                    FindFileData.cFileName);
                }
              }
              else
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
                  && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
                {
                  McTemplateU0z_EventWriteTransfer(v60, EVENT_COPY_PROFILE_DIRECTORY_HIVE_FOUND, FindFileData.cFileName);
                }
                SystemTimeAsFileTime = 0;
                GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                if ( (unsigned int)ReconcileFile(
                                     v50,
                                     lpDirectoryName,
                                     a3,
                                     0,
                                     (struct _FILETIME *)(v114 & -(__int64)((a3 & 0x800000) != 0)),
                                     1) )
                {
                  v102 = 0;
                  GetSystemTimeAsFileTime(&v102);
                  _WriteCopyEvent(&SystemTimeAsFileTime, &v102, &FindFileData, v50, lpDirectoryName);
                  FileAttributesW = GetFileAttributesW(lpDirectoryName);
                  if ( FileAttributesW == -1 )
                  {
                    v66 = 1140;
                    goto LABEL_108;
                  }
                  if ( (FileAttributesW & 0x2002) != 0x2002
                    && !SetFileAttributesW(lpDirectoryName, FileAttributesW | 0x2002) )
                  {
                    v66 = 1134;
LABEL_108:
                    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)v66, v64, v65);
                  }
                }
                else
                {
                  v61 = (const char *)GetLastError();
                  wil::details::in1diag3::Log_Win32(
                    retaddr,
                    (void *)0x450,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                    v61,
                    dwCreationDispositiona);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
                    && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
                  {
                    McTemplateU0d_EventWriteTransfer(
                      v62,
                      EVENT_COPY_PROFILE_DIRECTORY_RECONCILE_FAILED,
                      (unsigned int)v61);
                  }
                  CCopyError::Report((CCopyError *)&v93, TokenHandle, v50, lpDirectoryName, (DWORD)v61);
                }
              }
            }
          }
          if ( !FindNextFileW(FirstFileW, &FindFileData) )
          {
            FindClose(FirstFileW);
            LODWORD(LastError) = 0;
            goto LABEL_119;
          }
          v49 = v98;
        }
      }
      LODWORD(LastError) = GetLastError();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
      {
        McTemplateU0d_EventWriteTransfer(v68, EVENT_COPY_PROFILE_DIRECTORY_FIND_FIRST_FAILED, (unsigned int)LastError);
      }
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x489,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)(unsigned int)LastError,
        (unsigned int)dwCreationDisposition);
    }
LABEL_119:
    if ( (_DWORD)v103 )
      goto LABEL_136;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
    {
      dwCreationDisposition = v118;
      McGenEventWrite_EventWriteTransfer(v69, EVENT_COPY_PROFILE_DIRECTORY_COPYRUPDIR_START, v70, 1);
    }
    for ( i = v100; i; i = (struct _FILEINFO *)*((_QWORD *)i + 6) )
    {
      v72 = CopyRupDirectory(*(const unsigned __int16 **)i, *((const unsigned __int16 **)i + 1), a3 & 0x8000);
      if ( v72 < 0 )
        CCopyError::Report(
          (CCopyError *)&v93,
          TokenHandle,
          *(const unsigned __int16 **)i,
          *((const unsigned __int16 **)i + 1),
          (unsigned __int16)v72);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
    {
      dwCreationDisposition = v118;
      McGenEventWrite_EventWriteTransfer(v73, EVENT_COPY_PROFILE_DIRECTORY_COPYRUPDIR_END, v74, 1);
    }
    if ( !v97
      || (v75 = _MultiThreadedCopy(v97, a3, TokenHandle, (struct CCopyError *)&v93), (LODWORD(LastError) = v75) == 0) )
    {
LABEL_136:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
      {
        McGenEventWrite_EventWriteTransfer(v77, EVENT_COPY_PROFILE_DIRECTORY_RESTORE_DIR_TIMESTAMP, v78, 1);
      }
      for ( j = v100; j; j = (struct _FILEINFO *)*((_QWORD *)j + 6) )
      {
        SetFileAttributesW(*((LPCWSTR *)j + 1), 0x80u);
        FileW = CreateFileW(*((LPCWSTR *)j + 1), 0x40000000u, 6u, 0, 3u, 0x2000080u, 0);
        v83 = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x4E1, v81, v82);
        }
        else
        {
          if ( !SetFileTime(FileW, 0, 0, (const FILETIME *)j + 2) )
            wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x4DA, v84, v85);
          CloseHandle(v83);
        }
        SetFileAttributesW(*((LPCWSTR *)j + 1), *((_DWORD *)j + 10));
      }
      if ( (a3 & 2) != 0 || !v93 )
      {
        v26 = 1;
      }
      else
      {
        LODWORD(LastError) = 299;
        v26 = 0;
      }
      v25 = lpDirectoryName;
      goto LABEL_153;
    }
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x4B3,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)v75,
      (unsigned int)dwCreationDisposition);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
    {
      McTemplateU0d_EventWriteTransfer(v76, EVENT_COPY_PROFILE_DIRECTORY_COPY_FILES_FAILED, (unsigned int)LastError);
    }
    goto LABEL_48;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x2B7,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    (const char *)(unsigned int)v21,
    (int)dwCreationDisposition);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    || (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) == 0 )
  {
    goto LABEL_24;
  }
  v24 = EVENT_COPY_PROFILE_DIRECTORY_EXCLUSION_SOURCE_FAILED;
LABEL_23:
  McTemplateU0d_EventWriteTransfer(v23, v24, v22);
LABEL_24:
  LODWORD(LastError) = (unsigned __int16)v22;
  v25 = 0;
  v26 = 0;
LABEL_153:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( lpFileName )
    LocalFree((HLOCAL)lpFileName);
  if ( v25 )
    LocalFree(v25);
  if ( hMem )
    LocalFree(hMem);
  if ( v109 )
    LocalFree(v109);
  if ( v110 )
    LocalFree(v110);
  if ( v111 )
    LocalFree(v111);
  if ( v97 )
    FreeFileInfoList(v97);
  if ( v104 )
    FreeFileInfoList(v104);
  if ( v100 )
    FreeFileInfoList(v100);
  if ( v112 )
    FreeFileInfoList(v112);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl) )
  {
    if ( (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
      McTemplateU0dt_EventWriteTransfer(v87, v86, (unsigned int)LastError, v26);
  }
  SetLastError((DWORD)LastError);
  return v26;
}

```

## disassembly

```asm
0x18000a200  mov     r11, rsp
0x18000a203  push    rbx
0x18000a204  push    rsi
0x18000a205  push    rdi
0x18000a206  push    r12
0x18000a208  push    r13
0x18000a20a  push    r14
0x18000a20c  push    r15
0x18000a20e  sub     rsp, 3B0h
0x18000a215  mov     rax, cs:__security_cookie
0x18000a21c  xor     rax, rsp
0x18000a21f  mov     [rsp+3E8h+var_48], rax
0x18000a227  mov     r14, [rsp+3E8h+arg_20]
0x18000a22f  mov     r12d, r8d
0x18000a232  mov     rsi, rdx
0x18000a235  mov     [rsp+3E8h+var_2D0], r9
0x18000a23d  mov     r15, rcx
0x18000a240  mov     qword ptr [r11-300h], 0
0x18000a24b  xor     edx, edx; Val
0x18000a24d  mov     qword ptr [r11-2F8h], 0
0x18000a258  mov     r8d, 250h; Size
0x18000a25e  mov     qword ptr [r11-2F0h], 0
0x18000a269  lea     rcx, [r11-2B8h]; void *
0x18000a270  mov     qword ptr [r11-2E8h], 0
0x18000a27b  mov     qword ptr [r11-358h], 0
0x18000a286  mov     qword ptr [r11-320h], 0
0x18000a291  mov     qword ptr [r11-340h], 0
0x18000a29c  mov     qword ptr [r11-2E0h], 0
0x18000a2a7  call    memset_0
0x18000a2ac  mov     qword ptr [rsp+3E8h+var_330.dwLowDateTime], 0
0x18000a2b8  mov     [rsp+3E8h+var_68], 0
0x18000a2c4  mov     [rsp+3E8h+var_318], 0
0x18000a2d0  mov     qword ptr [rsp+3E8h+FreeBytesAvailableToCaller], 0
0x18000a2dc  mov     qword ptr [rsp+3E8h+TotalNumberOfBytes], 0
0x18000a2e8  mov     qword ptr [rsp+3E8h+TotalNumberOfFreeBytes], 0
0x18000a2f4  mov     [rsp+3E8h+TokenHandle], 0
0x18000a300  mov     [rsp+3E8h+var_328], 0
0x18000a30c  mov     qword ptr [rsp+3E8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000a318  mov     [rsp+3E8h+var_360], 0
0x18000a323  mov     [rsp+3E8h+var_348], 0
0x18000a32e  mov     dword ptr [rsp+3E8h+var_378+4], 0
0x18000a336  call    cs:__imp_GetLastError
0x18000a33c  mov     edi, eax
0x18000a33e  test    r15, r15
0x18000a341  jz      loc_18000B203
0x18000a347  test    rsi, rsi
0x18000a34a  jz      loc_18000B203
0x18000a350  mov     r10d, 104h
0x18000a356  lea     r8, [rsp+3E8h+var_328]; unsigned __int64 *
0x18000a35e  mov     edx, r10d; unsigned __int64
0x18000a361  mov     rcx, r15; unsigned __int16 *
0x18000a364  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000a369  mov     ebx, eax
0x18000a36b  test    eax, eax
0x18000a36d  jns     short loc_18000A393
0x18000a36f  mov     edx, 273h; void *
0x18000a374  mov     rcx, [rsp+3E8h]; this
0x18000a37c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a383  mov     r9d, ebx; char *
0x18000a386  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a38b  movzx   ecx, bx
0x18000a38e  jmp     loc_18000B208
0x18000a393  lea     r8, [rsp+3E8h+SystemTimeAsFileTime]; unsigned __int64 *
0x18000a39b  mov     rdx, r10; unsigned __int64
0x18000a39e  mov     rcx, rsi; unsigned __int16 *
0x18000a3a1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000a3a6  mov     dword ptr [rsp+3E8h+var_378], eax
0x18000a3aa  mov     ebx, eax
0x18000a3ac  test    eax, eax
0x18000a3ae  jns     short loc_18000A3B7
0x18000a3b0  mov     edx, 27Bh
0x18000a3b5  jmp     short loc_18000A374
0x18000a3b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000a3be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000a3c3  test    al, al
0x18000a3c5  jz      short loc_18000A3E7
0x18000a3c7  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000a3ce  jz      short loc_18000A3E7
0x18000a3d0  mov     r9, rsi
0x18000a3d3  mov     [rsp+3E8h+dwCreationDisposition], r12d; unsigned int
0x18000a3d8  mov     r8, r15
0x18000a3db  lea     rdx, EVENT_COPY_PROFILE_DIRECTORY_START
0x18000a3e2  call    McTemplateU0zzd_EventWriteTransfer
0x18000a3e7  call    cs:__imp_GetCurrentThread
0x18000a3ed  mov     ebx, 0Eh
0x18000a3f2  lea     r9, [rsp+3E8h+TokenHandle]; TokenHandle
0x18000a3fa  mov     rcx, rax; ThreadHandle
0x18000a3fd  mov     edx, ebx; DesiredAccess
0x18000a3ff  lea     r8d, [rbx-0Dh]; OpenAsSelf
0x18000a403  call    cs:__imp_OpenThreadToken
0x18000a409  test    eax, eax
0x18000a40b  jnz     short loc_18000A44E
0x18000a40d  call    cs:__imp_GetLastError
0x18000a413  cmp     eax, 3F0h
0x18000a418  jnz     short loc_18000A437
0x18000a41a  call    cs:__imp_GetCurrentProcess
0x18000a420  lea     r8, [rsp+3E8h+TokenHandle]; TokenHandle
0x18000a428  mov     edx, ebx; DesiredAccess
0x18000a42a  mov     rcx, rax; ProcessHandle
0x18000a42d  call    cs:__imp_OpenProcessToken
0x18000a433  test    eax, eax
0x18000a435  jnz     short loc_18000A44E
0x18000a437  mov     rcx, [rsp+3E8h]; this
0x18000a43f  mov     edx, 292h; void *
0x18000a444  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18000a449  jmp     loc_18000B20E
0x18000a44e  mov     [rsp+3E8h+lpFileName], 0
0x18000a45a  mov     [rsp+3E8h+lpDirectoryName], 0
0x18000a463  mov     [rsp+3E8h+var_388], 0
0x18000a46b  bt      r12d, 0Bh
0x18000a470  jnb     loc_18000A5E1
0x18000a476  test    r14, r14
0x18000a479  jz      loc_18000A5E1
0x18000a47f  lea     r8, [rsp+3E8h+var_350]; unsigned __int64 *
0x18000a487  mov     [rsp+3E8h+var_350], 0
0x18000a493  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000a498  mov     rcx, r14; unsigned __int16 *
0x18000a49b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000a4a0  mov     ebx, eax
0x18000a4a2  test    eax, eax
0x18000a4a4  jns     short loc_18000A4B0
0x18000a4a6  mov     edx, 2A2h
0x18000a4ab  jmp     loc_18000A374
0x18000a4b0  mov     edx, dword ptr [rsp+3E8h+var_328]
0x18000a4b7  lea     rax, [rsp+3E8h+var_370]
0x18000a4bc  mov     r13d, dword ptr [rsp+3E8h+var_350]
0x18000a4c4  inc     edx; unsigned int
0x18000a4c6  mov     qword ptr [rsp+3E8h+dwFlagsAndAttributes], rax; unsigned int *
0x18000a4cb  mov     r8, r14; unsigned __int16 *
0x18000a4ce  lea     rax, [rsp+3E8h+var_2F0]
0x18000a4d6  mov     [rsp+3E8h+var_370], 0
0x18000a4de  mov     rcx, r15; unsigned __int16 *
0x18000a4e1  mov     qword ptr [rsp+3E8h+dwCreationDisposition], rax; int
0x18000a4e6  lea     r9d, [r13+1]; unsigned int
0x18000a4ea  call    ?AllocateAndExpandExclusionList@@YAJPEBGK0KPEAPEAGAEAK@Z; AllocateAndExpandExclusionList(ushort const *,ulong,ushort const *,ulong,ushort * *,ulong &)
0x18000a4ef  mov     dword ptr [rsp+3E8h+var_378], eax
0x18000a4f3  mov     ebx, eax
0x18000a4f5  test    eax, eax
0x18000a4f7  jns     short loc_18000A54C
0x18000a4f9  mov     rcx, [rsp+3E8h]; this
0x18000a501  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a508  mov     r9d, eax; char *
0x18000a50b  mov     edx, 2B7h; void *
0x18000a510  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a515  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000a51c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000a521  test    al, al
0x18000a523  jz      short loc_18000A53D
0x18000a525  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000a52c  jz      short loc_18000A53D
0x18000a52e  lea     rdx, EVENT_COPY_PROFILE_DIRECTORY_EXCLUSION_SOURCE_FAILED
0x18000a535  mov     r8d, ebx
0x18000a538  call    McTemplateU0d_EventWriteTransfer
0x18000a53d  movzx   edi, bx
0x18000a540  mov     rbx, [rsp+3E8h+lpDirectoryName]
0x18000a545  mov     esi, ebx
0x18000a547  jmp     loc_18000B0FF
0x18000a54c  bt      r12d, 0Dh
0x18000a551  jb      loc_18000A5E1
0x18000a557  mov     edx, [rsp+3E8h+SystemTimeAsFileTime.dwLowDateTime]
0x18000a55e  lea     rax, [rsp+3E8h+var_370]
0x18000a563  mov     qword ptr [rsp+3E8h+dwFlagsAndAttributes], rax; unsigned int *
0x18000a568  lea     r9d, [r13+1]; unsigned int
0x18000a56c  lea     rax, [rsp+3E8h+var_2E8]
0x18000a574  mov     [rsp+3E8h+var_370], 0
0x18000a57c  inc     edx; unsigned int
0x18000a57e  mov     qword ptr [rsp+3E8h+dwCreationDisposition], rax; int
0x18000a583  mov     r8, r14; unsigned __int16 *
0x18000a586  mov     rcx, rsi; unsigned __int16 *
0x18000a589  call    ?AllocateAndExpandExclusionList@@YAJPEBGK0KPEAPEAGAEAK@Z; AllocateAndExpandExclusionList(ushort const *,ulong,ushort const *,ulong,ushort * *,ulong &)
0x18000a58e  mov     dword ptr [rsp+3E8h+var_378], eax
0x18000a592  mov     ebx, eax
0x18000a594  test    eax, eax
0x18000a596  jns     short loc_18000A5E1
0x18000a598  mov     rcx, [rsp+3E8h]; this
0x18000a5a0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a5a7  mov     r9d, eax; char *
0x18000a5aa  mov     edx, 2D1h; void *
0x18000a5af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a5b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000a5bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000a5c0  test    al, al
0x18000a5c2  jz      loc_18000A53D
0x18000a5c8  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000a5cf  jz      loc_18000A53D
0x18000a5d5  lea     rdx, EVENT_COPY_PROFILE_DIRECTORY_EXCLUSION_DEST_FAILED
0x18000a5dc  jmp     loc_18000A535
0x18000a5e1  bt      r12d, 15h
0x18000a5e6  jb      short loc_18000A643
0x18000a5e8  mov     rcx, rsi; pszSrc
0x18000a5eb  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000a5f0  mov     dword ptr [rsp+3E8h+var_378], eax
0x18000a5f4  mov     ebx, eax
0x18000a5f6  test    eax, eax
0x18000a5f8  jns     short loc_18000A643
0x18000a5fa  mov     rcx, [rsp+3E8h]; this
0x18000a602  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a609  mov     r9d, eax; char *
0x18000a60c  mov     edx, 2EDh; void *
0x18000a611  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a616  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000a61d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000a622  test    al, al
0x18000a624  jz      loc_18000A53D
0x18000a62a  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000a631  jz      loc_18000A53D
0x18000a637  lea     rdx, EVENT_COPY_PROFILE_DIRECTORY_CREATEDIR_FAILED
0x18000a63e  jmp     loc_18000A535
0x18000a643  mov     r13d, 410h
0x18000a649  mov     ebx, 40h ; '@'
0x18000a64e  mov     edx, r13d; uBytes
0x18000a651  mov     ecx, ebx; uFlags
0x18000a653  call    cs:__imp_LocalAlloc
0x18000a659  mov     edx, r13d; uBytes
0x18000a65c  mov     ecx, ebx; uFlags
0x18000a65e  mov     r14, rax
0x18000a661  mov     [rsp+3E8h+lpFileName], rax
0x18000a669  call    cs:__imp_LocalAlloc
0x18000a66f  mov     [rsp+3E8h+lpDirectoryName], rax
0x18000a674  mov     r13, rax
0x18000a677  test    r14, r14
0x18000a67a  jz      loc_18000B0D4
0x18000a680  test    rax, rax
0x18000a683  jz      loc_18000B0D4
0x18000a689  mov     eax, r12d
0x18000a68c  mov     ebx, 208h
0x18000a691  and     eax, 20h
0x18000a694  mov     r8, r15; unsigned __int16 *
0x18000a697  mov     edx, ebx; unsigned __int64
0x18000a699  mov     [rsp+3E8h+var_370], eax
0x18000a69d  mov     rcx, r14; unsigned __int16 *
0x18000a6a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a6a5  mov     r8, rsi; unsigned __int16 *
0x18000a6a8  mov     edx, ebx; unsigned __int64
0x18000a6aa  mov     rcx, r13; unsigned __int16 *
0x18000a6ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a6b2  lea     r8, [rsp+3E8h+var_360]; unsigned int *
0x18000a6ba  mov     edx, ebx; unsigned int
0x18000a6bc  mov     rcx, r14; unsigned __int16 *
0x18000a6bf  call    ?CheckSlash@@YAPEAGPEAGIPEAI@Z; CheckSlash(ushort *,uint,uint *)
0x18000a6c4  lea     r8, [rsp+3E8h+var_348]; unsigned int *
0x18000a6cc  mov     [rsp+3E8h+var_350], rax
0x18000a6d4  mov     edx, ebx; unsigned int
0x18000a6d6  mov     rcx, r13; unsigned __int16 *
0x18000a6d9  call    ?CheckSlash@@YAPEAGPEAGIPEAI@Z; CheckSlash(ushort *,uint,uint *)
0x18000a6de  mov     [rsp+3E8h+var_58], rax
0x18000a6e6  mov     eax, r12d
0x18000a6e9  and     eax, 200h
0x18000a6ee  mov     dword ptr [rsp+3E8h+var_328], eax
0x18000a6f5  jnz     loc_18000A898
0x18000a6fb  lea     r8, [rsp+3E8h+hMem]; unsigned __int16 **
0x18000a703  mov     rcx, r14; unsigned __int16 *
0x18000a706  call    ?_CreateLongPathBuffer@@YAJPEBG_KPEAPEAG@Z; _CreateLongPathBuffer(ushort const *,unsigned __int64,ushort * *)
0x18000a70b  test    eax, eax
0x18000a70d  js      short loc_18000A738
0x18000a70f  lea     r8, [rsp+3E8h+var_2F8]; unsigned __int16 **
0x18000a717  mov     rcx, r13; unsigned __int16 *
0x18000a71a  call    ?_CreateLongPathBuffer@@YAJPEBG_KPEAPEAG@Z; _CreateLongPathBuffer(ushort const *,unsigned __int64,ushort * *)
0x18000a71f  test    eax, eax
0x18000a721  js      short loc_18000A738
0x18000a723  mov     r14, [rsp+3E8h+hMem]
0x18000a72b  mov     ebx, 8000h
0x18000a730  mov     r13, [rsp+3E8h+var_2F8]
0x18000a738  mov     rcx, [rsp+3E8h+TokenHandle]; void *
0x18000a740  lea     rax, [rsp+3E8h+var_378+4]
0x18000a745  mov     [rsp+3E8h+var_390], rax; struct CCopyError *
0x18000a74a  mov     r9, r13; unsigned __int16 *
0x18000a74d  mov     rax, [rsp+3E8h+var_2F0]
0x18000a755  mov     r8d, ebx; unsigned int
0x18000a758  mov     [rsp+3E8h+var_398], 0; int
0x18000a760  mov     rdx, r14; unsigned __int16 *
0x18000a763  mov     [rsp+3E8h+var_3A0], rax; unsigned __int16 *
0x18000a768  lea     rax, [rsp+3E8h+var_358]
0x18000a770  mov     [rsp+3E8h+var_3A8], 1; int
0x18000a778  mov     [rsp+3E8h+var_3B0], rax; struct _FILEINFO **
0x18000a77d  lea     rax, [rsp+3E8h+var_340]
0x18000a785  mov     [rsp+3E8h+hTemplateFile], rax; struct _FILEINFO **
0x18000a78a  mov     [rsp+3E8h+dwFlagsAndAttributes], r12d; unsigned int
0x18000a78f  mov     [rsp+3E8h+dwCreationDisposition], ebx; unsigned int
0x18000a793  call    ?RecurseDirectory@@YAHPEAXPEAGK1KKPEAPEAU_FILEINFO@@2HPEBGHAEAVCCopyError@@@Z; RecurseDirectory(void *,ushort *,ulong,ushort *,ulong,ulong,_FILEINFO * *,_FILEINFO * *,int,ushort const *,int,CCopyError &)
0x18000a798  test    eax, eax
0x18000a79a  jnz     short loc_18000A7F2
0x18000a79c  call    cs:__imp_GetLastError
0x18000a7a2  mov     edi, eax
0x18000a7a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000a7ab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000a7b0  test    al, al
0x18000a7b2  jz      short loc_18000A7CC
0x18000a7b4  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000a7bb  jz      short loc_18000A7CC
0x18000a7bd  mov     r8d, edi
0x18000a7c0  lea     rdx, EVENT_COPY_PROFILE_DIRECTORY_RECURSE_SOURCE_FAILED
0x18000a7c7  call    McTemplateU0d_EventWriteTransfer
0x18000a7cc  mov     edx, 35Ch; void *
0x18000a7d1  mov     r9d, edi; char *
0x18000a7d4  mov     rcx, [rsp+3E8h]; this
0x18000a7dc  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a7e3  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000a7e8  mov     rbx, [rsp+3E8h+lpDirectoryName]
0x18000a7ed  jmp     loc_18000B0FB
  ... truncated ...
```
