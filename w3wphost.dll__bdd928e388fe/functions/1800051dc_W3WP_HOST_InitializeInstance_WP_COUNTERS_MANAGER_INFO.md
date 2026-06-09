# W3WP_HOST::InitializeInstance(WP_COUNTERS_MANAGER_INFO *)

- ea: `0x1800051dc`
- end: `0x180005bff`
- name: `?InitializeInstance@W3WP_HOST@@QEAAJPEAUWP_COUNTERS_MANAGER_INFO@@@Z`
- size: `2595`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, struct WP_COUNTERS_MANAGER_INFO *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003340`
- `0x180004750`

## callees

- `0x180001f68`
- `0x180003550`
- `0x1800051dc`
- `0x180005d44`
- `0x180006b70`
- `0x180007958`
- `0x180008474`
- `0x1800086ec`
- `0x180009294`
- `0x18000c39e`
- `0x18000c3d0`
- `0x18000d010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000534f`
- `msvcrt!swprintf_s` at `0x18000534f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000547d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000547d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a89`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005267`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005473`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005267`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005473`
- `OLEAUT32!__imp_SysAllocString` at `0x180005680`
- `OLEAUT32!__imp_SysAllocString` at `0x180005680`
- `OLEAUT32!__imp_VariantInit` at `0x180005251`
- `OLEAUT32!__imp_VariantInit` at `0x180005251`
- `OLEAUT32!__imp_VariantClear` at `0x180005bb1`
- `OLEAUT32!__imp_VariantClear` at `0x180005bb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000532c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000532c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005a1f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005a7d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005ade`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005b36`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005a1f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005a7d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005ade`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005b36`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000579e`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000579e`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180005301`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180005a45`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180005b04`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180005301`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180005a45`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180005b04`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800059fc`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005a33`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005a61`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005abe`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005af2`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005b1a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800059fc`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005a33`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005a61`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005abe`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005af2`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005b1a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005337`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005a09`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005a6e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005acb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005b27`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005337`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005a09`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005a6e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005acb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005b27`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000538e`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180005aa5`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180005b49`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000538e`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180005aa5`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180005b49`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000539e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800053d7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000539e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800053d7`
- `iisutil!PuDbgPrint` at `0x18000550c`
- `iisutil!PuDbgPrint` at `0x18000577d`
- `iisutil!PuDbgPrint` at `0x180005b8d`
- `iisutil!PuDbgPrint` at `0x18000550c`
- `iisutil!PuDbgPrint` at `0x18000577d`
- `iisutil!PuDbgPrint` at `0x180005b8d`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180005ba6`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180005ba6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180005bd6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180005bd6`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000522f`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000522f`
- `iisutil!PuDbgPrintError` at `0x1800052be`
- `iisutil!PuDbgPrintError` at `0x1800052be`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x1800059f3`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005a2a`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005a58`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005ab5`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005ae9`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005b11`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x1800059f3`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005a2a`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005a58`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005ab5`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005ae9`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005b11`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180005528`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180005528`
- `nativerd!InitializeNativeConfiguration` at `0x1800054c8`
- `nativerd!InitializeNativeConfiguration` at `0x1800054c8`

## string_xrefs

- `0x1800052b7`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180005500`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180005757`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180005b86`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x1800054eb`: `Could not initialize native config reader 0x%x\n`
- `0x18000554b`: `Creating config interface failed: 0x%x\n`
- `0x1800055eb`: `SettingConfigPathMapping for applicationhost.config failed\n`
- `0x180005642`: `SettingConfigPathMapping for root web.config failed\n`
- `0x18000542a`: `Failed to create WAS_W3WP_COUNTERSET instance.\n`
- `0x18000559d`: `EnableIgnoreWebConfigFilesMode( FALSE ) failed: 0x%x\n`
- `0x180005990`: `iiscore.dll`
- `0x1800059ad`: `wbhst_pm.dll`
- `0x180005a0f`: `%windir%\system32\inetsrv\iiscore.dll`
- `0x180005ad4`: `%windir%\system32\inetsrv\wbhst_pm.dll`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::InitializeInstance(W3WP_HOST *this, struct WP_COUNTERS_MANAGER_INFO *a2)
{
  W3WP_HOST *v2; // rdi
  signed int LastError; // eax
  int DefaultNativeConfigurationSystem; // ebx
  __int64 v6; // r8
  const char *v7; // rax
  DWORD CurrentProcessId; // ebx
  wchar_t *Str; // rax
  signed int v10; // eax
  __int64 v11; // rax
  __int64 v12; // r8
  const char *v13; // rax
  _QWORD *v14; // rsi
  __int64 v15; // rax
  _WORD *v16; // r8
  _WORD *v17; // r8
  __int64 v18; // rcx
  _WORD *v19; // rax
  __int64 v20; // rax
  _WORD *v21; // rcx
  char *v22; // rax
  char *v23; // rbx
  signed int v24; // eax
  _QWORD *v25; // rax
  _DWORD *v26; // r8
  __int64 v27; // rax
  int v28; // edx
  int v29; // ecx
  BUFFER *Buffer; // rax
  DWORD v31; // ebx
  WCHAR *v32; // rax
  DWORD v33; // ebx
  BUFFER *v34; // rax
  BUFFER *v35; // rax
  DWORD v36; // ebx
  WCHAR *v37; // rax
  signed int v38; // eax
  STRU *v39; // rdi
  BUFFER *v40; // rax
  DWORD v41; // ebx
  WCHAR *v42; // rax
  DWORD v43; // ebx
  BUFFER *v44; // rax
  BUFFER *v45; // rax
  DWORD v46; // ebx
  WCHAR *v47; // rax
  __int64 *v49; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v51; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v52[48]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 v53[272]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = g_pW3WPHost;
  memset_0(v53, 0, 0x108u);
  BUFFER::BUFFER((BUFFER *)v52, v53, 0x108u);
  memset(&pvarg, 0, sizeof(pvarg));
  v49 = 0;
  VariantInit(&pvarg);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)v2 + 208), 0x3E8u) )
  {
    LastError = GetLastError();
    DefaultNativeConfigurationSystem = LastError;
    if ( LastError > 0 )
      DefaultNativeConfigurationSystem = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_113;
    v6 = 1961;
    goto LABEL_6;
  }
  if ( !*(_DWORD *)(*((_QWORD *)v2 + 39) + 88LL) && *((_DWORD *)a2 + 16) == 1 )
  {
    *((_QWORD *)v2 + 14) = a2;
    *((_DWORD *)v2 + 30) = 1;
    DefaultNativeConfigurationSystem = STRU::Resize((W3WP_HOST *)((char *)v2 + 128), 0x50u);
    if ( DefaultNativeConfigurationSystem < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_113;
      v7 = "Failed to Resize the string.";
      v6 = 1993;
      goto LABEL_7;
    }
    CurrentProcessId = GetCurrentProcessId();
    Str = STRU::QueryStr((W3WP_HOST *)((char *)v2 + 128));
    if ( swprintf_s(Str, 0xBu, L"%d", CurrentProcessId) == -1 )
    {
      DefaultNativeConfigurationSystem = -2147418113;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          2015,
          "W3WP_HOST::InitializeInstance",
          -2147418113,
          "swprintf_s failed unexpectedly.");
      goto LABEL_113;
    }
    STRU::SyncWithBuffer((W3WP_HOST *)((char *)v2 + 128));
    DefaultNativeConfigurationSystem = STRU::Append((W3WP_HOST *)((char *)v2 + 128), L"_");
    if ( DefaultNativeConfigurationSystem < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_113;
      v7 = "Failed to append '_' to instance name.\n";
      v6 = 2033;
      goto LABEL_7;
    }
    DefaultNativeConfigurationSystem = STRU::Append(
                                         (W3WP_HOST *)((char *)v2 + 128),
                                         *(const unsigned __int16 **)(*((_QWORD *)v2 + 39) + 24LL));
    if ( DefaultNativeConfigurationSystem < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_113;
      v7 = "Failed to append app pool name.\n";
      v6 = 2049;
      goto LABEL_7;
    }
    DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v2 + 6) + 16LL))(
                                         (__int64)v2 + 48,
                                         0);
    if ( DefaultNativeConfigurationSystem < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_113;
      v7 = "Failed to create WAS_W3WP_COUNTERSET instance.\n";
      v6 = 2066;
      goto LABEL_7;
    }
    DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*((_QWORD *)v2 + 6) + 32LL))(
                                         (__int64)v2 + 48,
                                         0,
                                         4,
                                         (__int64)v2 + 360);
    if ( DefaultNativeConfigurationSystem < 0 )
      goto LABEL_113;
  }
  *((_DWORD *)v2 + 50) = 1;
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)v2 + 256), 0x3E8u) )
  {
    v10 = GetLastError();
    DefaultNativeConfigurationSystem = v10;
    if ( v10 > 0 )
      DefaultNativeConfigurationSystem = (unsigned __int16)v10 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_113;
    v6 = 2095;
LABEL_6:
    v7 = "Initializing criticial section failed failed\n";
LABEL_7:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      v6,
      "W3WP_HOST::InitializeInstance",
      DefaultNativeConfigurationSystem,
      v7);
    goto LABEL_113;
  }
  v11 = *((_QWORD *)v2 + 39);
  *((_DWORD *)v2 + 62) = 1;
  if ( !*(_DWORD *)(v11 + 88) )
  {
    DefaultNativeConfigurationSystem = InitializeNativeConfiguration();
    if ( DefaultNativeConfigurationSystem < 0 )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_113;
      v12 = 2120;
      v13 = "Could not initialize native config reader 0x%x\n";
      goto LABEL_36;
    }
    v14 = (_QWORD *)((char *)v2 + 192);
    *((_DWORD *)v2 + 46) = 1;
    DefaultNativeConfigurationSystem = GetDefaultNativeConfigurationSystem((struct INativeConfigurationSystem **)v2 + 24);
    if ( DefaultNativeConfigurationSystem < 0 )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_113;
      v12 = 2135;
      v13 = "Creating config interface failed: 0x%x\n";
      goto LABEL_36;
    }
    v15 = *((_QWORD *)v2 + 39);
    if ( !*(_DWORD *)(v15 + 88) )
    {
      if ( !*(_DWORD *)(v15 + 96) )
      {
        DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v14 + 192LL))(
                                             *v14,
                                             1);
        if ( DefaultNativeConfigurationSystem < 0 )
        {
          if ( (g_dwDebugFlags & 3) == 0 )
            goto LABEL_113;
          v12 = 2163;
          v13 = "EnableIgnoreWebConfigFilesMode( FALSE ) failed: 0x%x\n";
          goto LABEL_36;
        }
      }
      v16 = *(_WORD **)(*((_QWORD *)v2 + 39) + 64LL);
      if ( v16 )
      {
        if ( *v16 )
        {
          DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _WORD *, __int64))(*(_QWORD *)*v14 + 64LL))(
                                               *v14,
                                               L"MACHINE/WEBROOT/APPHOST",
                                               v16,
                                               3);
          if ( DefaultNativeConfigurationSystem < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_113;
            v7 = "SettingConfigPathMapping for applicationhost.config failed\n";
            v6 = 2186;
            goto LABEL_7;
          }
        }
      }
      v17 = *(_WORD **)(*((_QWORD *)v2 + 39) + 72LL);
      if ( v17 )
      {
        if ( *v17 )
        {
          DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _WORD *, __int64))(*(_QWORD *)*v14 + 64LL))(
                                               *v14,
                                               L"MACHINE/WEBROOT",
                                               v17,
                                               2);
          if ( DefaultNativeConfigurationSystem < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_113;
            v7 = "SettingConfigPathMapping for root web.config failed\n";
            v6 = 2209;
            goto LABEL_7;
          }
        }
      }
    }
  }
  v18 = *((_QWORD *)v2 + 39);
  v19 = *(_WORD **)(v18 + 40);
  if ( v19 && *v19 )
  {
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(*(const OLECHAR **)(v18 + 40));
    if ( !pvarg.llVal )
    {
      DefaultNativeConfigurationSystem = -2147024882;
      goto LABEL_113;
    }
    DefaultNativeConfigurationSystem = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 **))v2 + 24))(
                                         *((_QWORD *)v2 + 24),
                                         &IID_IAppHostAdminManager,
                                         &v49);
    if ( DefaultNativeConfigurationSystem < 0 )
      goto LABEL_113;
    v20 = *v49;
    v51 = pvarg;
    DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v20 + 40))(
                                         v49,
                                         L"defaultManagedRuntimeVersion",
                                         &v51);
    if ( DefaultNativeConfigurationSystem < 0 )
      goto LABEL_113;
  }
  DefaultNativeConfigurationSystem = W3WP_HOST::SetupConfigSystemMetadata(v2);
  if ( DefaultNativeConfigurationSystem < 0 )
    goto LABEL_113;
  v21 = *(_WORD **)(*((_QWORD *)v2 + 39) + 40LL);
  if ( v21 )
  {
    if ( *v21 )
    {
      DefaultNativeConfigurationSystem = W3WP_HOST::PreloadClr(v2);
      if ( DefaultNativeConfigurationSystem < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
            2259,
            "W3WP_HOST::InitializeInstance",
            "Failed while trying to preload CLR version %S.  hr = %x\n");
        goto LABEL_113;
      }
    }
  }
  v22 = (char *)operator new(0xC8u);
  v23 = v22;
  if ( v22 )
  {
    BUFFER::BUFFER((BUFFER *)(v22 + 80));
    *((_QWORD *)v23 + 24) = v2;
    *((_QWORD *)v23 + 5) = 0;
    *((_DWORD *)v23 + 12) = 0;
    *((_QWORD *)v23 + 7) = 0;
    *((_QWORD *)v23 + 8) = 0;
    *((_DWORD *)v23 + 18) = 0;
    *((_DWORD *)v23 + 32) = 1572864;
    *((_QWORD *)v23 + 17) = 0;
    *((_DWORD *)v23 + 36) = 0;
    *((_QWORD *)v23 + 19) = 0;
    *((_QWORD *)v23 + 20) = 0;
    *((_QWORD *)v23 + 21) = 0;
    *((_QWORD *)v23 + 22) = 0;
    *((_DWORD *)v23 + 46) = 0;
  }
  else
  {
    v23 = 0;
  }
  *((_QWORD *)v2 + 13) = v23;
  if ( !v23 )
  {
    v24 = GetLastError();
    DefaultNativeConfigurationSystem = v24;
    if ( v24 > 0 )
      DefaultNativeConfigurationSystem = (unsigned __int16)v24 | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_113;
    v13 = "Failed to initialize WP_RECYCLER.  hr = %x\n";
    v12 = 2276;
    goto LABEL_36;
  }
  DefaultNativeConfigurationSystem = WP_RECYCLER::InitializeInstance((WP_RECYCLER *)v23);
  if ( DefaultNativeConfigurationSystem < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_113;
    v12 = 2287;
    v13 = "Failed to initialize WP_RECYCLER.  hr = %x\n";
    goto LABEL_36;
  }
  WP_RECYCLER::StartRequestBased(*((WP_RECYCLER **)v2 + 13), *(_DWORD *)(*((_QWORD *)v2 + 39) + 8LL));
  v25 = operator new(0x58u);
  if ( v25 )
  {
    v25[1] = 0;
    *v25 = &WP_IPM::`vftable';
    v25[2] = 0;
    v25[3] = 0;
    *(_QWORD *)((char *)v25 + 36) = 0;
    *(_QWORD *)((char *)v25 + 44) = 0;
    *(_QWORD *)((char *)v25 + 52) = 0;
    *((_DWORD *)v25 + 15) = 0;
    *((_DWORD *)v25 + 16) = 0;
    *((_DWORD *)v25 + 17) = 0;
    *((_DWORD *)v25 + 18) = 0;
  }
  else
  {
    v25 = 0;
  }
  *((_QWORD *)v2 + 11) = v25;
  if ( !v25 )
  {
    DefaultNativeConfigurationSystem = -2147024888;
    goto LABEL_110;
  }
  DefaultNativeConfigurationSystem = WP_IPM::Initialize((WP_IPM *)v25, **((unsigned __int16 ***)v2 + 39));
  if ( DefaultNativeConfigurationSystem < 0 )
  {
LABEL_110:
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        2316,
        "W3WP_HOST::InitializeInstance",
        "Failed to initialize IPM.  hr = %x\n");
    EVENT_LOG::LogEvent((W3WP_HOST *)((char *)v2 + 80), 0xC00008E9, 0, 0, DefaultNativeConfigurationSystem);
    goto LABEL_113;
  }
  if ( !*(_DWORD *)(*((_QWORD *)v2 + 39) + 12LL) )
    goto LABEL_89;
  v26 = operator new(0x20u);
  if ( v26 )
  {
    v27 = *((_QWORD *)v2 + 39);
    v28 = *(_DWORD *)(v27 + 16);
    v29 = *(_DWORD *)(v27 + 12);
    *(_QWORD *)v26 = 0;
    v26[2] = 0;
    v26[3] = v29;
    *((_QWORD *)v26 + 2) = 0;
    v26[6] = 0;
    v26[7] = v28;
  }
  else
  {
    v26 = 0;
  }
  *((_QWORD *)v2 + 12) = v26;
  if ( !v26 )
  {
    DefaultNativeConfigurationSystem = -2147024888;
    goto LABEL_94;
  }
  DefaultNativeConfigurationSystem = WP_IDLE_TIMER::Initialize(v26);
  if ( DefaultNativeConfigurationSystem < 0 )
  {
LABEL_94:
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_113;
    v13 = "Failed to initialize idle timer.  hr = %x\n";
    v12 = 2352;
LABEL_36:
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      v12,
      "W3WP_HOST::InitializeInstance",
      v13);
    goto LABEL_113;
  }
