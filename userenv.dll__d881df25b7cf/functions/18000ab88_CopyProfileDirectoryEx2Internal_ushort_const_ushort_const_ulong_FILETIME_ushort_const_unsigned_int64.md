# CopyProfileDirectoryEx2Internal(ushort const *,ushort const *,ulong,_FILETIME *,ushort const *,unsigned __int64)

- ea: `0x18000ab88`
- end: `0x18000bca0`
- name: `?CopyProfileDirectoryEx2Internal@@YAHPEBG0KPEAU_FILETIME@@0_K@Z`
- size: `4376`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, struct _FILETIME *@<r9>, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180015650`

## callees

- `0x1800067b8`
- `0x180006e18`
- `0x180007590`
- `0x180007724`
- `0x18000778c`
- `0x1800077c4`
- `0x180007b20`
- `0x180007f80`
- `0x180008dd8`
- `0x180009344`
- `0x180009ddc`
- `0x18000a200`
- `0x18000ab88`
- `0x18000bca8`
- `0x18000bd3c`
- `0x18000c8c0`
- `0x18000cce0`
- `0x18000da4c`
- `0x18000ddf0`
- `0x18000e640`
- `0x18000efe0`
- `0x180019404`
- `0x18001b220`
- `0x18001b334`
- `0x18001b3b4`
- `0x18001b61c`
- `0x18001b6a4`
- `0x18001b704`
- `0x18001b75c`
- `0x18001b914`
- `0x18001b9c4`
- `0x18001bc04`
- `0x18001bcc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ad97`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ad97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ad75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ad75`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000add3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000add3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000adba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000adba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bc59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bc6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bc59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bc6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ada7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ada7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000baa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000baa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000afff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b01b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000afff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b01b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b688`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b757`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b688`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b757`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000b4b7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000b4b7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ba5d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ba5d`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000ba7e`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000ba7e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000b82f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000b82f`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18000b320`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18000b320`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000b7e4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000b7e4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000b7b0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000ba28`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000baca`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000b7b0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000ba28`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000baca`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b78b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b78b`

## string_xrefs

