# WdsLoad(wchar_t const *,HINSTANCE__ *)

- ea: `0x180011e10`
- end: `0x180012e71`
- name: `?WdsLoad@@YAJPEB_WPEAUHINSTANCE__@@@Z`
- size: `4193`
- prototype: `__int64 __fastcall(const wchar_t *, HINSTANCE)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800130b8`

## callees

- `0x180001de0`
- `0x1800020d0`
- `0x1800054f0`
- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18000ed98`
- `0x180010448`
- `0x180010750`
- `0x180010de4`
- `0x180011248`
- `0x1800118a4`
- `0x1800119e8`
- `0x180011b54`
- `0x180011bc0`
- `0x180011bec`
- `0x180011e10`
- `0x1800138a0`
- `0x180014054`
- `0x180014470`
- `0x1800147b0`
- `0x180014ce0`
- `0x18001b77a`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!wcstoul` at `0x180012bcf`
- `msvcrt!wcstoul` at `0x180012bcf`
- `msvcrt!_errno` at `0x180012bdc`
- `msvcrt!_errno` at `0x180012bdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001248d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001251a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001248d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001251a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012634`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800122d4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012361`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800123ee`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001247b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012508`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012595`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012622`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012d77`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800122d4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012361`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800123ee`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001247b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012508`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012595`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012622`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012d77`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800120a9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18001215f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800120a9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18001215f`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800126c3`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180012baa`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800126c3`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180012baa`

## string_xrefs

- `0x180012083`: `wdscore.dll`
- `0x180012132`: `wdscore.dll`
- `0x180011e97`: `Wds logger is already initialized`
- `0x180011f0f`: `No core dll path specified`
- `0x180011fab`: `Failed to get windows directory for WDSCORE DLL path.`
- `0x180012139`: `system32\`
- `0x1800121aa`: `Could not load WDSCORE DLL from path: {}. Continuing without text file logging.`
- `0x180012214`: `Failed to load WDSCORE DLL: {}`
- `0x1800126bc`: `COMPONENT_BASED_SERVICING_LOGFILE`
- `0x1800127d0`: `Failed to get log path from: {}`
- `0x1800129f5`: `Failed to ensure that logging directory exists: {}`
- `0x180012aa1`: `WDS logging is not enabled in the registry, continuing without logging.`
- `0x180012b45`: `Failed to initialize logging with DLL: {}, log file: {}`
- `0x180012ba3`: `COMPONENT_BASED_SERVICING_LOGLEVEL`
- `0x180012d03`: `Failed to configure logging settings`

## pseudocode

```c
__int64 __fastcall WdsLoad(const wchar_t *a1, HINSTANCE a2)
{
  wchar_t *v3; // rsi
  int v4; // r15d
  unsigned int *v5; // r14
  unsigned int v6; // r13d
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  int WindowsDirectory; // eax
  __int64 v12; // rcx
  char *v13; // rcx
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  wchar_t *v16; // rbx
  HMODULE LibraryW; // rax
  wchar_t *v18; // rdi
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  signed int LastError; // esi
  __int64 v23; // rdx
  __int64 v24; // rcx
  DWORD v25; // esi
  __int64 v26; // rcx
  __int64 v27; // r8
  wchar_t *v28; // rcx
  __int64 v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // rdx
  int v32; // esi
  wchar_t *v33; // rcx
  wchar_t *v34; // rcx
  __int64 v35; // rcx
  unsigned int v36; // eax
  __int64 v37; // rcx
  unsigned int v38; // eax
  __int64 v39; // rcx
  unsigned int v40; // eax
  __int64 v41; // rcx
  unsigned int v42; // eax
  __int64 v43; // rcx
  unsigned int v44; // eax
  __int64 v45; // rcx
  unsigned int v46; // eax
  __int64 v47; // rcx
  unsigned int v48; // eax
  const wchar_t *v49; // rdx
  HKEY v50; // rcx
  __int64 v51; // r8
  const wchar_t *v52; // r9
  __int64 v53; // rdx
  const wchar_t *v54; // rdx
  HKEY v55; // rcx
  __int64 v56; // r8
  const wchar_t *v57; // r9
  unsigned int v58; // r15d
  int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // rcx
  unsigned int v62; // r14d
  __int64 v63; // rcx
  __int64 v64; // rcx
  int v65; // eax
  int v66; // eax
  int Directory; // eax
  __int64 v68; // rdx
  __int64 v69; // rcx
  unsigned int v70; // r12d
  __int64 v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // rcx
  struct ILogManager *SetupLog; // r12
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // rcx
  unsigned int v78; // r15d
  __int64 v79; // rdx
  __int64 v80; // rcx
  int v81; // eax
  __int64 v82; // rdx
  __int64 v83; // rcx
  FARPROC ProcAddress; // rax
  char v85; // [rsp+50h] [rbp-B0h] BYREF
  char v86; // [rsp+51h] [rbp-AFh]
  LPCWSTR lpLibFileName; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int *v88; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v89; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *EndPtr; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v91; // [rsp+78h] [rbp-88h] BYREF
  int v92; // [rsp+80h] [rbp-80h]
  __int64 v93; // [rsp+84h] [rbp-7Ch]
  int v94; // [rsp+8Ch] [rbp-74h]
  _QWORD v95[3]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v96[7]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v97[4]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR String[64]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Buffer[512]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5C8h] [rbp+4C8h]

  v3 = 0;
  v89 = 0;
  lpLibFileName = 0;
  v4 = 0;
  EndPtr = 0;
  v5 = 0;
  v6 = 1;
  v97[0] = 0;
  v86 = 1;
  v88 = 0;
  if ( _InterlockedIncrement(&vcWdsLoadOperations) > 1 )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Wds logger is already initialized");
      v97[0] = -2147023649;
      EndPtr = (wchar_t *)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v7,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&EndPtr);
    }
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x284,
           (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
           (const char *)0x4DF);