LABEL_89:
  (*(void (__fastcall **)(char *, _QWORD, __int64, __int64))(*((_QWORD *)g_pW3WPHost + 6) + 32LL))(
    (char *)g_pW3WPHost + 48,
    0,
    3,
    (__int64)v2 + 392);
  if ( !*(_DWORD *)(*((_QWORD *)v2 + 39) + 88LL) )
  {
    Buffer = STRU::QueryBuffer((W3WP_HOST *)((char *)v2 + 400));
    v31 = BUFFER::QuerySize(Buffer) >> 1;
    v32 = STRU::QueryStr((W3WP_HOST *)((char *)v2 + 400));
    v33 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\iiscore.dll", v32, v31);
    v34 = STRU::QueryBuffer((W3WP_HOST *)((char *)v2 + 400));
    if ( v33 > BUFFER::QuerySize(v34) >> 1 )
    {
      DefaultNativeConfigurationSystem = STRU::Resize((W3WP_HOST *)((char *)v2 + 400), 2 * v33);
      if ( DefaultNativeConfigurationSystem < 0 )
        goto LABEL_115;
      v35 = STRU::QueryBuffer((W3WP_HOST *)((char *)v2 + 400));
      v36 = BUFFER::QuerySize(v35) >> 1;
      v37 = STRU::QueryStr((W3WP_HOST *)((char *)v2 + 400));
      v33 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\iiscore.dll", v37, v36);
    }
    if ( v33 )
    {
      STRU::SyncWithBuffer((W3WP_HOST *)((char *)v2 + 400));
      v39 = (W3WP_HOST *)((char *)v2 + 976);
      v40 = STRU::QueryBuffer(v39);
      v41 = BUFFER::QuerySize(v40) >> 1;
      v42 = STRU::QueryStr(v39);
      v43 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\wbhst_pm.dll", v42, v41);
      v44 = STRU::QueryBuffer(v39);
      if ( v43 > BUFFER::QuerySize(v44) >> 1 )
      {
        v38 = STRU::Resize(v39, 2 * v43);
        if ( v38 < 0 )
        {
LABEL_102:
          DefaultNativeConfigurationSystem = v38;
          goto LABEL_115;
        }
        v45 = STRU::QueryBuffer(v39);
        v46 = BUFFER::QuerySize(v45) >> 1;
        v47 = STRU::QueryStr(v39);
        v43 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\iiscore.dll", v47, v46);
      }
      if ( v43 )
      {
        STRU::SyncWithBuffer(v39);
LABEL_108:
        DefaultNativeConfigurationSystem = 0;
        goto LABEL_113;
      }
    }
    v38 = GetLastError();
    if ( v38 > 0 )
      v38 = (unsigned __int16)v38 | 0x80070000;
    goto LABEL_102;
  }
  DefaultNativeConfigurationSystem = BuildPathFromModule(L"iiscore.dll", (W3WP_HOST *)((char *)v2 + 400));
  if ( DefaultNativeConfigurationSystem >= 0 )
  {
    DefaultNativeConfigurationSystem = BuildPathFromModule(L"wbhst_pm.dll", (W3WP_HOST *)((char *)v2 + 976));
    if ( DefaultNativeConfigurationSystem >= 0 )
      goto LABEL_108;
  }