- `0x18000ad0a`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000aead`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000af4c`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000afae`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000b19a`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000b344`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000b6e4`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000b80e`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000b87d`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000b991`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000bb18`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

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
                            (const unsigned __int16 *)v110,
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
                            (const unsigned __int16 *)v111,
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
0x18000ab88  mov     r11, rsp
0x18000ab8b  push    rbx
0x18000ab8c  push    rsi
0x18000ab8d  push    rdi
0x18000ab8e  push    r12
0x18000ab90  push    r13
0x18000ab92  push    r14
0x18000ab94  push    r15
0x18000ab96  sub     rsp, 3B0h
0x18000ab9d  mov     rax, cs:__security_cookie
0x18000aba4  xor     rax, rsp
0x18000aba7  mov     [rsp+3E8h+var_48], rax
0x18000abaf  mov     r14, [rsp+3E8h+arg_20]
0x18000abb7  mov     r12d, r8d
0x18000abba  mov     rsi, rdx
0x18000abbd  mov     [rsp+3E8h+var_2D0], r9
0x18000abc5  mov     r15, rcx
0x18000abc8  mov     qword ptr [r11-300h], 0
0x18000abd3  xor     edx, edx; Val
0x18000abd5  mov     qword ptr [r11-2F8h], 0
0x18000abe0  mov     r8d, 250h; Size
0x18000abe6  mov     qword ptr [r11-2F0h], 0
0x18000abf1  lea     rcx, [r11-2B8h]; void *
0x18000abf8  mov     qword ptr [r11-2E8h], 0
0x18000ac03  mov     qword ptr [r11-358h], 0
0x18000ac0e  mov     qword ptr [r11-320h], 0
0x18000ac19  mov     qword ptr [r11-340h], 0
0x18000ac24  mov     qword ptr [r11-2E0h], 0
0x18000ac2f  call    memset_0
0x18000ac34  mov     qword ptr [rsp+3E8h+var_330.dwLowDateTime], 0
0x18000ac40  mov     [rsp+3E8h+var_68], 0
0x18000ac4c  mov     [rsp+3E8h+var_318], 0
0x18000ac58  mov     qword ptr [rsp+3E8h+FreeBytesAvailableToCaller], 0
0x18000ac64  mov     qword ptr [rsp+3E8h+TotalNumberOfBytes], 0
0x18000ac70  mov     qword ptr [rsp+3E8h+TotalNumberOfFreeBytes], 0
0x18000ac7c  mov     [rsp+3E8h+TokenHandle], 0
0x18000ac88  mov     [rsp+3E8h+var_328], 0
0x18000ac94  mov     qword ptr [rsp+3E8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000aca0  mov     [rsp+3E8h+var_360], 0
0x18000acab  mov     [rsp+3E8h+var_348], 0
0x18000acb6  mov     dword ptr [rsp+3E8h+var_378+4], 0
0x18000acbe  call    cs:__imp_GetLastError
0x18000acc5  nop     dword ptr [rax+rax+00h]
0x18000acca  mov     edi, eax
0x18000accc  test    r15, r15
0x18000accf  jz      loc_18000BC69
0x18000acd5  test    rsi, rsi
0x18000acd8  jz      loc_18000BC69
0x18000acde  mov     r10d, 104h
0x18000ace4  lea     r8, [rsp+3E8h+var_328]; unsigned __int64 *
0x18000acec  mov     edx, r10d; unsigned __int64
0x18000acef  mov     rcx, r15; unsigned __int16 *
0x18000acf2  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000acf7  mov     ebx, eax
0x18000acf9  test    eax, eax
0x18000acfb  jns     short loc_18000AD21
0x18000acfd  mov     edx, 273h; void *
0x18000ad02  mov     rcx, [rsp+3E8h]; this
0x18000ad0a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000ad11  mov     r9d, ebx; char *
0x18000ad14  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ad19  movzx   ecx, bx
0x18000ad1c  jmp     loc_18000BC6E
0x18000ad21  lea     r8, [rsp+3E8h+SystemTimeAsFileTime]; unsigned __int64 *
0x18000ad29  mov     rdx, r10; unsigned __int64
0x18000ad2c  mov     rcx, rsi; unsigned __int16 *
0x18000ad2f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000ad34  mov     dword ptr [rsp+3E8h+var_378], eax
0x18000ad38  mov     ebx, eax
0x18000ad3a  test    eax, eax
0x18000ad3c  jns     short loc_18000AD45
0x18000ad3e  mov     edx, 27Bh
0x18000ad43  jmp     short loc_18000AD02
0x18000ad45  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000ad4c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000ad51  test    al, al
0x18000ad53  jz      short loc_18000AD75
0x18000ad55  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000ad5c  jz      short loc_18000AD75
0x18000ad5e  mov     r9, rsi
0x18000ad61  mov     [rsp+3E8h+dwCreationDisposition], r12d; unsigned int
0x18000ad66  mov     r8, r15
0x18000ad69  lea     rdx, EVENT_COPY_PROFILE_DIRECTORY_START
0x18000ad70  call    McTemplateU0zzd_EventWriteTransfer
0x18000ad75  call    cs:__imp_GetCurrentThread
0x18000ad7c  nop     dword ptr [rax+rax+00h]
0x18000ad81  mov     ebx, 0Eh
0x18000ad86  lea     r9, [rsp+3E8h+TokenHandle]; TokenHandle
0x18000ad8e  mov     rcx, rax; ThreadHandle
0x18000ad91  mov     edx, ebx; DesiredAccess
0x18000ad93  lea     r8d, [rbx-0Dh]; OpenAsSelf
0x18000ad97  call    cs:__imp_OpenThreadToken
0x18000ad9e  nop     dword ptr [rax+rax+00h]
0x18000ada3  test    eax, eax
0x18000ada5  jnz     short loc_18000ADFA
0x18000ada7  call    cs:__imp_GetLastError
0x18000adae  nop     dword ptr [rax+rax+00h]
0x18000adb3  cmp     eax, 3F0h
0x18000adb8  jnz     short loc_18000ADE3
0x18000adba  call    cs:__imp_GetCurrentProcess
0x18000adc1  nop     dword ptr [rax+rax+00h]
0x18000adc6  lea     r8, [rsp+3E8h+TokenHandle]; TokenHandle
0x18000adce  mov     edx, ebx; DesiredAccess
0x18000add0  mov     rcx, rax; ProcessHandle
0x18000add3  call    cs:__imp_OpenProcessToken
0x18000adda  nop     dword ptr [rax+rax+00h]
0x18000addf  test    eax, eax
0x18000ade1  jnz     short loc_18000ADFA
0x18000ade3  mov     rcx, [rsp+3E8h]; this
0x18000adeb  mov     edx, 292h; void *
0x18000adf0  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18000adf5  jmp     loc_18000BC7A
0x18000adfa  mov     [rsp+3E8h+lpFileName], 0
0x18000ae06  mov     [rsp+3E8h+lpDirectoryName], 0
0x18000ae0f  mov     [rsp+3E8h+var_388], 0
0x18000ae17  bt      r12d, 0Bh
0x18000ae1c  jnb     loc_18000AF8D
0x18000ae22  test    r14, r14
0x18000ae25  jz      loc_18000AF8D
0x18000ae2b  lea     r8, [rsp+3E8h+var_350]; unsigned __int64 *
0x18000ae33  mov     [rsp+3E8h+var_350], 0
0x18000ae3f  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000ae44  mov     rcx, r14; unsigned __int16 *
0x18000ae47  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000ae4c  mov     ebx, eax
0x18000ae4e  test    eax, eax
0x18000ae50  jns     short loc_18000AE5C
0x18000ae52  mov     edx, 2A2h
0x18000ae57  jmp     loc_18000AD02
0x18000ae5c  mov     edx, dword ptr [rsp+3E8h+var_328]
0x18000ae63  lea     rax, [rsp+3E8h+var_370]
0x18000ae68  mov     r13d, dword ptr [rsp+3E8h+var_350]
0x18000ae70  inc     edx; unsigned int
0x18000ae72  mov     qword ptr [rsp+3E8h+dwFlagsAndAttributes], rax; unsigned int *
0x18000ae77  mov     r8, r14; unsigned __int16 *
0x18000ae7a  lea     rax, [rsp+3E8h+var_2F0]
0x18000ae82  mov     [rsp+3E8h+var_370], 0
0x18000ae8a  mov     rcx, r15; unsigned __int16 *
0x18000ae8d  mov     qword ptr [rsp+3E8h+dwCreationDisposition], rax; int
0x18000ae92  lea     r9d, [r13+1]; unsigned int
0x18000ae96  call    ?AllocateAndExpandExclusionList@@YAJPEBGK0KPEAPEAGAEAK@Z; AllocateAndExpandExclusionList(ushort const *,ulong,ushort const *,ulong,ushort * *,ulong &)
0x18000ae9b  mov     dword ptr [rsp+3E8h+var_378], eax
0x18000ae9f  mov     ebx, eax
0x18000aea1  test    eax, eax
0x18000aea3  jns     short loc_18000AEF8
0x18000aea5  mov     rcx, [rsp+3E8h]; this
0x18000aead  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000aeb4  mov     r9d, eax; char *
0x18000aeb7  mov     edx, 2B7h; void *
0x18000aebc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000aec1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000aec8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000aecd  test    al, al
0x18000aecf  jz      short loc_18000AEE9
0x18000aed1  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000aed8  jz      short loc_18000AEE9
0x18000aeda  lea     rdx, EVENT_COPY_PROFILE_DIRECTORY_EXCLUSION_SOURCE_FAILED
0x18000aee1  mov     r8d, ebx
0x18000aee4  call    McTemplateU0d_EventWriteTransfer
0x18000aee9  movzx   edi, bx
0x18000aeec  mov     rbx, [rsp+3E8h+lpDirectoryName]
0x18000aef1  mov     esi, ebx
0x18000aef3  jmp     loc_18000BB35
0x18000aef8  bt      r12d, 0Dh
0x18000aefd  jb      loc_18000AF8D
0x18000af03  mov     edx, [rsp+3E8h+SystemTimeAsFileTime.dwLowDateTime]
0x18000af0a  lea     rax, [rsp+3E8h+var_370]
0x18000af0f  mov     qword ptr [rsp+3E8h+dwFlagsAndAttributes], rax; unsigned int *
0x18000af14  lea     r9d, [r13+1]; unsigned int
0x18000af18  lea     rax, [rsp+3E8h+var_2E8]
0x18000af20  mov     [rsp+3E8h+var_370], 0
0x18000af28  inc     edx; unsigned int
0x18000af2a  mov     qword ptr [rsp+3E8h+dwCreationDisposition], rax; int
0x18000af2f  mov     r8, r14; unsigned __int16 *
0x18000af32  mov     rcx, rsi; unsigned __int16 *
0x18000af35  call    ?AllocateAndExpandExclusionList@@YAJPEBGK0KPEAPEAGAEAK@Z; AllocateAndExpandExclusionList(ushort const *,ulong,ushort const *,ulong,ushort * *,ulong &)
0x18000af3a  mov     dword ptr [rsp+3E8h+var_378], eax
0x18000af3e  mov     ebx, eax
0x18000af40  test    eax, eax
0x18000af42  jns     short loc_18000AF8D
0x18000af44  mov     rcx, [rsp+3E8h]; this
0x18000af4c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000af53  mov     r9d, eax; char *
0x18000af56  mov     edx, 2D1h; void *
0x18000af5b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000af60  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000af67  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000af6c  test    al, al
0x18000af6e  jz      loc_18000AEE9
0x18000af74  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000af7b  jz      loc_18000AEE9
0x18000af81  lea     rdx, EVENT_COPY_PROFILE_DIRECTORY_EXCLUSION_DEST_FAILED
0x18000af88  jmp     loc_18000AEE1
0x18000af8d  bt      r12d, 15h
0x18000af92  jb      short loc_18000AFEF
0x18000af94  mov     rcx, rsi; pszSrc
0x18000af97  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000af9c  mov     dword ptr [rsp+3E8h+var_378], eax
0x18000afa0  mov     ebx, eax
0x18000afa2  test    eax, eax
0x18000afa4  jns     short loc_18000AFEF
0x18000afa6  mov     rcx, [rsp+3E8h]; this
0x18000afae  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000afb5  mov     r9d, eax; char *
0x18000afb8  mov     edx, 2EDh; void *
0x18000afbd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000afc2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000afc9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000afce  test    al, al
0x18000afd0  jz      loc_18000AEE9
0x18000afd6  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000afdd  jz      loc_18000AEE9
0x18000afe3  lea     rdx, EVENT_COPY_PROFILE_DIRECTORY_CREATEDIR_FAILED
0x18000afea  jmp     loc_18000AEE1
0x18000afef  mov     r13d, 410h
0x18000aff5  mov     ebx, 40h ; '@'
0x18000affa  mov     edx, r13d; uBytes
0x18000affd  mov     ecx, ebx; uFlags
0x18000afff  call    cs:__imp_LocalAlloc
0x18000b006  nop     dword ptr [rax+rax+00h]
0x18000b00b  mov     edx, r13d; uBytes
0x18000b00e  mov     ecx, ebx; uFlags
0x18000b010  mov     r14, rax
0x18000b013  mov     [rsp+3E8h+lpFileName], rax
0x18000b01b  call    cs:__imp_LocalAlloc
0x18000b022  nop     dword ptr [rax+rax+00h]
0x18000b027  mov     [rsp+3E8h+lpDirectoryName], rax
0x18000b02c  mov     r13, rax
0x18000b02f  test    r14, r14
0x18000b032  jz      loc_18000BB04
0x18000b038  test    rax, rax
0x18000b03b  jz      loc_18000BB04
0x18000b041  mov     eax, r12d
0x18000b044  mov     ebx, 208h
0x18000b049  and     eax, 20h
0x18000b04c  mov     r8, r15; unsigned __int16 *
0x18000b04f  mov     edx, ebx; unsigned __int64
0x18000b051  mov     [rsp+3E8h+var_370], eax
0x18000b055  mov     rcx, r14; unsigned __int16 *
0x18000b058  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b05d  mov     r8, rsi; unsigned __int16 *
0x18000b060  mov     edx, ebx; unsigned __int64
0x18000b062  mov     rcx, r13; unsigned __int16 *
0x18000b065  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b06a  lea     r8, [rsp+3E8h+var_360]; unsigned int *
0x18000b072  mov     edx, ebx; unsigned int
0x18000b074  mov     rcx, r14; unsigned __int16 *
0x18000b077  call    ?CheckSlash@@YAPEAGPEAGIPEAI@Z; CheckSlash(ushort *,uint,uint *)
0x18000b07c  lea     r8, [rsp+3E8h+var_348]; unsigned int *
0x18000b084  mov     [rsp+3E8h+var_350], rax
0x18000b08c  mov     edx, ebx; unsigned int
0x18000b08e  mov     rcx, r13; unsigned __int16 *
0x18000b091  call    ?CheckSlash@@YAPEAGPEAGIPEAI@Z; CheckSlash(ushort *,uint,uint *)
0x18000b096  mov     [rsp+3E8h+var_58], rax
0x18000b09e  mov     eax, r12d
0x18000b0a1  and     eax, 200h
0x18000b0a6  mov     dword ptr [rsp+3E8h+var_328], eax
0x18000b0ad  jnz     loc_18000B25C
0x18000b0b3  lea     r8, [rsp+3E8h+hMem]; unsigned __int16 **
0x18000b0bb  mov     rcx, r14; unsigned __int16 *
0x18000b0be  call    ?_CreateLongPathBuffer@@YAJPEBG_KPEAPEAG@Z; _CreateLongPathBuffer(ushort const *,unsigned __int64,ushort * *)
0x18000b0c3  test    eax, eax
0x18000b0c5  js      short loc_18000B0F0
0x18000b0c7  lea     r8, [rsp+3E8h+var_2F8]; unsigned __int16 **
0x18000b0cf  mov     rcx, r13; unsigned __int16 *
0x18000b0d2  call    ?_CreateLongPathBuffer@@YAJPEBG_KPEAPEAG@Z; _CreateLongPathBuffer(ushort const *,unsigned __int64,ushort * *)
0x18000b0d7  test    eax, eax
0x18000b0d9  js      short loc_18000B0F0
0x18000b0db  mov     r14, [rsp+3E8h+hMem]
0x18000b0e3  mov     ebx, 8000h
0x18000b0e8  mov     r13, [rsp+3E8h+var_2F8]
0x18000b0f0  mov     rcx, [rsp+3E8h+TokenHandle]; void *
0x18000b0f8  lea     rax, [rsp+3E8h+var_378+4]
0x18000b0fd  mov     [rsp+3E8h+var_390], rax; struct CCopyError *
0x18000b102  mov     r9, r13; unsigned __int16 *
0x18000b105  mov     rax, [rsp+3E8h+var_2F0]
0x18000b10d  mov     r8d, ebx; unsigned int
0x18000b110  mov     [rsp+3E8h+var_398], 0; int
0x18000b118  mov     rdx, r14; unsigned __int16 *
0x18000b11b  mov     [rsp+3E8h+var_3A0], rax; unsigned __int16 *
0x18000b120  lea     rax, [rsp+3E8h+var_358]
0x18000b128  mov     [rsp+3E8h+var_3A8], 1; int
0x18000b130  mov     [rsp+3E8h+var_3B0], rax; struct _FILEINFO **
0x18000b135  lea     rax, [rsp+3E8h+var_340]
0x18000b13d  mov     [rsp+3E8h+hTemplateFile], rax; struct _FILEINFO **
0x18000b142  mov     [rsp+3E8h+dwFlagsAndAttributes], r12d; unsigned int
0x18000b147  mov     [rsp+3E8h+dwCreationDisposition], ebx; unsigned int
0x18000b14b  call    ?RecurseDirectory@@YAHPEAXPEAGK1KKPEAPEAU_FILEINFO@@2HPEBGHAEAVCCopyError@@@Z; RecurseDirectory(void *,ushort *,ulong,ushort *,ulong,ulong,_FILEINFO * *,_FILEINFO * *,int,ushort const *,int,CCopyError &)
0x18000b150  test    eax, eax
0x18000b152  jnz     short loc_18000B1B0
0x18000b154  call    cs:__imp_GetLastError
0x18000b15b  nop     dword ptr [rax+rax+00h]
0x18000b160  mov     edi, eax
0x18000b162  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000b169  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000b16e  test    al, al
0x18000b170  jz      short loc_18000B18A
0x18000b172  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000b179  jz      short loc_18000B18A
0x18000b17b  mov     r8d, edi
  ... truncated ...
```