LABEL_9:
    wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
    return (unsigned int)v8;
  }
  if ( !a1 )
  {
    v8 = -2147024809;
    v97[0] = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No core dll path specified");
      EndPtr = (wchar_t *)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v9,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&EndPtr);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x287,
      (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)0x80070057LL);
    goto LABEL_9;
  }
  WindowsDirectory = PathGetWindowsDirectory(&EndPtr, a2);
  v8 = WindowsDirectory;
  if ( WindowsDirectory < 0 )
  {
    v97[0] = WindowsDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get windows directory for WDSCORE DLL path.");
      v88 = v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v12,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v88);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28A,
      (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v8);
    wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
    v13 = (char *)EndPtr;
    goto LABEL_15;
  }
  v8 = SczAllocFromSz(&lpLibFileName, a1);
  if ( v8 < 0 )
  {
    v14 = 652;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v8);
    wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
    if ( !EndPtr )
    {
LABEL_22:
      v13 = (char *)lpLibFileName;
LABEL_15:
      if ( v13 )
        operator delete(v13 - 8);
      return (unsigned int)v8;
    }
    v15 = EndPtr - 4;
LABEL_21:
    operator delete(v15);
    goto LABEL_22;
  }
  v8 = SczEnsureBackslashTerminated(&lpLibFileName);
  if ( v8 < 0 )
  {
    v14 = 653;
    goto LABEL_19;
  }
  v8 = SczAllocConcatSz(&lpLibFileName, L"wdscore.dll");
  if ( v8 < 0 )
  {
    v14 = 654;
    goto LABEL_19;
  }
  v16 = (wchar_t *)lpLibFileName;
  LibraryW = LoadLibraryW(lpLibFileName);
  if ( vhWdsDll )
    goto LABEL_234;
  v18 = EndPtr;
  vhWdsDll = LibraryW;
  if ( LibraryW )
    goto LABEL_65;
  v8 = SczAllocFromSz(&lpLibFileName, EndPtr);
  if ( v8 < 0 )
  {
    v19 = 659;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v8);
    wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
    if ( !v18 )
      goto LABEL_22;
    v15 = v18 - 4;
    goto LABEL_21;
  }
  v8 = SczEnsureBackslashTerminated(&lpLibFileName);
  if ( v8 < 0 )
  {
    v19 = 660;
    goto LABEL_31;
  }
  v8 = SczAllocConcat2Sz(&lpLibFileName, L"system32\\", L"wdscore.dll");
  if ( v8 < 0 )
  {
    v19 = 661;
    goto LABEL_31;
  }
  v16 = (wchar_t *)lpLibFileName;
  LibraryW = LoadLibraryW(lpLibFileName);
  if ( vhWdsDll )
LABEL_234:
    INTERNAL_ERROR_ACTION(-1073741595);
  vhWdsDll = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    if ( LastError == 126 )
    {
      EndPtr = v16;
      v25 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<wchar_t const *>(
          v24,
          v23,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Could not load WDSCORE DLL from path: {}. Continuing without"
                                                            " text file logging.",
          (__int64)&EndPtr);
        v97[0] = v25;
        v88 = v97;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>(v26, 0, v27, &v88);
      }
      v86 = 0;
      wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
      if ( v18 )
        operator delete(v18 - 4);
      if ( !v16 )
        return v6;
      v28 = v16 - 4;
LABEL_46:
      operator delete(v28);
      return v6;
    }
    if ( LogAdapter::g_Logger )
    {
      EndPtr = v16;
      LogAdapter::Logger::LogPartial<wchar_t const *>(
        v21,
        v20,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load WDSCORE DLL: {}",
        (__int64)&EndPtr);
      if ( LastError > 0 )
        v30 = (unsigned __int16)LastError | 0x80070000;
      else
        v30 = LastError;
      v97[0] = v30;
      v88 = v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v29,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v88);
    }
    if ( LastError )
    {
      v31 = 674;
LABEL_55:
      v32 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v31,
              (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
              (const char *)(unsigned int)LastError);
      wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
      if ( v18 )
        operator delete(v18 - 4);
      if ( !v16 )
        return (unsigned int)v32;
      v33 = v16 - 4;
LABEL_59:
      operator delete(v33);
      return (unsigned int)v32;
    }
    goto LABEL_61;
  }
