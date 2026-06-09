# W3WP_HOST::InitializeInstance(WP_COUNTERS_MANAGER_INFO *)

- ea: `0x18000561c`
- end: `0x180006170`
- name: `?InitializeInstance@W3WP_HOST@@QEAAJPEAUWP_COUNTERS_MANAGER_INFO@@@Z`
- size: `2900`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, struct WP_COUNTERS_MANAGER_INFO *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003540`
- `0x180004b20`

## callees

- `0x180002090`
- `0x180003784`
- `0x18000561c`
- `0x1800062bc`
- `0x18000722c`
- `0x180008128`
- `0x180008d78`
- `0x180009028`
- `0x180009cec`
- `0x18000d2be`
- `0x18000d2f0`
- `0x18000e010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800057bf`
- `msvcrt!swprintf_s` at `0x1800057bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000590b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000590b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f89`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800056b3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800058fb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800056b3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800058fb`
- `OLEAUT32!__imp_SysAllocString` at `0x180005b26`
- `OLEAUT32!__imp_SysAllocString` at `0x180005b26`
- `OLEAUT32!__imp_VariantInit` at `0x180005697`
- `OLEAUT32!__imp_VariantInit` at `0x180005697`
- `OLEAUT32!__imp_VariantClear` at `0x180006115`
- `OLEAUT32!__imp_VariantClear` at `0x180006115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005790`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005790`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005eef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005f77`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005ffc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006082`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005eef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005f77`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005ffc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006082`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180005c50`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180005c50`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000575f`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180005f27`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180006034`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000575f`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180005f27`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180006034`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005ec0`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005f0f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005f4f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005fd0`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000601c`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000605a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005ec0`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005f0f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005f4f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005fd0`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000601c`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000605a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800057a1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005ed3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005f62`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005fe3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000606d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800057a1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005ed3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005f62`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005fe3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000606d`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180005804`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180005fab`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000609b`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180005804`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180005fab`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000609b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000581a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005859`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000581a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005859`
- `iisutil!PuDbgPrint` at `0x1800059a6`
- `iisutil!PuDbgPrint` at `0x180005c29`
- `iisutil!PuDbgPrint` at `0x1800060e5`
- `iisutil!PuDbgPrint` at `0x1800059a6`
- `iisutil!PuDbgPrint` at `0x180005c29`
- `iisutil!PuDbgPrint` at `0x1800060e5`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006104`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006104`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180006140`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180006140`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000566f`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000566f`
- `iisutil!PuDbgPrintError` at `0x180005716`
- `iisutil!PuDbgPrintError` at `0x180005716`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005eb1`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005f00`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005f40`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005fc1`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000600d`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000604b`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005eb1`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005f00`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005f40`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180005fc1`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000600d`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000604b`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x1800059c8`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x1800059c8`
- `nativerd!InitializeNativeConfiguration` at `0x18000595c`
- `nativerd!InitializeNativeConfiguration` at `0x18000595c`

## string_xrefs

- `0x18000570f`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x18000599a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180005c03`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x1800060de`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180005985`: `Could not initialize native config reader 0x%x\n`
- `0x1800059f1`: `Creating config interface failed: 0x%x\n`
- `0x180005a91`: `SettingConfigPathMapping for applicationhost.config failed\n`
- `0x180005ae8`: `SettingConfigPathMapping for root web.config failed\n`
- `0x1800058b2`: `Failed to create WAS_W3WP_COUNTERSET instance.\n`
- `0x180005a43`: `EnableIgnoreWebConfigFilesMode( FALSE ) failed: 0x%x\n`
- `0x180005e4e`: `iiscore.dll`
- `0x180005e6b`: `wbhst_pm.dll`
- `0x180005edf`: `%windir%\system32\inetsrv\iiscore.dll`
- `0x180005ff2`: `%windir%\system32\inetsrv\wbhst_pm.dll`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::InitializeInstance(W3WP_HOST *this, struct WP_COUNTERS_MANAGER_INFO *a2)
{
  W3WP_HOST *v2; // rdi
  signed int LastError; // eax
  int v5; // ebx
  __int64 v6; // r8
  const char *v7; // rax
  DWORD CurrentProcessId; // ebx
  wchar_t *Str; // rax
  signed int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  _QWORD *v13; // rsi
  int DefaultNativeConfigurationSystem; // eax
  __int64 v15; // rax
  int v16; // eax
  _WORD *v17; // r8
  _WORD *v18; // r8
  __int64 v19; // rcx
  _WORD *v20; // rax
  __int64 v21; // rax
  _WORD *v22; // rcx
  char *v23; // rax
  char *v24; // rbx
  signed int v25; // eax
  int v26; // eax
  _QWORD *v27; // rax
  _DWORD *v28; // r8
  __int64 v29; // rax
  int v30; // edx
  int v31; // ecx
  BUFFER *Buffer; // rax
  DWORD v33; // ebx
  WCHAR *v34; // rax
  DWORD v35; // ebx
  BUFFER *v36; // rax
  BUFFER *v37; // rax
  DWORD v38; // ebx
  WCHAR *v39; // rax
  signed int v40; // eax
  STRU *v41; // rdi
  BUFFER *v42; // rax
  DWORD v43; // ebx
  WCHAR *v44; // rax
  DWORD v45; // ebx
  BUFFER *v46; // rax
  BUFFER *v47; // rax
  DWORD v48; // ebx
  WCHAR *v49; // rax
  __int64 *v51; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v53; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v54[48]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 v55[272]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = g_pW3WPHost;
  memset_0(v55, 0, 0x108u);
  BUFFER::BUFFER((BUFFER *)v54, v55, 0x108u);
  memset(&pvarg, 0, sizeof(pvarg));
  v51 = 0;
  VariantInit(&pvarg);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)v2 + 208), 0x3E8u) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_113;
    v6 = 1961;
    goto LABEL_6;
  }
  if ( !*(_DWORD *)(*((_QWORD *)v2 + 39) + 88LL) && *((_DWORD *)a2 + 16) == 1 )
  {
    *((_QWORD *)v2 + 14) = a2;
    *((_DWORD *)v2 + 30) = 1;
    v5 = STRU::Resize((W3WP_HOST *)((char *)v2 + 128), 0x50u);
    if ( v5 < 0 )
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
      v5 = -2147418113;
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
    v5 = STRU::Append((W3WP_HOST *)((char *)v2 + 128), L"_");
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_113;
      v7 = "Failed to append '_' to instance name.\n";
      v6 = 2033;
      goto LABEL_7;
    }
    v5 = STRU::Append((W3WP_HOST *)((char *)v2 + 128), *(const unsigned __int16 **)(*((_QWORD *)v2 + 39) + 24LL));
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_113;
      v7 = "Failed to append app pool name.\n";
      v6 = 2049;
      goto LABEL_7;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v2 + 6) + 16LL))((__int64)v2 + 48, 0);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_113;
      v7 = "Failed to create WAS_W3WP_COUNTERSET instance.\n";
      v6 = 2066;
      goto LABEL_7;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*((_QWORD *)v2 + 6) + 32LL))(
           (__int64)v2 + 48,
           0,
           4,
           (__int64)v2 + 360);
    if ( v5 < 0 )
      goto LABEL_113;
  }
  *((_DWORD *)v2 + 50) = 1;
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)v2 + 256), 0x3E8u) )
  {
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
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
      v5,
      v7);
    goto LABEL_113;
  }
  v11 = *((_QWORD *)v2 + 39);
  *((_DWORD *)v2 + 62) = 1;
  if ( !*(_DWORD *)(v11 + 88) )
  {
    v12 = InitializeNativeConfiguration();
    v5 = v12;
    if ( v12 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          2120,
          "W3WP_HOST::InitializeInstance",
          "Could not initialize native config reader 0x%x\n",
          v12);
      goto LABEL_113;
    }
    v13 = (_QWORD *)((char *)v2 + 192);
    *((_DWORD *)v2 + 46) = 1;
    DefaultNativeConfigurationSystem = GetDefaultNativeConfigurationSystem((struct INativeConfigurationSystem **)v2 + 24);
    v5 = DefaultNativeConfigurationSystem;
    if ( DefaultNativeConfigurationSystem < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          2135,
          "W3WP_HOST::InitializeInstance",
          "Creating config interface failed: 0x%x\n",
          DefaultNativeConfigurationSystem);
      goto LABEL_113;
    }
    v15 = *((_QWORD *)v2 + 39);
    if ( !*(_DWORD *)(v15 + 88) )
    {
      if ( !*(_DWORD *)(v15 + 96) )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v13 + 192LL))(*v13, 1);
        v5 = v16;
        if ( v16 < 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
              2163,
              "W3WP_HOST::InitializeInstance",
              "EnableIgnoreWebConfigFilesMode( FALSE ) failed: 0x%x\n",
              v16);
          goto LABEL_113;
        }
      }
      v17 = *(_WORD **)(*((_QWORD *)v2 + 39) + 64LL);
      if ( v17 )
      {
        if ( *v17 )
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _WORD *, __int64))(*(_QWORD *)*v13 + 64LL))(
                 *v13,
                 L"MACHINE/WEBROOT/APPHOST",
                 v17,
                 3);
          if ( v5 < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_113;
            v7 = "SettingConfigPathMapping for applicationhost.config failed\n";
            v6 = 2186;
            goto LABEL_7;
          }
        }
      }
      v18 = *(_WORD **)(*((_QWORD *)v2 + 39) + 72LL);
      if ( v18 )
      {
        if ( *v18 )
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _WORD *, __int64))(*(_QWORD *)*v13 + 64LL))(
                 *v13,
                 L"MACHINE/WEBROOT",
                 v18,
                 2);
          if ( v5 < 0 )
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
  v19 = *((_QWORD *)v2 + 39);
  v20 = *(_WORD **)(v19 + 40);
  if ( v20 && *v20 )
  {
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(*(const OLECHAR **)(v19 + 40));
    if ( !pvarg.llVal )
    {
      v5 = -2147024882;
      goto LABEL_113;
    }
    v5 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 **))v2 + 24))(
           *((_QWORD *)v2 + 24),
           &IID_IAppHostAdminManager,
           &v51);
    if ( v5 < 0 )
      goto LABEL_113;
    v21 = *v51;
    v53 = pvarg;
    v5 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v21 + 40))(
           v51,
           L"defaultManagedRuntimeVersion",
           &v53);
    if ( v5 < 0 )
      goto LABEL_113;
  }
  v5 = W3WP_HOST::SetupConfigSystemMetadata(v2);
  if ( v5 < 0 )
    goto LABEL_113;
  v22 = *(_WORD **)(*((_QWORD *)v2 + 39) + 40LL);
  if ( v22 )
  {
    if ( *v22 )
    {
      v5 = W3WP_HOST::PreloadClr(v2);
      if ( v5 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
            2259,
            "W3WP_HOST::InitializeInstance",
            "Failed while trying to preload CLR version %S.  hr = %x\n",
            *(const wchar_t **)(*((_QWORD *)v2 + 39) + 40LL),
            v5);
        goto LABEL_113;
      }
    }
  }
  v23 = (char *)operator new(0xC8u);
  v24 = v23;
  if ( v23 )
  {
    BUFFER::BUFFER((BUFFER *)(v23 + 80));
    *((_QWORD *)v24 + 24) = v2;
    *((_QWORD *)v24 + 5) = 0;
    *((_DWORD *)v24 + 12) = 0;
    *((_QWORD *)v24 + 7) = 0;
    *((_QWORD *)v24 + 8) = 0;
    *((_DWORD *)v24 + 18) = 0;
    *((_DWORD *)v24 + 32) = 1572864;
    *((_QWORD *)v24 + 17) = 0;
    *((_DWORD *)v24 + 36) = 0;
    *((_QWORD *)v24 + 19) = 0;
    *((_QWORD *)v24 + 20) = 0;
    *((_QWORD *)v24 + 21) = 0;
    *((_QWORD *)v24 + 22) = 0;
    *((_DWORD *)v24 + 46) = 0;
  }
  else
  {
    v24 = 0;
  }
  *((_QWORD *)v2 + 13) = v24;
  if ( !v24 )
  {
    v25 = GetLastError();
    v5 = v25;
    if ( v25 > 0 )
      v5 = (unsigned __int16)v25 | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        2276,
        "W3WP_HOST::InitializeInstance",
        "Failed to initialize WP_RECYCLER.  hr = %x\n",
        v5);
    goto LABEL_113;
  }
  v26 = WP_RECYCLER::InitializeInstance((WP_RECYCLER *)v24);
  v5 = v26;
  if ( v26 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        2287,
        "W3WP_HOST::InitializeInstance",
        "Failed to initialize WP_RECYCLER.  hr = %x\n",
        v26);
    goto LABEL_113;
  }
  WP_RECYCLER::StartRequestBased(*((WP_RECYCLER **)v2 + 13), *(_DWORD *)(*((_QWORD *)v2 + 39) + 8LL));
  v27 = operator new(0x58u);
  if ( v27 )
  {
    v27[1] = 0;
    *v27 = &WP_IPM::`vftable';
    v27[2] = 0;
    v27[3] = 0;
    *(_QWORD *)((char *)v27 + 36) = 0;
    *(_QWORD *)((char *)v27 + 44) = 0;
    *(_QWORD *)((char *)v27 + 52) = 0;
    *((_DWORD *)v27 + 15) = 0;
    *((_DWORD *)v27 + 16) = 0;
    *((_DWORD *)v27 + 17) = 0;
    *((_DWORD *)v27 + 18) = 0;
  }
  else
  {
    v27 = 0;
  }
  *((_QWORD *)v2 + 11) = v27;
  if ( !v27 )
  {
    v5 = -2147024888;
    goto LABEL_110;
  }
  v5 = WP_IPM::Initialize((WP_IPM *)v27, **((unsigned __int16 ***)v2 + 39));
  if ( v5 < 0 )
  {
LABEL_110:
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        2316,
        "W3WP_HOST::InitializeInstance",
        "Failed to initialize IPM.  hr = %x\n",
        v5);
    EVENT_LOG::LogEvent((W3WP_HOST *)((char *)v2 + 80), 0xC00008E9, 0, 0, v5);
    goto LABEL_113;
  }
  if ( !*(_DWORD *)(*((_QWORD *)v2 + 39) + 12LL) )
    goto LABEL_89;
  v28 = operator new(0x20u);
  if ( v28 )
  {
    v29 = *((_QWORD *)v2 + 39);
    v30 = *(_DWORD *)(v29 + 16);
    v31 = *(_DWORD *)(v29 + 12);
    *(_QWORD *)v28 = 0;
    v28[2] = 0;
    v28[3] = v31;
    *((_QWORD *)v28 + 2) = 0;
    v28[6] = 0;
    v28[7] = v30;
  }
  else
  {
    v28 = 0;
  }
  *((_QWORD *)v2 + 12) = v28;
  if ( !v28 )
  {
    v5 = -2147024888;
LABEL_94:
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        2352,
        "W3WP_HOST::InitializeInstance",
        "Failed to initialize idle timer.  hr = %x\n",
        v5);
    goto LABEL_113;
  }
  v5 = WP_IDLE_TIMER::Initialize(v28);
  if ( v5 < 0 )
    goto LABEL_94;
LABEL_89:
  (*(void (__fastcall **)(char *, _QWORD, __int64, __int64))(*((_QWORD *)g_pW3WPHost + 6) + 32LL))(
    (char *)g_pW3WPHost + 48,
    0,
    3,
    (__int64)v2 + 392);
  if ( !*(_DWORD *)(*((_QWORD *)v2 + 39) + 88LL) )
  {
    Buffer = STRU::QueryBuffer((W3WP_HOST *)((char *)v2 + 400));
    v33 = BUFFER::QuerySize(Buffer) >> 1;
    v34 = STRU::QueryStr((W3WP_HOST *)((char *)v2 + 400));
    v35 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\iiscore.dll", v34, v33);
    v36 = STRU::QueryBuffer((W3WP_HOST *)((char *)v2 + 400));
    if ( v35 > BUFFER::QuerySize(v36) >> 1 )
    {
      v5 = STRU::Resize((W3WP_HOST *)((char *)v2 + 400), 2 * v35);
      if ( v5 < 0 )
        goto LABEL_115;
      v37 = STRU::QueryBuffer((W3WP_HOST *)((char *)v2 + 400));
      v38 = BUFFER::QuerySize(v37) >> 1;
      v39 = STRU::QueryStr((W3WP_HOST *)((char *)v2 + 400));
      v35 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\iiscore.dll", v39, v38);
    }
    if ( v35 )
    {
      STRU::SyncWithBuffer((W3WP_HOST *)((char *)v2 + 400));
      v41 = (W3WP_HOST *)((char *)v2 + 976);
      v42 = STRU::QueryBuffer(v41);
      v43 = BUFFER::QuerySize(v42) >> 1;
      v44 = STRU::QueryStr(v41);
      v45 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\wbhst_pm.dll", v44, v43);
      v46 = STRU::QueryBuffer(v41);
      if ( v45 > BUFFER::QuerySize(v46) >> 1 )
      {
        v40 = STRU::Resize(v41, 2 * v45);
        if ( v40 < 0 )
        {
LABEL_102:
          v5 = v40;
          goto LABEL_115;
        }
        v47 = STRU::QueryBuffer(v41);
        v48 = BUFFER::QuerySize(v47) >> 1;
        v49 = STRU::QueryStr(v41);
        v45 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\iiscore.dll", v49, v48);
      }
      if ( v45 )
      {
        STRU::SyncWithBuffer(v41);
LABEL_108:
        v5 = 0;
        goto LABEL_113;
      }
    }
    v40 = GetLastError();
    if ( v40 > 0 )
      v40 = (unsigned __int16)v40 | 0x80070000;
    goto LABEL_102;
  }
  v5 = BuildPathFromModule(L"iiscore.dll", (W3WP_HOST *)((char *)v2 + 400));
  if ( v5 >= 0 )
  {
    v5 = BuildPathFromModule(L"wbhst_pm.dll", (W3WP_HOST *)((char *)v2 + 976));
    if ( v5 >= 0 )
      goto LABEL_108;
  }
LABEL_113:
  VariantClear(&pvarg);
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    v51 = 0;
  }
LABEL_115:
  BUFFER::~BUFFER((BUFFER *)v54);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000561c  push    rbp
0x18000561e  push    rbx
0x18000561f  push    rsi
0x180005620  push    rdi
0x180005621  push    r12
0x180005623  push    r14
0x180005625  push    r15
0x180005627  lea     rbp, [rsp-0D0h]
0x18000562f  sub     rsp, 1D0h
0x180005636  mov     rax, cs:__security_cookie
0x18000563d  xor     rax, rsp
0x180005640  mov     [rbp+100h+var_40], rax
0x180005647  mov     rdi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000564e  lea     rcx, [rbp+100h+var_150]; void *
0x180005652  mov     rbx, rdx
0x180005655  mov     esi, 108h
0x18000565a  mov     r8d, esi; Size
0x18000565d  xor     edx, edx; Val
0x18000565f  call    memset_0
0x180005664  mov     r8d, esi
0x180005667  lea     rdx, [rbp+100h+var_150]
0x18000566b  lea     rcx, [rbp+100h+var_180]
0x18000566f  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180005676  nop     dword ptr [rax+rax+00h]
0x18000567b  xorps   xmm0, xmm0
0x18000567e  lea     rcx, [rsp+200h+pvarg]; pvarg
0x180005683  xor     eax, eax
0x180005685  xor     r14d, r14d
0x180005688  movups  xmmword ptr [rsp+200h+pvarg], xmm0
0x18000568d  mov     qword ptr [rsp+200h+pvarg+10h], rax
0x180005692  mov     [rsp+200h+var_1C0], r14
0x180005697  call    cs:__imp_VariantInit
0x18000569e  nop     dword ptr [rax+rax+00h]
0x1800056a3  mov     r15d, 3E8h
0x1800056a9  lea     rcx, [rdi+0D0h]; lpCriticalSection
0x1800056b0  mov     edx, r15d; dwSpinCount
0x1800056b3  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800056ba  nop     dword ptr [rax+rax+00h]
0x1800056bf  test    eax, eax
0x1800056c1  jnz     short loc_180005727
0x1800056c3  call    cs:__imp_GetLastError
0x1800056ca  nop     dword ptr [rax+rax+00h]
0x1800056cf  mov     ebx, eax
0x1800056d1  test    eax, eax
0x1800056d3  jle     short loc_1800056DE
0x1800056d5  movzx   ebx, ax
0x1800056d8  or      ebx, 80070000h
0x1800056de  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800056e5  jz      loc_180006110
0x1800056eb  mov     r8d, 7A9h
0x1800056f1  lea     rax, aInitializingCr; "Initializing criticial section failed f"...
0x1800056f8  mov     [rsp+200h+var_1D8], rax
0x1800056fd  mov     dword ptr [rsp+200h+var_1E0], ebx
0x180005701  mov     rcx, cs:g_pDebug
0x180005708  lea     r9, aW3wpHostInitia; "W3WP_HOST::InitializeInstance"
0x18000570f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005716  call    cs:__imp_PuDbgPrintError
0x18000571d  nop     dword ptr [rax+rax+00h]
0x180005722  jmp     loc_180006110
0x180005727  mov     rax, [rdi+138h]
0x18000572e  mov     r12d, 1
0x180005734  cmp     [rax+58h], r14d
0x180005738  jnz     loc_1800058EA
0x18000573e  cmp     [rbx+40h], r12d
0x180005742  jnz     loc_1800058EA
0x180005748  lea     rsi, [rdi+80h]
0x18000574f  mov     [rdi+70h], rbx
0x180005753  mov     rcx, rsi
0x180005756  mov     [rdi+78h], r12d
0x18000575a  lea     edx, [r12+4Fh]
0x18000575f  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180005766  nop     dword ptr [rax+rax+00h]
0x18000576b  mov     ebx, eax
0x18000576d  test    eax, eax
0x18000576f  jns     short loc_180005790
0x180005771  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005778  jz      loc_180006110
0x18000577e  lea     rax, aFailedToResize; "Failed to Resize the string."
0x180005785  mov     r8d, 7C9h
0x18000578b  jmp     loc_1800056F8
0x180005790  call    cs:__imp_GetCurrentProcessId
0x180005797  nop     dword ptr [rax+rax+00h]
0x18000579c  mov     rcx, rsi
0x18000579f  mov     ebx, eax
0x1800057a1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800057a8  nop     dword ptr [rax+rax+00h]
0x1800057ad  mov     r9d, ebx
0x1800057b0  lea     r8, aD; "%d"
0x1800057b7  mov     rcx, rax; Buffer
0x1800057ba  mov     edx, 0Bh; BufferCount
0x1800057bf  call    cs:__imp_swprintf_s
0x1800057c6  nop     dword ptr [rax+rax+00h]
0x1800057cb  cmp     eax, 0FFFFFFFFh
0x1800057ce  jnz     short loc_180005801
0x1800057d0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800057d7  mov     ebx, 8000FFFFh
0x1800057dc  jz      loc_180006110
0x1800057e2  lea     rax, aSwprintfSFaile; "swprintf_s failed unexpectedly."
0x1800057e9  mov     r8d, 7DFh
0x1800057ef  mov     [rsp+200h+var_1D8], rax
0x1800057f4  mov     dword ptr [rsp+200h+var_1E0], 8000FFFFh
0x1800057fc  jmp     loc_180005701
0x180005801  mov     rcx, rsi
0x180005804  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000580b  nop     dword ptr [rax+rax+00h]
0x180005810  lea     rdx, asc_1800104D8; "_"
0x180005817  mov     rcx, rsi
0x18000581a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005821  nop     dword ptr [rax+rax+00h]
0x180005826  mov     ebx, eax
0x180005828  test    eax, eax
0x18000582a  jns     short loc_18000584B
0x18000582c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005833  jz      loc_180006110
0x180005839  lea     rax, aFailedToAppend_0; "Failed to append '_' to instance name."...
0x180005840  mov     r8d, 7F1h
0x180005846  jmp     loc_1800056F8
0x18000584b  mov     rdx, [rdi+138h]
0x180005852  mov     rcx, rsi
0x180005855  mov     rdx, [rdx+18h]
0x180005859  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005860  nop     dword ptr [rax+rax+00h]
0x180005865  mov     ebx, eax
0x180005867  test    eax, eax
0x180005869  jns     short loc_18000588A
0x18000586b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005872  jz      loc_180006110
0x180005878  lea     rax, aFailedToAppend; "Failed to append app pool name.\n"
0x18000587f  mov     r8d, 801h
0x180005885  jmp     loc_1800056F8
0x18000588a  lea     rsi, [rdi+30h]
0x18000588e  xor     edx, edx
0x180005890  mov     rax, [rsi]
0x180005893  mov     rcx, rsi
0x180005896  mov     rax, [rax+10h]
0x18000589a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000589f  mov     ebx, eax
0x1800058a1  test    eax, eax
0x1800058a3  jns     short loc_1800058C4
0x1800058a5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800058ac  jz      loc_180006110
0x1800058b2  lea     rax, aFailedToCreate_1; "Failed to create WAS_W3WP_COUNTERSET in"...
0x1800058b9  mov     r8d, 812h
0x1800058bf  jmp     loc_1800056F8
0x1800058c4  mov     rax, [rsi]
0x1800058c7  lea     r9, [rdi+168h]
0x1800058ce  xor     edx, edx
0x1800058d0  mov     rcx, rsi
0x1800058d3  mov     rax, [rax+20h]
0x1800058d7  lea     r8d, [rdx+4]
0x1800058db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e0  mov     ebx, eax
0x1800058e2  test    eax, eax
0x1800058e4  js      loc_180006110
0x1800058ea  lea     rcx, [rdi+100h]; lpCriticalSection
0x1800058f1  mov     [rdi+0C8h], r12d
0x1800058f8  mov     edx, r15d; dwSpinCount
0x1800058fb  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180005902  nop     dword ptr [rax+rax+00h]
0x180005907  test    eax, eax
0x180005909  jnz     short loc_18000593E
0x18000590b  call    cs:__imp_GetLastError
0x180005912  nop     dword ptr [rax+rax+00h]
0x180005917  mov     ebx, eax
0x180005919  test    eax, eax
0x18000591b  jle     short loc_180005926
0x18000591d  movzx   ebx, ax
0x180005920  or      ebx, 80070000h
0x180005926  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000592d  jz      loc_180006110
0x180005933  mov     r8d, 82Fh
0x180005939  jmp     loc_1800056F1
0x18000593e  mov     rax, [rdi+138h]
0x180005945  mov     r15d, 3
0x18000594b  mov     [rdi+0F8h], r12d
0x180005952  cmp     [rax+58h], r14d
0x180005956  jnz     loc_180005AFA
0x18000595c  call    cs:__imp_?InitializeNativeConfiguration@@YAJXZ; InitializeNativeConfiguration(void)
0x180005963  nop     dword ptr [rax+rax+00h]
0x180005968  mov     ebx, eax
0x18000596a  test    eax, eax
0x18000596c  jns     short loc_1800059B7
0x18000596e  test    byte ptr cs:g_dwDebugFlags, r15b
0x180005975  jz      loc_180006110
0x18000597b  mov     dword ptr [rsp+200h+var_1D8], eax
0x18000597f  mov     r8d, 848h
0x180005985  lea     rax, aCouldNotInitia; "Could not initialize native config read"...
0x18000598c  mov     rcx, cs:g_pDebug
0x180005993  lea     r9, aW3wpHostInitia; "W3WP_HOST::InitializeInstance"
0x18000599a  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800059a1  mov     [rsp+200h+var_1E0], rax
0x1800059a6  call    cs:__imp_PuDbgPrint
0x1800059ad  nop     dword ptr [rax+rax+00h]
0x1800059b2  jmp     loc_180006110
0x1800059b7  lea     rsi, [rdi+0C0h]
0x1800059be  mov     [rdi+0B8h], r12d
0x1800059c5  mov     rcx, rsi
0x1800059c8  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x1800059cf  nop     dword ptr [rax+rax+00h]
0x1800059d4  mov     ebx, eax
0x1800059d6  test    eax, eax
0x1800059d8  jns     short loc_1800059FA
0x1800059da  test    byte ptr cs:g_dwDebugFlags, r15b
0x1800059e1  jz      loc_180006110
0x1800059e7  mov     dword ptr [rsp+200h+var_1D8], eax
0x1800059eb  mov     r8d, 857h
0x1800059f1  lea     rax, aCreatingConfig; "Creating config interface failed: 0x%x"...
0x1800059f8  jmp     short loc_18000598C
0x1800059fa  mov     rax, [rdi+138h]
0x180005a01  cmp     [rax+58h], r14d
0x180005a05  jnz     loc_180005AFA
0x180005a0b  cmp     [rax+60h], r14d
0x180005a0f  jnz     short loc_180005A4F
0x180005a11  mov     rcx, [rsi]
0x180005a14  mov     edx, r12d
0x180005a17  mov     rax, [rcx]
0x180005a1a  mov     rax, [rax+0C0h]
0x180005a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a26  mov     ebx, eax
0x180005a28  test    eax, eax
0x180005a2a  jns     short loc_180005A4F
0x180005a2c  test    byte ptr cs:g_dwDebugFlags, r15b
0x180005a33  jz      loc_180006110
0x180005a39  mov     dword ptr [rsp+200h+var_1D8], eax
0x180005a3d  mov     r8d, 873h
0x180005a43  lea     rax, aEnableignorewe; "EnableIgnoreWebConfigFilesMode( FALSE )"...
0x180005a4a  jmp     loc_18000598C
0x180005a4f  mov     rax, [rdi+138h]
0x180005a56  mov     r8, [rax+40h]
0x180005a5a  test    r8, r8
0x180005a5d  jz      short loc_180005AA3
0x180005a5f  cmp     [r8], r14w
0x180005a63  jz      short loc_180005AA3
0x180005a65  mov     rcx, [rsi]
0x180005a68  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180005a6f  mov     r9d, r15d
0x180005a72  mov     rax, [rcx]
0x180005a75  mov     rax, [rax+40h]
0x180005a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a7e  mov     ebx, eax
0x180005a80  test    eax, eax
0x180005a82  jns     short loc_180005AA3
0x180005a84  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005a8b  jz      loc_180006110
0x180005a91  lea     rax, aSettingconfigp_0; "SettingConfigPathMapping for applicatio"...
0x180005a98  mov     r8d, 88Ah
0x180005a9e  jmp     loc_1800056F8
0x180005aa3  mov     rax, [rdi+138h]
0x180005aaa  mov     r8, [rax+48h]
0x180005aae  test    r8, r8
0x180005ab1  jz      short loc_180005AFA
0x180005ab3  cmp     [r8], r14w
0x180005ab7  jz      short loc_180005AFA
0x180005ab9  mov     rcx, [rsi]
0x180005abc  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x180005ac3  mov     r9d, 2
0x180005ac9  mov     rax, [rcx]
0x180005acc  mov     rax, [rax+40h]
0x180005ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad5  mov     ebx, eax
0x180005ad7  test    eax, eax
0x180005ad9  jns     short loc_180005AFA
0x180005adb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005ae2  jz      loc_180006110
0x180005ae8  lea     rax, aSettingconfigp; "SettingConfigPathMapping for root web.c"...
0x180005aef  mov     r8d, 8A1h
0x180005af5  jmp     loc_1800056F8
0x180005afa  mov     rcx, [rdi+138h]
0x180005b01  mov     rax, [rcx+28h]
0x180005b05  test    rax, rax
0x180005b08  jz      loc_180005BAB
0x180005b0e  cmp     [rax], r14w
0x180005b12  jz      loc_180005BAB
0x180005b18  mov     eax, 8
0x180005b1d  mov     word ptr [rsp+200h+pvarg], ax
0x180005b22  mov     rcx, [rcx+28h]; psz
0x180005b26  call    cs:__imp_SysAllocString
0x180005b2d  nop     dword ptr [rax+rax+00h]
0x180005b32  mov     qword ptr [rsp+200h+pvarg+8], rax
0x180005b37  test    rax, rax
0x180005b3a  jnz     short loc_180005B46
0x180005b3c  mov     ebx, 8007000Eh
0x180005b41  jmp     loc_180006110
0x180005b46  mov     rcx, [rdi+0C0h]
0x180005b4d  lea     r8, [rsp+200h+var_1C0]
0x180005b52  lea     rdx, IID_IAppHostAdminManager
0x180005b59  mov     rax, [rcx]
0x180005b5c  mov     rax, [rax]
0x180005b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b64  mov     ebx, eax
0x180005b66  test    eax, eax
0x180005b68  js      loc_180006110
0x180005b6e  mov     rcx, [rsp+200h+var_1C0]
0x180005b73  lea     r8, [rsp+200h+var_1A0]
0x180005b78  movups  xmm0, xmmword ptr [rsp+200h+pvarg]
0x180005b7d  lea     rdx, aDefaultmanaged; "defaultManagedRuntimeVersion"
0x180005b84  movsd   xmm1, qword ptr [rsp+200h+pvarg+10h]
0x180005b8a  mov     rax, [rcx]
0x180005b8d  movaps  [rsp+200h+var_1A0], xmm0
0x180005b92  movsd   [rsp+200h+var_190], xmm1
  ... truncated ...
```