LABEL_113:
  VariantClear(&pvarg);
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64 *))(*v49 + 16))(v49);
    v49 = 0;
  }
LABEL_115:
  BUFFER::~BUFFER((BUFFER *)v52);
  return (unsigned int)DefaultNativeConfigurationSystem;
}

```

## disassembly

```asm
0x1800051dc  push    rbp
0x1800051de  push    rbx
0x1800051df  push    rsi
0x1800051e0  push    rdi
0x1800051e1  push    r12
0x1800051e3  push    r14
0x1800051e5  push    r15
0x1800051e7  lea     rbp, [rsp-0D0h]
0x1800051ef  sub     rsp, 1D0h
0x1800051f6  mov     rax, cs:__security_cookie
0x1800051fd  xor     rax, rsp
0x180005200  mov     [rbp+100h+var_40], rax
0x180005207  mov     rdi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000520e  lea     rcx, [rbp+100h+var_150]; void *
0x180005212  mov     rbx, rdx
0x180005215  mov     esi, 108h
0x18000521a  mov     r8d, esi; Size
0x18000521d  xor     edx, edx; Val
0x18000521f  call    memset_0
0x180005224  mov     r8d, esi
0x180005227  lea     rdx, [rbp+100h+var_150]
0x18000522b  lea     rcx, [rbp+100h+var_180]
0x18000522f  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180005235  xorps   xmm0, xmm0
0x180005238  lea     rcx, [rsp+200h+pvarg]; pvarg
0x18000523d  xor     eax, eax
0x18000523f  xor     r14d, r14d
0x180005242  movups  xmmword ptr [rsp+200h+pvarg], xmm0
0x180005247  mov     qword ptr [rsp+200h+pvarg+10h], rax
0x18000524c  mov     [rsp+200h+var_1C0], r14
0x180005251  call    cs:__imp_VariantInit
0x180005257  mov     r15d, 3E8h
0x18000525d  lea     rcx, [rdi+0D0h]; lpCriticalSection
0x180005264  mov     edx, r15d; dwSpinCount
0x180005267  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000526d  test    eax, eax
0x18000526f  jnz     short loc_1800052C9
0x180005271  call    cs:__imp_GetLastError
0x180005277  mov     ebx, eax
0x180005279  test    eax, eax
0x18000527b  jle     short loc_180005286
0x18000527d  movzx   ebx, ax
0x180005280  or      ebx, 80070000h
0x180005286  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000528d  jz      loc_180005BAC
0x180005293  mov     r8d, 7A9h
0x180005299  lea     rax, aInitializingCr; "Initializing criticial section failed f"...
0x1800052a0  mov     [rsp+200h+var_1D8], rax
0x1800052a5  mov     dword ptr [rsp+200h+var_1E0], ebx
0x1800052a9  mov     rcx, cs:g_pDebug
0x1800052b0  lea     r9, aW3wpHostInitia; "W3WP_HOST::InitializeInstance"
0x1800052b7  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800052be  call    cs:__imp_PuDbgPrintError
0x1800052c4  jmp     loc_180005BAC
0x1800052c9  mov     rax, [rdi+138h]
0x1800052d0  mov     r12d, 1
0x1800052d6  cmp     [rax+58h], r14d
0x1800052da  jnz     loc_180005462
0x1800052e0  cmp     [rbx+40h], r12d
0x1800052e4  jnz     loc_180005462
0x1800052ea  lea     rsi, [rdi+80h]
0x1800052f1  mov     [rdi+70h], rbx
0x1800052f5  mov     rcx, rsi
0x1800052f8  mov     [rdi+78h], r12d
0x1800052fc  lea     edx, [r12+4Fh]
0x180005301  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180005307  mov     ebx, eax
0x180005309  test    eax, eax
0x18000530b  jns     short loc_18000532C
0x18000530d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005314  jz      loc_180005BAC
0x18000531a  lea     rax, aFailedToResize; "Failed to Resize the string."
0x180005321  mov     r8d, 7C9h
0x180005327  jmp     loc_1800052A0
0x18000532c  call    cs:__imp_GetCurrentProcessId
0x180005332  mov     rcx, rsi
0x180005335  mov     ebx, eax
0x180005337  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000533d  mov     r9d, ebx
0x180005340  lea     r8, aD; "%d"
0x180005347  mov     rcx, rax; Buffer
0x18000534a  mov     edx, 0Bh; BufferCount
0x18000534f  call    cs:__imp_swprintf_s
0x180005355  cmp     eax, 0FFFFFFFFh
0x180005358  jnz     short loc_18000538B
0x18000535a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005361  mov     ebx, 8000FFFFh
0x180005366  jz      loc_180005BAC
0x18000536c  lea     rax, aSwprintfSFaile; "swprintf_s failed unexpectedly."
0x180005373  mov     r8d, 7DFh
0x180005379  mov     [rsp+200h+var_1D8], rax
0x18000537e  mov     dword ptr [rsp+200h+var_1E0], 8000FFFFh
0x180005386  jmp     loc_1800052A9
0x18000538b  mov     rcx, rsi
0x18000538e  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180005394  lea     rdx, asc_18000F4C8; "_"
0x18000539b  mov     rcx, rsi
0x18000539e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800053a4  mov     ebx, eax
0x1800053a6  test    eax, eax
0x1800053a8  jns     short loc_1800053C9
0x1800053aa  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800053b1  jz      loc_180005BAC
0x1800053b7  lea     rax, aFailedToAppend_0; "Failed to append '_' to instance name."...
0x1800053be  mov     r8d, 7F1h
0x1800053c4  jmp     loc_1800052A0
0x1800053c9  mov     rdx, [rdi+138h]
0x1800053d0  mov     rcx, rsi
0x1800053d3  mov     rdx, [rdx+18h]
0x1800053d7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800053dd  mov     ebx, eax
0x1800053df  test    eax, eax
0x1800053e1  jns     short loc_180005402
0x1800053e3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800053ea  jz      loc_180005BAC
0x1800053f0  lea     rax, aFailedToAppend; "Failed to append app pool name.\n"
0x1800053f7  mov     r8d, 801h
0x1800053fd  jmp     loc_1800052A0
0x180005402  lea     rsi, [rdi+30h]
0x180005406  xor     edx, edx
0x180005408  mov     rax, [rsi]
0x18000540b  mov     rcx, rsi
0x18000540e  mov     rax, [rax+10h]
0x180005412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005417  mov     ebx, eax
0x180005419  test    eax, eax
0x18000541b  jns     short loc_18000543C
0x18000541d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005424  jz      loc_180005BAC
0x18000542a  lea     rax, aFailedToCreate_1; "Failed to create WAS_W3WP_COUNTERSET in"...
0x180005431  mov     r8d, 812h
0x180005437  jmp     loc_1800052A0
0x18000543c  mov     rax, [rsi]
0x18000543f  lea     r9, [rdi+168h]
0x180005446  xor     edx, edx
0x180005448  mov     rcx, rsi
0x18000544b  mov     rax, [rax+20h]
0x18000544f  lea     r8d, [rdx+4]
0x180005453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005458  mov     ebx, eax
0x18000545a  test    eax, eax
0x18000545c  js      loc_180005BAC
0x180005462  lea     rcx, [rdi+100h]; lpCriticalSection
0x180005469  mov     [rdi+0C8h], r12d
0x180005470  mov     edx, r15d; dwSpinCount
0x180005473  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180005479  test    eax, eax
0x18000547b  jnz     short loc_1800054AA
0x18000547d  call    cs:__imp_GetLastError
0x180005483  mov     ebx, eax
0x180005485  test    eax, eax
0x180005487  jle     short loc_180005492
0x180005489  movzx   ebx, ax
0x18000548c  or      ebx, 80070000h
0x180005492  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005499  jz      loc_180005BAC
0x18000549f  mov     r8d, 82Fh
0x1800054a5  jmp     loc_180005299
0x1800054aa  mov     rax, [rdi+138h]
0x1800054b1  mov     r15d, 3
0x1800054b7  mov     [rdi+0F8h], r12d
0x1800054be  cmp     [rax+58h], r14d
0x1800054c2  jnz     loc_180005654
0x1800054c8  call    cs:__imp_?InitializeNativeConfiguration@@YAJXZ; InitializeNativeConfiguration(void)
0x1800054ce  mov     ebx, eax
0x1800054d0  test    eax, eax
0x1800054d2  jns     short loc_180005517
0x1800054d4  test    byte ptr cs:g_dwDebugFlags, r15b
0x1800054db  jz      loc_180005BAC
0x1800054e1  mov     dword ptr [rsp+200h+var_1D8], eax
0x1800054e5  mov     r8d, 848h
0x1800054eb  lea     rax, aCouldNotInitia; "Could not initialize native config read"...
0x1800054f2  mov     rcx, cs:g_pDebug
0x1800054f9  lea     r9, aW3wpHostInitia; "W3WP_HOST::InitializeInstance"
0x180005500  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005507  mov     [rsp+200h+var_1E0], rax
0x18000550c  call    cs:__imp_PuDbgPrint
0x180005512  jmp     loc_180005BAC
0x180005517  lea     rsi, [rdi+0C0h]
0x18000551e  mov     [rdi+0B8h], r12d
0x180005525  mov     rcx, rsi
0x180005528  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x18000552e  mov     ebx, eax
0x180005530  test    eax, eax
0x180005532  jns     short loc_180005554
0x180005534  test    byte ptr cs:g_dwDebugFlags, r15b
0x18000553b  jz      loc_180005BAC
0x180005541  mov     dword ptr [rsp+200h+var_1D8], eax
0x180005545  mov     r8d, 857h
0x18000554b  lea     rax, aCreatingConfig; "Creating config interface failed: 0x%x"...
0x180005552  jmp     short loc_1800054F2
0x180005554  mov     rax, [rdi+138h]
0x18000555b  cmp     [rax+58h], r14d
0x18000555f  jnz     loc_180005654
0x180005565  cmp     [rax+60h], r14d
0x180005569  jnz     short loc_1800055A9
0x18000556b  mov     rcx, [rsi]
0x18000556e  mov     edx, r12d
0x180005571  mov     rax, [rcx]
0x180005574  mov     rax, [rax+0C0h]
0x18000557b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005580  mov     ebx, eax
0x180005582  test    eax, eax
0x180005584  jns     short loc_1800055A9
0x180005586  test    byte ptr cs:g_dwDebugFlags, r15b
0x18000558d  jz      loc_180005BAC
0x180005593  mov     dword ptr [rsp+200h+var_1D8], eax
0x180005597  mov     r8d, 873h
0x18000559d  lea     rax, aEnableignorewe; "EnableIgnoreWebConfigFilesMode( FALSE )"...
0x1800055a4  jmp     loc_1800054F2
0x1800055a9  mov     rax, [rdi+138h]
0x1800055b0  mov     r8, [rax+40h]
0x1800055b4  test    r8, r8
0x1800055b7  jz      short loc_1800055FD
0x1800055b9  cmp     [r8], r14w
0x1800055bd  jz      short loc_1800055FD
0x1800055bf  mov     rcx, [rsi]
0x1800055c2  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800055c9  mov     r9d, r15d
0x1800055cc  mov     rax, [rcx]
0x1800055cf  mov     rax, [rax+40h]
0x1800055d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055d8  mov     ebx, eax
0x1800055da  test    eax, eax
0x1800055dc  jns     short loc_1800055FD
0x1800055de  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800055e5  jz      loc_180005BAC
0x1800055eb  lea     rax, aSettingconfigp_0; "SettingConfigPathMapping for applicatio"...
0x1800055f2  mov     r8d, 88Ah
0x1800055f8  jmp     loc_1800052A0
0x1800055fd  mov     rax, [rdi+138h]
0x180005604  mov     r8, [rax+48h]
0x180005608  test    r8, r8
0x18000560b  jz      short loc_180005654
0x18000560d  cmp     [r8], r14w
0x180005611  jz      short loc_180005654
0x180005613  mov     rcx, [rsi]
0x180005616  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x18000561d  mov     r9d, 2
0x180005623  mov     rax, [rcx]
0x180005626  mov     rax, [rax+40h]
0x18000562a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000562f  mov     ebx, eax
0x180005631  test    eax, eax
0x180005633  jns     short loc_180005654
0x180005635  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000563c  jz      loc_180005BAC
0x180005642  lea     rax, aSettingconfigp; "SettingConfigPathMapping for root web.c"...
0x180005649  mov     r8d, 8A1h
0x18000564f  jmp     loc_1800052A0
0x180005654  mov     rcx, [rdi+138h]
0x18000565b  mov     rax, [rcx+28h]
0x18000565f  test    rax, rax
0x180005662  jz      loc_1800056FF
0x180005668  cmp     [rax], r14w
0x18000566c  jz      loc_1800056FF
0x180005672  mov     eax, 8
0x180005677  mov     word ptr [rsp+200h+pvarg], ax
0x18000567c  mov     rcx, [rcx+28h]; psz
0x180005680  call    cs:__imp_SysAllocString
0x180005686  mov     qword ptr [rsp+200h+pvarg+8], rax
0x18000568b  test    rax, rax
0x18000568e  jnz     short loc_18000569A
0x180005690  mov     ebx, 8007000Eh
0x180005695  jmp     loc_180005BAC
0x18000569a  mov     rcx, [rdi+0C0h]
0x1800056a1  lea     r8, [rsp+200h+var_1C0]
0x1800056a6  lea     rdx, IID_IAppHostAdminManager
0x1800056ad  mov     rax, [rcx]
0x1800056b0  mov     rax, [rax]
0x1800056b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b8  mov     ebx, eax
0x1800056ba  test    eax, eax
0x1800056bc  js      loc_180005BAC
0x1800056c2  mov     rcx, [rsp+200h+var_1C0]
0x1800056c7  lea     r8, [rsp+200h+var_1A0]
0x1800056cc  movups  xmm0, xmmword ptr [rsp+200h+pvarg]
0x1800056d1  lea     rdx, aDefaultmanaged; "defaultManagedRuntimeVersion"
0x1800056d8  movsd   xmm1, qword ptr [rsp+200h+pvarg+10h]
0x1800056de  mov     rax, [rcx]
0x1800056e1  movaps  [rsp+200h+var_1A0], xmm0
0x1800056e6  movsd   [rsp+200h+var_190], xmm1
0x1800056ec  mov     rax, [rax+28h]
0x1800056f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f5  mov     ebx, eax
0x1800056f7  test    eax, eax
0x1800056f9  js      loc_180005BAC
0x1800056ff  mov     rcx, rdi; this
0x180005702  call    ?SetupConfigSystemMetadata@W3WP_HOST@@AEAAJXZ; W3WP_HOST::SetupConfigSystemMetadata(void)
0x180005707  mov     ebx, eax
0x180005709  test    eax, eax
0x18000570b  js      loc_180005BAC
0x180005711  mov     rax, [rdi+138h]
0x180005718  mov     rcx, [rax+28h]
0x18000571c  test    rcx, rcx
0x18000571f  jz      short loc_180005788
0x180005721  cmp     [rcx], r14w
0x180005725  jz      short loc_180005788
0x180005727  mov     rcx, rdi; this
0x18000572a  call    ?PreloadClr@W3WP_HOST@@QEAAJXZ; W3WP_HOST::PreloadClr(void)
  ... truncated ...
```