LABEL_65:
  vpfnWdsSetupLogInit = (struct ILogManager *(*)(HINSTANCE, unsigned int, const wchar_t *))GetProcAddress(
                                                                                             LibraryW,
                                                                                             "WdsSetupLogInit");
  if ( !vpfnWdsSetupLogInit )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for WdsSetupLogInit.");
      if ( LastError > 0 )
        v36 = (unsigned __int16)LastError | 0x80070000;
      else
        v36 = LastError;
      v97[0] = v36;
      EndPtr = (wchar_t *)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v35,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&EndPtr);
    }
    if ( LastError )
    {
      v31 = 679;
      goto LABEL_55;
    }
    goto LABEL_61;
  }
  vpfnWdsGenericSetupLogInit = (int (*)(const wchar_t *, unsigned int))GetProcAddress(
                                                                         vhWdsDll,
                                                                         "WdsGenericSetupLogInit");
  if ( !vpfnWdsGenericSetupLogInit )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for WdsGenericSetupLogInit.");
      if ( LastError > 0 )
        v38 = (unsigned __int16)LastError | 0x80070000;
      else
        v38 = LastError;
      v97[0] = v38;
      EndPtr = (wchar_t *)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v37,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&EndPtr);
    }
    if ( LastError )
    {
      v31 = 682;
      goto LABEL_55;
    }
    goto LABEL_61;
  }
  vpfnWdsGetSetupLog = (struct ILogManager *(*)(void))GetProcAddress(vhWdsDll, "WdsGetSetupLog");
  if ( !vpfnWdsGetSetupLog )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for WdsGetSetupLog.");
      if ( LastError > 0 )
        v40 = (unsigned __int16)LastError | 0x80070000;
      else
        v40 = LastError;
      v97[0] = v40;
      EndPtr = (wchar_t *)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v39,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&EndPtr);
    }
    if ( LastError )
    {
      v31 = 685;
      goto LABEL_55;
    }
    goto LABEL_61;
  }
  vpfnWdsSetupLogDestroy = (void (*)(void))GetProcAddress(vhWdsDll, "WdsSetupLogDestroy");
  if ( !vpfnWdsSetupLogDestroy )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for WdsSetupLogDestroy.");
      if ( LastError > 0 )
        v42 = (unsigned __int16)LastError | 0x80070000;
      else
        v42 = LastError;
      v97[0] = v42;
      EndPtr = (wchar_t *)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v41,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&EndPtr);
    }
    if ( LastError )
    {
      v31 = 689;
      goto LABEL_55;
    }
    goto LABEL_61;
  }
  vpfnWdsSetupLogMessageA = (enum tagLOGRESULT (__high *)(struct tagLOG_PARTIAL_MSG *, unsigned int, const char *, const char *, unsigned int, const char *, const char *, void *, unsigned int, void *, unsigned int))GetProcAddress(vhWdsDll, "WdsSetupLogMessageA");
  if ( !vpfnWdsSetupLogMessageA )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for WdsSetupLogMessageA.");
      if ( LastError > 0 )
        v44 = (unsigned __int16)LastError | 0x80070000;
      else
        v44 = LastError;
      v97[0] = v44;
      EndPtr = (wchar_t *)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v43,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&EndPtr);
    }
    if ( LastError )
    {
      v31 = 692;
      goto LABEL_55;
    }
    goto LABEL_61;
  }
  vpfnConstructPartialMsgVA = (struct tagLOG_PARTIAL_MSG *(*)(unsigned int, const char *, char *))GetProcAddress(
                                                                                                    vhWdsDll,
                                                                                                    "ConstructPartialMsgVA");
  if ( !vpfnConstructPartialMsgVA )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for ConstructPartialMsgVA.");
      if ( LastError > 0 )
        v46 = (unsigned __int16)LastError | 0x80070000;
      else
        v46 = LastError;
      v97[0] = v46;
      EndPtr = (wchar_t *)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v45,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&EndPtr);
    }
    if ( LastError )
    {
      v31 = 695;
      goto LABEL_55;
    }
    goto LABEL_61;
  }
  vpfnCurrentIP = (void *(*)(void))GetProcAddress(vhWdsDll, "CurrentIP");
  if ( !vpfnCurrentIP )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for CurrentIP.");
      if ( LastError > 0 )
        v48 = (unsigned __int16)LastError | 0x80070000;
      else
        v48 = LastError;
      v97[0] = v48;
      EndPtr = (wchar_t *)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v47,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&EndPtr);
    }
    if ( LastError )
    {
      v31 = 698;
      goto LABEL_55;
    }
LABEL_61:
    wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
    if ( v18 )
      operator delete(v18 - 4);
    if ( !v16 )
      return 0;
    v34 = v16 - 4;
LABEL_216:
    operator delete(v34);
    return 0;
  }
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( GetEnvironmentVariableW(L"COMPONENT_BASED_SERVICING_LOGFILE", Buffer, 0x200u) - 1 <= 0x1FE )
  {
    v32 = SczAllocFromSz(&v89, Buffer);
    if ( v32 < 0 )
    {
      v53 = 729;
LABEL_124:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v53,
        (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
        (const char *)(unsigned int)v32);
      wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
LABEL_125:
      if ( v18 )
        operator delete(v18 - 4);
      if ( v16 )
        operator delete(v16 - 4);
      if ( !v89 )
        return (unsigned int)v32;
      v33 = v89 - 4;
      goto LABEL_59;
    }
    v3 = v89;
    v4 = 1;
    v97[0] = 1;
  }
  v6 = 0;
  if ( v4 )
  {
LABEL_189:
    if ( !(unsigned int)((__int64 (__fastcall *)(wchar_t *, __int64))vpfnWdsGenericSetupLogInit)(v3, 0x8000) )
    {
      v70 = -2147467259;
      v97[0] = -2147467259;
      if ( LogAdapter::g_Logger )
      {
        EndPtr = v3;
        v88 = (unsigned int *)v16;
        LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *>(
          v76,
          v75,
          "Failed to initialize logging with DLL: {}, log file: {}",
          &v88,
          &EndPtr);
        lpLibFileName = (LPCWSTR)v97;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v77,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&lpLibFileName);
      }
      v72 = 883;
      goto LABEL_176;
    }
    v78 = 1024;
    memset_0(String, 0, sizeof(String));
    if ( GetEnvironmentVariableW(L"COMPONENT_BASED_SERVICING_LOGLEVEL", String, 0x40u) - 1 <= 0x3E )
    {
      EndPtr = 0;
      v78 = wcstoul(String, &EndPtr, 16);
      if ( !v78 && *_errno() == 34 )
        v78 = 1024;
    }
    SetupLog = vpfnWdsGetSetupLog();
    if ( !SetupLog )
    {
      LogAdapter::TraceAtLevelHr<long,>(v80, v79, "Failed to acquire log manager");
      v86 = 0;
LABEL_208:
      wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
      if ( v5 )
        operator delete(v5 - 2);
      if ( v18 )
        operator delete(v18 - 4);
      if ( v16 )
        operator delete(v16 - 4);
      if ( !v3 )
        return 0;
      v34 = v3 - 4;
      goto LABEL_216;
    }
    if ( v78 == 256 )
    {
      v81 = 0;
    }
    else if ( v78 == 512 )
    {
      v81 = 0x2000000;
    }
    else
    {
      v81 = 0x4000000;
      if ( v78 != 1024 )
        v81 = 150994944;
    }
    v92 = v81;
    v91 = L"Sev";
    v94 = 0;
    v96[1] = L"Sev";
    v96[0] = L"DT";
    v96[2] = L"Msg";
    v96[3] = L"Err";
    v96[4] = L"Uid";
    v93 = 1;
    v96[5] = 0;
    v95[0] = v3;
    v95[1] = 0;
    v95[2] = 0;
    if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, __int64 *, _QWORD *, void **))SetupLog)(
            SetupLog,
            &qword_180023F40,
            &v91,
            &qword_180023F50,
            v96,
            &qword_180023F60,
            v95,
            &FileLogHandle) )
    {
      LogAdapter::TraceAtLevelHr<long,>(v83, v82, "Failed to configure logging settings");
      v86 = 0;
      vpfnWdsSetupLogDestroy();
      goto LABEL_208;
    }
    ProcAddress = GetProcAddress(vhWdsDll, "WdsLogRegisterProvider");
    if ( ProcAddress
      && ((unsigned int (__fastcall *)(__int128 *, __int64 (__fastcall *)()))ProcAddress)(
           &xmmword_180023F30,
           CreateCbsLogMonitorProvider) == 1 )
    {
      if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, __int128 *, _QWORD, void **))SetupLog)(
              SetupLog,
              &qword_180023F40,
              &v91,
              &qword_180023F50,
              v96,
              &xmmword_180023F30,
              0,
              &CbsMonitorLogHandle) )
        LogAdapter::TraceInfo<>("Unable to add CbsLogMonitor provider");
      v86 = 0;
      goto LABEL_225;
    }
    LogAdapter::TraceInfo<>("Unable to register CbsLogMonitor provider");
LABEL_224:
    v86 = 0;
    if ( !SetupLog )
    {
LABEL_226:
      wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
      if ( v5 )
        operator delete(v5 - 2);
      if ( v18 )
        operator delete(v18 - 4);
      if ( v16 )
        operator delete(v16 - 4);
      if ( !v3 )
        return v6;
      v28 = v3 - 4;
      goto LABEL_46;
    }
LABEL_225:
    vpfnWdsSetupLogDestroy();
    goto LABEL_226;
  }
  if ( (int)CbsRegQueryDWORDValue(v50, v49, v51, v52, v97) < 0 || (v58 = v97[0]) == 0 )
  {
    v62 = -2147467260;
    v97[0] = -2147467260;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"WDS logging is not enabled in the registry, continuing without logging.");
      EndPtr = (wchar_t *)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v73,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&EndPtr);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x342,
      (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)0x80004004LL);
    wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
    goto LABEL_162;
  }
  v6 = CbsRegQueryStringValue(v55, v54, v56, v57, &v89);
  if ( (v6 & 0x80000000) != 0 || (v3 = v89, !*v89) )
  {
    v32 = SczAllocFromSz(&v89, v18);
    if ( v32 < 0 )
    {
      v53 = 765;
      goto LABEL_124;
    }
    v32 = SczEnsureBackslashTerminated(&v89);
    if ( v32 < 0 )
    {
      v53 = 766;
      goto LABEL_124;
    }
    v32 = SczAllocConcatSz(&v89, L"Logs\\CBS");
    if ( v32 < 0 )
    {
      v53 = 767;
      goto LABEL_124;
    }
    v3 = v89;
    v65 = SczAllocFromSz(&v88, v89);
    v62 = v65;
    if ( v65 >= 0 )
    {
      v66 = SczAllocConcatSz(&v89, L"\\CBS.log");
      v32 = v66;
      if ( v66 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x301,
          (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
          (const char *)(unsigned int)v66);
        wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
        if ( v88 )
          operator delete(v88 - 2);
        goto LABEL_125;
      }
      v3 = v89;
      v5 = v88;
      goto LABEL_172;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x300,
      (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v65);
    wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
    if ( v88 )
      operator delete(v88 - 2);
LABEL_162:
    if ( v18 )
      operator delete(v18 - 4);
    if ( v16 )
      operator delete(v16 - 4);
    if ( !v3 )
      return v62;
    goto LABEL_146;
  }
  v59 = DirectoryFromPath(v89);
  v62 = v59;
  if ( v59 < 0 )
  {
    v97[0] = v59;
    if ( LogAdapter::g_Logger )
    {
      EndPtr = v3;
      LogAdapter::Logger::LogPartial<wchar_t const *>(
        v61,
        v60,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get log path from: {}",
        (__int64)&EndPtr);
      lpLibFileName = (LPCWSTR)v97;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v63,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&lpLibFileName);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F0,
      (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)v62);
    wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
    if ( v88 )
      operator delete(v88 - 2);
    if ( v18 )
      operator delete(v18 - 4);
    if ( v16 )
      operator delete(v16 - 4);
LABEL_146:
    operator delete(v3 - 4);
    return v62;
  }
  v5 = v88;
  v64 = -1;
  do
    ++v64;
  while ( *((_WORD *)v88 + v64) );
  if ( v64 && *((_WORD *)v88 + v64 - 1) == 92 )
    *((_WORD *)v88 + v64 - 1) = 0;
LABEL_172:
  Directory = RecursivelyCreateDirectory(v5, 0);
  v70 = Directory;
  if ( Directory >= 0 )
  {
    SetupLog = 0;
    if ( !v58 )
      goto LABEL_224;
    goto LABEL_189;
  }
  v97[0] = Directory;
  if ( LogAdapter::g_Logger )
  {
    EndPtr = v3;
    LogAdapter::Logger::LogPartial<wchar_t const *>(
      v69,
      v68,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure that logging directory exists: {}",
      (__int64)&EndPtr);
    v88 = v97;
    LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      v71,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
      (__int64)&v88);
  }
  v72 = 774;
LABEL_176:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v72,
    (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
    (const char *)v70);
  wil::details::lambda_call__WdsLoad_::_2_::_lambda_1___::_lambda_call__WdsLoad_::_2_::_lambda_1___(&v85);
  if ( v5 )
    operator delete(v5 - 2);
  if ( v18 )
    operator delete(v18 - 4);
  if ( v16 )
    operator delete(v16 - 4);
  if ( v3 )
    operator delete(v3 - 4);
  return v70;
}

```

## disassembly

```asm
0x180011e10  push    rbp
0x180011e12  push    rbx
0x180011e13  push    rsi
0x180011e14  push    rdi
0x180011e15  push    r12
0x180011e17  push    r13
0x180011e19  push    r14
0x180011e1b  push    r15
0x180011e1d  lea     rbp, [rsp-488h]
0x180011e25  sub     rsp, 588h
0x180011e2c  mov     rax, cs:__security_cookie
0x180011e33  xor     rax, rsp
0x180011e36  mov     [rbp+4C0h+var_50], rax
0x180011e3d  xor     r12d, r12d
0x180011e40  mov     rdi, rcx
0x180011e43  mov     esi, r12d
0x180011e46  mov     [rsp+5C0h+var_558], r12
0x180011e4b  mov     [rsp+5C0h+lpLibFileName], r12
0x180011e50  mov     r15d, r12d
0x180011e53  mov     [rsp+5C0h+EndPtr], r12
0x180011e58  mov     r14d, r12d
0x180011e5b  lea     r13d, [r12+1]
0x180011e60  mov     [rbp+4C0h+var_4E0], r12d
0x180011e64  mov     [rsp+5C0h+var_56F], r13b
0x180011e69  mov     eax, r13d
0x180011e6c  mov     [rsp+5C0h+var_560], r12
0x180011e71  lock xadd cs:?vcWdsLoadOperations@@3JA, eax; long vcWdsLoadOperations
0x180011e79  add     eax, r13d
0x180011e7c  cmp     eax, r13d
0x180011e7f  jle     short loc_180011EE9
0x180011e81  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011e88  test    rcx, rcx
0x180011e8b  jz      short loc_180011EC7
0x180011e8d  lea     r15d, [r12+3]
0x180011e92  xor     edx, edx
0x180011e94  mov     r8d, r15d
0x180011e97  lea     r9, aWdsLoggerIsAlr; "Wds logger is already initialized"
0x180011e9e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180011ea3  lea     rax, [rbp+4C0h+var_4E0]
0x180011ea7  mov     [rbp+4C0h+var_4E0], 800704DFh
0x180011eae  lea     r9, [rsp+5C0h+EndPtr]
0x180011eb3  mov     [rsp+5C0h+EndPtr], rax
0x180011eb8  lea     r8, a0; ": {0}"
0x180011ebf  mov     edx, r15d
0x180011ec2  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011ec7  mov     rcx, [rbp+4C8h]; this
0x180011ece  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180011ed5  mov     r9d, 4DFh; char *
0x180011edb  mov     edx, 284h; void *
0x180011ee0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011ee5  mov     ebx, eax
0x180011ee7  jmp     short loc_180011F53
0x180011ee9  test    rdi, rdi
0x180011eec  jnz     loc_180011F82
0x180011ef2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011ef9  mov     ebx, 80070057h
0x180011efe  mov     [rbp+4C0h+var_4E0], ebx
0x180011f01  test    rcx, rcx
0x180011f04  jz      short loc_180011F38
0x180011f06  lea     r15d, [rdi+3]
0x180011f0a  xor     edx, edx
0x180011f0c  mov     r8d, r15d
0x180011f0f  lea     r9, aNoCoreDllPathS; "No core dll path specified"
0x180011f16  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180011f1b  lea     rax, [rbp+4C0h+var_4E0]
0x180011f1f  mov     edx, r15d
0x180011f22  lea     r9, [rsp+5C0h+EndPtr]
0x180011f27  mov     [rsp+5C0h+EndPtr], rax
0x180011f2c  lea     r8, asc_1800233AC; ": {}"
0x180011f33  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011f38  mov     rcx, [rbp+4C8h]; this
0x180011f3f  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180011f46  mov     r9d, ebx; char *
0x180011f49  mov     edx, 287h; void *
0x180011f4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011f53  lea     rcx, [rsp+5C0h+var_570]
0x180011f58  call    wil__details__lambda_call__WdsLoad____2____lambda_1______lambda_call__WdsLoad____2____lambda_1___
0x180011f5d  mov     eax, ebx
0x180011f5f  mov     rcx, [rbp+4C0h+var_50]
0x180011f66  xor     rcx, rsp; StackCookie
0x180011f69  call    __security_check_cookie
0x180011f6e  add     rsp, 588h
0x180011f75  pop     r15
0x180011f77  pop     r14
0x180011f79  pop     r13
0x180011f7b  pop     r12
0x180011f7d  pop     rdi
0x180011f7e  pop     rsi
0x180011f7f  pop     rbx
0x180011f80  pop     rbp
0x180011f81  retn
0x180011f82  lea     rcx, [rsp+5C0h+EndPtr]
0x180011f87  call    PathGetWindowsDirectory
0x180011f8c  mov     ebx, eax
0x180011f8e  test    eax, eax
0x180011f90  jns     loc_18001201A
0x180011f96  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011f9d  mov     [rbp+4C0h+var_4E0], eax
0x180011fa0  test    rcx, rcx
0x180011fa3  jz      short loc_180011FD9
0x180011fa5  mov     r15d, 3
0x180011fab  lea     r9, aFailedToGetWin; "Failed to get windows directory for WDS"...
0x180011fb2  mov     r8d, r15d
0x180011fb5  xor     edx, edx
0x180011fb7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180011fbc  lea     rax, [rbp+4C0h+var_4E0]
0x180011fc0  mov     edx, r15d
0x180011fc3  lea     r9, [rsp+5C0h+var_560]
0x180011fc8  mov     [rsp+5C0h+var_560], rax
0x180011fcd  lea     r8, asc_1800233AC; ": {}"
0x180011fd4  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011fd9  mov     rcx, [rbp+4C8h]; this
0x180011fe0  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180011fe7  mov     r9d, ebx; char *
0x180011fea  mov     edx, 28Ah; void *
0x180011fef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ff4  lea     rcx, [rsp+5C0h+var_570]
0x180011ff9  call    wil__details__lambda_call__WdsLoad____2____lambda_1______lambda_call__WdsLoad____2____lambda_1___
0x180011ffe  mov     rcx, [rsp+5C0h+EndPtr]
0x180012003  test    rcx, rcx
0x180012006  jz      loc_180011F5D
0x18001200c  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180012010  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012015  jmp     loc_180011F5D
0x18001201a  mov     rdx, rdi
0x18001201d  lea     rcx, [rsp+5C0h+lpLibFileName]
0x180012022  call    SczAllocFromSz
0x180012027  mov     ebx, eax
0x180012029  test    eax, eax
0x18001202b  jns     short loc_18001206C
0x18001202d  mov     edx, 28Ch; void *
0x180012032  mov     rcx, [rbp+4C8h]; this
0x180012039  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180012040  mov     r9d, ebx; char *
0x180012043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012048  lea     rcx, [rsp+5C0h+var_570]
0x18001204d  call    wil__details__lambda_call__WdsLoad____2____lambda_1______lambda_call__WdsLoad____2____lambda_1___
0x180012052  mov     rcx, [rsp+5C0h+EndPtr]
0x180012057  test    rcx, rcx
0x18001205a  jz      short loc_180012065
0x18001205c  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180012060  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012065  mov     rcx, [rsp+5C0h+lpLibFileName]
0x18001206a  jmp     short loc_180012003
0x18001206c  lea     rcx, [rsp+5C0h+lpLibFileName]
0x180012071  call    SczEnsureBackslashTerminated
0x180012076  mov     ebx, eax
0x180012078  test    eax, eax
0x18001207a  jns     short loc_180012083
0x18001207c  mov     edx, 28Dh
0x180012081  jmp     short loc_180012032
0x180012083  lea     rdx, ModuleName; "wdscore.dll"
0x18001208a  lea     rcx, [rsp+5C0h+lpLibFileName]
0x18001208f  call    SczAllocConcatSz
0x180012094  mov     ebx, eax
0x180012096  test    eax, eax
0x180012098  jns     short loc_1800120A1
0x18001209a  mov     edx, 28Eh
0x18001209f  jmp     short loc_180012032
0x1800120a1  mov     rbx, [rsp+5C0h+lpLibFileName]
0x1800120a6  mov     rcx, rbx; lpLibFileName
0x1800120a9  call    cs:__imp_LoadLibraryW
0x1800120af  cmp     cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A, r12; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x1800120b6  jnz     loc_180012E66
0x1800120bc  mov     rdi, [rsp+5C0h+EndPtr]
0x1800120c1  mov     cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A, rax; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x1800120c8  test    rax, rax
0x1800120cb  jnz     loc_1800122CA
0x1800120d1  mov     rdx, rdi
0x1800120d4  lea     rcx, [rsp+5C0h+lpLibFileName]
0x1800120d9  call    SczAllocFromSz
0x1800120de  mov     ebx, eax
0x1800120e0  test    eax, eax
0x1800120e2  jns     short loc_18001211B
0x1800120e4  mov     edx, 293h; void *
0x1800120e9  mov     rcx, [rbp+4C8h]; this
0x1800120f0  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x1800120f7  mov     r9d, ebx; char *
0x1800120fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800120ff  lea     rcx, [rsp+5C0h+var_570]
0x180012104  call    wil__details__lambda_call__WdsLoad____2____lambda_1______lambda_call__WdsLoad____2____lambda_1___
0x180012109  test    rdi, rdi
0x18001210c  jz      loc_180012065
0x180012112  lea     rcx, [rdi-8]
0x180012116  jmp     loc_180012060
0x18001211b  lea     rcx, [rsp+5C0h+lpLibFileName]
0x180012120  call    SczEnsureBackslashTerminated
0x180012125  mov     ebx, eax
0x180012127  test    eax, eax
0x180012129  jns     short loc_180012132
0x18001212b  mov     edx, 294h
0x180012130  jmp     short loc_1800120E9
0x180012132  lea     r8, ModuleName; "wdscore.dll"
0x180012139  lea     rdx, aSystem32; "system32\\"
0x180012140  lea     rcx, [rsp+5C0h+lpLibFileName]
0x180012145  call    SczAllocConcat2Sz
0x18001214a  mov     ebx, eax
0x18001214c  test    eax, eax
0x18001214e  jns     short loc_180012157
0x180012150  mov     edx, 295h
0x180012155  jmp     short loc_1800120E9
0x180012157  mov     rbx, [rsp+5C0h+lpLibFileName]
0x18001215c  mov     rcx, rbx; lpLibFileName
0x18001215f  call    cs:__imp_LoadLibraryW
0x180012165  cmp     cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A, r12; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x18001216c  jnz     loc_180012E66
0x180012172  mov     cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A, rax; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x180012179  test    rax, rax
0x18001217c  jnz     loc_1800122CA
0x180012182  call    cs:__imp_GetLastError
0x180012188  mov     esi, eax
0x18001218a  cmp     eax, 7Eh ; '~'
0x18001218d  jnz     short loc_180012201
0x18001218f  mov     [rsp+5C0h+EndPtr], rbx
0x180012194  call    cs:__imp_GetLastError
0x18001219a  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, r12; LogAdapter::Logger * LogAdapter::g_Logger
0x1800121a1  mov     esi, eax
0x1800121a3  jz      short loc_1800121CE
0x1800121a5  lea     r9, [rsp+5C0h+EndPtr]
0x1800121aa  lea     r8, aCouldNotLoadWd; "Could not load WDSCORE DLL from path: {"...
0x1800121b1  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800121b6  lea     rax, [rbp+4C0h+var_4E0]
0x1800121ba  mov     [rbp+4C0h+var_4E0], esi
0x1800121bd  lea     r9, [rsp+5C0h+var_560]
0x1800121c2  mov     [rsp+5C0h+var_560], rax
0x1800121c7  xor     edx, edx
0x1800121c9  call    ??$Log@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)
0x1800121ce  lea     rcx, [rsp+5C0h+var_570]
0x1800121d3  mov     [rsp+5C0h+var_56F], r12b
0x1800121d8  call    wil__details__lambda_call__WdsLoad____2____lambda_1______lambda_call__WdsLoad____2____lambda_1___
0x1800121dd  test    rdi, rdi
0x1800121e0  jz      short loc_1800121EB
0x1800121e2  lea     rcx, [rdi-8]; Block
0x1800121e6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800121eb  test    rbx, rbx
0x1800121ee  jz      short loc_1800121F9
0x1800121f0  lea     rcx, [rbx-8]; Block
0x1800121f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800121f9  mov     eax, r13d
0x1800121fc  jmp     loc_180011F5F
0x180012201  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, r12; LogAdapter::Logger * LogAdapter::g_Logger
0x180012208  jz      short loc_180012252
0x18001220a  lea     r9, [rsp+5C0h+EndPtr]
0x18001220f  mov     [rsp+5C0h+EndPtr], rbx
0x180012214  lea     r8, aFailedToLoadWd; "Failed to load WDSCORE DLL: {}"
0x18001221b  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180012220  test    esi, esi
0x180012222  jg      short loc_180012228
0x180012224  mov     eax, esi
0x180012226  jmp     short loc_180012230
0x180012228  movzx   eax, si
0x18001222b  or      eax, 80070000h
0x180012230  mov     [rbp+4C0h+var_4E0], eax
0x180012233  lea     r9, [rsp+5C0h+var_560]
0x180012238  lea     rax, [rbp+4C0h+var_4E0]
0x18001223c  mov     edx, 3
0x180012241  lea     r8, a0; ": {0}"
0x180012248  mov     [rsp+5C0h+var_560], rax
0x18001224d  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180012252  test    esi, esi
0x180012254  jz      short loc_1800122A0
0x180012256  mov     edx, 2A2h; void *
0x18001225b  mov     rcx, [rbp+4C8h]; this
0x180012262  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180012269  mov     r9d, esi; char *
0x18001226c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012271  lea     rcx, [rsp+5C0h+var_570]
0x180012276  mov     esi, eax
0x180012278  call    wil__details__lambda_call__WdsLoad____2____lambda_1______lambda_call__WdsLoad____2____lambda_1___
0x18001227d  test    rdi, rdi
0x180012280  jz      short loc_18001228B
0x180012282  lea     rcx, [rdi-8]; Block
0x180012286  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001228b  test    rbx, rbx
0x18001228e  jz      short loc_180012299
0x180012290  lea     rcx, [rbx-8]; Block
0x180012294  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012299  mov     eax, esi
0x18001229b  jmp     loc_180011F5F
0x1800122a0  lea     rcx, [rsp+5C0h+var_570]
0x1800122a5  call    wil__details__lambda_call__WdsLoad____2____lambda_1______lambda_call__WdsLoad____2____lambda_1___
0x1800122aa  test    rdi, rdi
0x1800122ad  jz      short loc_1800122B8
0x1800122af  lea     rcx, [rdi-8]; Block
0x1800122b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800122b8  test    rbx, rbx
0x1800122bb  jz      loc_180012D62
0x1800122c1  lea     rcx, [rbx-8]
0x1800122c5  jmp     loc_180012D5D
0x1800122ca  lea     rdx, aWdssetuplogini; "WdsSetupLogInit"
0x1800122d1  mov     rcx, rax; hModule
0x1800122d4  call    cs:__imp_GetProcAddress
0x1800122da  mov     cs:?vpfnWdsSetupLogInit@@3P6APEAVILogManager@@PEAUHINSTANCE__@@KPEB_W@ZEA, rax; ILogManager * (*vpfnWdsSetupLogInit)(HINSTANCE__ *,ulong,wchar_t const *)
0x1800122e1  test    rax, rax
0x1800122e4  jnz     short loc_180012353
0x1800122e6  call    cs:__imp_GetLastError
0x1800122ec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800122f3  mov     esi, eax
0x1800122f5  test    rcx, rcx
0x1800122f8  jz      short loc_180012341
  ... truncated ...
```
