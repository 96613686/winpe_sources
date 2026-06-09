# WdsSetupLogInit

- ea: `0x18001cb20`
- end: `0x18001d90b`
- name: `WdsSetupLogInit`
- size: `3563`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18000d350`

## callees

- `0x180001868`
- `0x180002250`
- `0x180005e18`
- `0x18001a8dc`
- `0x18001aa9c`
- `0x18001ac00`
- `0x18001ac6c`
- `0x18001ca90`
- `0x18001cb20`
- `0x18001dc70`
- `0x180020210`
- `0x1800207f0`
- `0x180022bcc`
- `0x180022bf8`
- `0x180022e40`
- `0x180022e64`
- `0x1800274de`
- `0x180027510`
- `0x1800275d0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001d351`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001d351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d75a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d75a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18001d782`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18001d782`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001d79d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001d79d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001d311`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001d311`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001d2f8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001d2f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18001cd26`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18001cd26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d327`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d327`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d225`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d225`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d262`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d262`
- `api-ms-win-core-errorhandling-l1-1-1!AddVectoredExceptionHandler` at `0x18001d898`
- `api-ms-win-core-errorhandling-l1-1-1!AddVectoredExceptionHandler` at `0x18001d898`

## string_xrefs

- `0x18001d025`: `setuplog.xml`
- `0x18001d05a`: `diagerr.xml`
- `0x18001d08f`: `diagwrn.xml`

## pseudocode

```c
struct ILogManager *__fastcall WdsSetupLogInit(__int64 a1, int a2, const wchar_t *a3)
{
  int v5; // eax
  unsigned __int16 *v6; // rdi
  const wchar_t *v7; // rbx
  const WCHAR *v8; // rcx
  __int64 MutexWrapperW; // r15
  int v11; // r13d
  struct ILogManager *v12; // rsi
  int v13; // edi
  unsigned __int64 v14; // rcx
  unsigned int v15; // edx
  unsigned int v16; // edx
  int v17; // r8d
  int v18; // ebx
  DWORD LastError; // ebx
  int v20; // eax
  DWORD cbData; // [rsp+64h] [rbp-1394h] BYREF
  int v22; // [rsp+68h] [rbp-1390h]
  int v23; // [rsp+6Ch] [rbp-138Ch]
  HKEY hKey; // [rsp+70h] [rbp-1388h] BYREF
  __int64 v25; // [rsp+78h] [rbp-1380h]
  unsigned __int64 v26; // [rsp+80h] [rbp-1378h]
  struct ILogManager *v27; // [rsp+88h] [rbp-1370h]
  _QWORD v28[6]; // [rsp+90h] [rbp-1368h] BYREF
  unsigned __int16 *v29; // [rsp+C0h] [rbp-1338h] BYREF
  unsigned __int16 *v30; // [rsp+C8h] [rbp-1330h] BYREF
  int v31; // [rsp+D0h] [rbp-1328h]
  __int64 v32; // [rsp+D4h] [rbp-1324h]
  int v33; // [rsp+DCh] [rbp-131Ch]
  unsigned __int16 *v34; // [rsp+E0h] [rbp-1318h] BYREF
  int v35; // [rsp+E8h] [rbp-1310h]
  __int64 v36; // [rsp+ECh] [rbp-130Ch]
  int v37; // [rsp+F4h] [rbp-1304h]
  unsigned __int16 *v38; // [rsp+F8h] [rbp-1300h] BYREF
  int v39; // [rsp+100h] [rbp-12F8h]
  __int64 v40; // [rsp+104h] [rbp-12F4h]
  int v41; // [rsp+10Ch] [rbp-12ECh]
  unsigned __int16 *v42; // [rsp+110h] [rbp-12E8h] BYREF
  int v43; // [rsp+118h] [rbp-12E0h]
  __int64 v44; // [rsp+11Ch] [rbp-12DCh]
  int v45; // [rsp+124h] [rbp-12D4h]
  _QWORD v46[3]; // [rsp+128h] [rbp-12D0h] BYREF
  unsigned __int16 *v47; // [rsp+140h] [rbp-12B8h] BYREF
  int v48; // [rsp+148h] [rbp-12B0h]
  __int64 v49; // [rsp+14Ch] [rbp-12ACh]
  int v50; // [rsp+154h] [rbp-12A4h]
  const wchar_t *v51; // [rsp+158h] [rbp-12A0h] BYREF
  __m128i v52; // [rsp+160h] [rbp-1298h]
  _QWORD v53[2]; // [rsp+170h] [rbp-1288h] BYREF
  _QWORD v54[3]; // [rsp+180h] [rbp-1278h] BYREF
  int v55; // [rsp+198h] [rbp-1260h]
  __int64 v56; // [rsp+19Ch] [rbp-125Ch]
  _QWORD v57[7]; // [rsp+1A8h] [rbp-1250h] BYREF
  const wchar_t *v58; // [rsp+1E0h] [rbp-1218h] BYREF
  __m128i si128; // [rsp+1E8h] [rbp-1210h]
  const wchar_t *v60; // [rsp+1F8h] [rbp-1200h] BYREF
  __m128i v61; // [rsp+200h] [rbp-11F8h]
  const wchar_t *v62; // [rsp+210h] [rbp-11E8h] BYREF
  __m128i v63; // [rsp+218h] [rbp-11E0h]
  CHAR Buffer[272]; // [rsp+230h] [rbp-11C8h] BYREF
  WCHAR Data[264]; // [rsp+340h] [rbp-10B8h] BYREF
  unsigned __int16 v66[264]; // [rsp+550h] [rbp-EA8h] BYREF
  unsigned __int16 v67[264]; // [rsp+760h] [rbp-C98h] BYREF
  unsigned __int16 v68[264]; // [rsp+970h] [rbp-A88h] BYREF
  unsigned __int16 v69[264]; // [rsp+B80h] [rbp-878h] BYREF
  unsigned __int16 v70[264]; // [rsp+D90h] [rbp-668h] BYREF
  unsigned __int16 v71[264]; // [rsp+FA0h] [rbp-458h] BYREF
  unsigned __int16 v72[264]; // [rsp+11B0h] [rbp-248h] BYREF
  LPCWSTR lpModuleName; // [rsp+13F8h] [rbp+0h]

  memset_0(Buffer, 0, 0x104u);
  memset_0(v66, 0, 0x208u);
  memset_0(v67, 0, 0x208u);
  memset_0(v68, 0, 0x208u);
  memset_0(v71, 0, 0x208u);
  memset_0(v69, 0, 0x208u);
  memset_0(v70, 0, 0x208u);
  memset_0(v72, 0, 0x208u);
  v29 = v72;
  if ( !(unsigned int)InitDefaultACL(((unsigned int)a2 >> 20) & 1) )
    return 0;
  v5 = IsUserAdminOrLocalService();
  v6 = L"SetupLog";
  v7 = L"Global\\SetupLog";
  if ( !v5 )
    v7 = L"SetupLog";
  v8 = L"Global\\WdsSetupLogInit";
  if ( !v5 )
    v8 = L"WdsSetupLogInit";
  MutexWrapperW = CreateMutexWrapperW(v8);
  v25 = MutexWrapperW;
  if ( MutexWrapperW )
  {
    v6 = (unsigned __int16 *)v7;
  }
  else
  {
    if ( GetLastError() == 5 )
    {
      MutexWrapperW = CreateMutexWrapperW(L"WdsSetupLogInit");
      v25 = MutexWrapperW;
    }
    else
    {
      v6 = (unsigned __int16 *)v7;
    }
    if ( !MutexWrapperW )
      return 0;
  }
  v11 = a2 & 0x10000000;
  if ( (a2 & 0x10000000) == 0 )
    ++g_RefCnt;
  v12 = g_pLogManager;
  if ( g_pLogManager )
  {
    v22 = 1;
    v27 = g_pLogManager;
  }
  else
  {
    v22 = 0;
    WdsLogRegStockProviders();
    v12 = (struct ILogManager *)WdsLogCreate(v6, (struct tagLOG_FIELD_INFO *)qword_180030AA0, 0x11u);
    v27 = v12;
    if ( !v12 )
    {
      if ( !v11 )
        --g_RefCnt;
      ReleaseMutexWrapper(MutexWrapperW);
      CloseHandleWrapper(MutexWrapperW);
      return 0;
    }
  }
  v23 = a2 & 0x10000000;
  v13 = 0;
  if ( (!a3 || StringCchPrintfA(Buffer, 0x104u, "%S", a3) < 0) && !GetWindowsDirectoryA(Buffer, 0xFAu) )
    StringCchCopyA(Buffer, 0x104u, "c:\\");
  v34 = v66;
  v35 = 2 * (a2 & 1);
  v36 = 0;
  v37 = 0;
  v38 = v67;
  v39 = v35;
  v40 = 0;
  v41 = 0;
  v42 = v71;
  v43 = v35;
  v44 = 0;
  v45 = 0;
  v54[2] = v68;
  v55 = v35;
  v56 = 0;
  v46[0] = L"CONOUT$";
  v46[1] = 0;
  v46[2] = 0;
  v47 = v69;
  v48 = v35;
  v49 = 0;
  v50 = 0;
  v30 = v70;
  v31 = v35;
  v32 = 0;
  v33 = 0;
  v28[0] = L"DT";
  v28[1] = L"Sev";
  v28[2] = L"Msg";
  v28[3] = L"Err";
  v28[4] = L"Uid";
  v28[5] = 0;
  v57[0] = L"Sev";
  v57[1] = L"Msg";
  v57[2] = L"Con";
  v57[3] = L"LN";
  v57[4] = L"Fil";
  v57[5] = L"Fun";
  v57[6] = L"Err";
  v53[0] = L"SACSetupAct";
  v53[1] = L"Windows Setup activity log";
  v54[0] = L"SACSetupErr";
  v54[1] = L"Windows Setup error log";
  v58 = L"Sev";
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v51 = L"Sev";
  v52 = _mm_load_si128((const __m128i *)&_xmm);
  v62 = L"Sev";
  v63 = _mm_load_si128((const __m128i *)&_xmm);
  v60 = L"Sev";
  v61 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (int)StringCchPrintfW(v66, 0x104u, L"%S\\%s", Buffer, L"setupact.log") >= 0
    && (int)StringCchPrintfW(v67, 0x104u, L"%S\\%s", Buffer, L"setuperr.log") >= 0
    && (int)StringCchPrintfW(v68, 0x104u, L"%S\\%s", Buffer, L"setuplog.xml") >= 0
    && (int)StringCchPrintfW(v69, 0x104u, L"%S\\%s", Buffer, L"diagerr.xml") >= 0
    && (int)StringCchPrintfW(v70, 0x104u, L"%S\\%s", Buffer, L"diagwrn.xml") >= 0
    && (int)StringCchPrintfW(v71, 0x104u, L"%S\\%s", Buffer, L"debug.log") >= 0
    && (int)StringCchPrintfW(v72, 0x104u, L"%S\\%s", Buffer, L"setuplog.cfg") >= 0 )
  {
    if ( (a2 & 0x2000000) == 0 )
      goto LABEL_52;
    if ( !a3 || (g_dwPrevFlags & 0x2000000) != 0 )
    {
      if ( !g_szMiniDumpPath )
      {
        hKey = 0;
        memset_0(Data, 0, 0x208u);
        cbData = 520;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\CrashControl", 0, 0x20019u, &hKey)
          && !RegQueryValueExW(hKey, L"MinidumpDir", 0, 0, (LPBYTE)Data, &cbData) )
        {
          v14 = (unsigned __int64)cbData >> 1;
          v26 = v14;
          if ( !*(_WORD *)&Buffer[2 * v14 + 270] )
            v26 = --v14;
          if ( v14 < 0x104 )
          {
            if ( 2 * v14 >= 0x208 )
              _report_rangecheckfailure();
            Data[v14] = 0;
          }
          if ( v14 < 0x103 && *(_WORD *)&Buffer[2 * v14 + 270] != 92 )
          {
            Data[v14] = 92;
            v26 = v14 + 1;
          }
          if ( ExpandEnvironmentStringsW(Data, &g_szMiniDumpPath, 0x104u) )
            CreateDirectoryW(&g_szMiniDumpPath, 0);
        }
        if ( hKey )
          RegCloseKey(hKey);
      }
LABEL_52:
      if ( !_bittest((const signed __int32 *)&g_dwPrevFlags, 0x18u) && (a2 & 0x1000000) != 0 )
      {
        g_OldUnhandledExceptionFilter = SetUnhandledExceptionFilter(WdsUnhandledExceptionFilter);
        g_dwPrevFlags |= 0x1000000u;
      }
      if ( !(unsigned int)InitializeTLSVariables() )
        goto LABEL_94;
      v15 = g_dwPrevFlags;
      if ( (g_dwPrevFlags & 0x1000) == 0 && (a2 & 0x1000) != 0 )
      {
        if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, __int64 *, unsigned __int16 **, _QWORD))v12)(
                v12,
                &qword_180030A88,
                &v58,
                &qword_180032D28,
                v28,
                &qword_180032D48,
                &v34,
                0) )
          goto LABEL_93;
        v15 = g_dwPrevFlags | 0x1000;
        g_dwPrevFlags |= 0x1000u;
      }
      if ( (v15 & 0x2000) == 0 && (a2 & 0x2000) != 0 )
      {
        if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, __int64 *, unsigned __int16 **, _QWORD))v12)(
                v12,
                &qword_180030A88,
                &v51,
                &qword_180032D28,
                v28,
                &qword_180032D48,
                &v38,
                0) )
          goto LABEL_93;
        v15 = g_dwPrevFlags | 0x2000;
        g_dwPrevFlags |= 0x2000u;
      }
      if ( (v15 & 0x20000) == 0 && (a2 & 0x20000) != 0 )
      {
        if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, _QWORD, _QWORD, __int64 *, _QWORD *, __int64 *, unsigned __int16 **, _QWORD))v12)(
                v12,
                0,
                0,
                &qword_180032D28,
                v28,
                &qword_180032D48,
                &v42,
                0) )
          goto LABEL_93;
        v15 = g_dwPrevFlags | 0x20000;
        g_dwPrevFlags |= 0x20000u;
      }
      v16 = a2 & 0xC0000 | v15;
      g_dwPrevFlags = v16;
      if ( (v16 & 0x10000) == 0 && (a2 & 0x10000) != 0 )
      {
        if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, __int64 *, _QWORD *, _QWORD))v12)(
                v12,
                &qword_180030A88,
                &v60,
                &qword_180032D28,
                v28,
                &qword_180032D48,
                v46,
                0) )
          goto LABEL_93;
        v16 = g_dwPrevFlags | 0x10000;
        g_dwPrevFlags |= 0x10000u;
      }
      v17 = v16;
      if ( (v16 & 0x8000) == 0 && (a2 & 0x8000) != 0 )
      {
        if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, _QWORD *, __int64 *, _QWORD *, _QWORD, _QWORD, _QWORD))v12)(
                v12,
                &qword_180030A78,
                v57,
                &qword_180030A58,
                v57,
                0,
                0,
                0) )
          goto LABEL_93;
        v16 = g_dwPrevFlags | 0x8000;
        g_dwPrevFlags = v16;
        v17 = v16;
      }
      if ( a2 >= 0 || v17 < 0 )
        goto LABEL_76;
      if ( (**(unsigned int (__fastcall ***)(struct ILogManager *, _QWORD, _QWORD, __int64 *, _QWORD *, __int64 *, _QWORD *, _QWORD))v12)(
             v12,
             0,
             0,
             &qword_180032D28,
             v28,
             &qword_180032D58,
             v53,
             0)
        && (**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, __int64 *, _QWORD *, _QWORD))v12)(
             v12,
             &qword_180030A88,
             &v51,
             &qword_180032D28,
             v28,
             &qword_180032D58,
             v54,
             0) )
      {
        v16 = g_dwPrevFlags | 0x80000000;
        g_dwPrevFlags = v16;
        LOWORD(v17) = v16;
LABEL_76:
        if ( (v17 & 0x4000) != 0 || (a2 & 0x4000) == 0 )
        {
LABEL_80:
          v18 = v22;
          if ( !v22 )
          {
            g_ProcessID = GetCurrentProcessId();
            g_pLogManager = v12;
            GetModuleFileNameA(0, g_ProcessExeA, 0x104u);
            GetModuleFileNameW(0, g_ProcessExeW, 0x104u);
            v16 = g_dwPrevFlags;
          }
          v13 = 1;
          if ( !v18 )
          {
            if ( !(*(unsigned int (__fastcall **)(struct ILogManager *, __int64 *, unsigned __int16 **, _QWORD))(*(_QWORD *)v12 + 16LL))(
                    v12,
                    &qword_180032D38,
                    &v29,
                    0)
              && g_bEnableDiagnosticMode )
            {
              LastError = GetLastError();
              v20 = (unsigned int)ConstructPartialMsgW(0x67000000u, "Unable to load global log filter.");
              WdsSetupLogMessageW(
                v20,
                589824,
                (int)L"D",
                0,
                1448,
                L"onecore\\base\\ntsetup\\panther\\wdslog\\setuplog.cpp",
                (__int64)L"WdsSetupLogInit",
                lpModuleName,
                LastError,
                0,
                0);
              v13 = 1;
            }
            v16 = g_dwPrevFlags;
          }
          if ( (v16 & 0x4000000) == 0 && (a2 & 0x4000000) != 0 )
          {
            AddVectoredExceptionHandler(((unsigned int)a2 >> 27) & 1, WdsVectoredExceptionHandler);
            g_dwPrevFlags |= 0x4000000u;
          }
          if ( (a2 & 2) != 0 )
          {
            (*(void (__fastcall **)(struct ILogManager *))(*(_QWORD *)v12 + 48LL))(v12);
          }
          else if ( (a2 & 4) != 0 )
          {
            (*(void (__fastcall **)(struct ILogManager *))(*(_QWORD *)v12 + 56LL))(v12);
          }
          goto LABEL_94;
        }
        if ( (**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD, __int64 *, unsigned __int16 **, _QWORD))v12)(
               v12,
               &qword_180030A88,
               &v51,
               &qword_180030A68,
               0,
               &qword_180032D48,
               &v47,
               0)
          && (**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD, __int64 *, unsigned __int16 **, _QWORD))v12)(
               v12,
               &qword_180030A88,
               &v62,
               &qword_180030A68,
               0,
               &qword_180032D48,
               &v30,
               0) )
        {
          v16 = g_dwPrevFlags | 0x4000;
          g_dwPrevFlags |= 0x4000u;
          goto LABEL_80;
        }
      }
LABEL_93:
      v13 = 0;
      goto LABEL_94;
    }
    if ( (int)StringCchPrintfW(&g_szMiniDumpPath, 0x104u, L"%s\\", a3) >= 0 )
    {
      g_dwPrevFlags |= 0x2000000u;
      goto LABEL_52;
    }
  }
LABEL_94:
  if ( !v13 )
  {
    g_pLogManager = v12;
    if ( !v11 )
      WdsSetupLogDestroy();
  }
  ReleaseMutexWrapper(MutexWrapperW);
  CloseHandleWrapper(MutexWrapperW);
  return g_pLogManager;
}

```

## disassembly

```asm
0x18001cb20  mov     [rsp+arg_0], rbx
0x18001cb25  mov     [rsp+arg_8], rsi
0x18001cb2a  push    rdi
0x18001cb2b  push    r12
0x18001cb2d  push    r13
0x18001cb2f  push    r14
0x18001cb31  push    r15
0x18001cb33  mov     eax, 13D0h
0x18001cb38  call    _alloca_probe
0x18001cb3d  sub     rsp, rax
0x18001cb40  mov     rax, cs:__security_cookie
0x18001cb47  xor     rax, rsp
0x18001cb4a  mov     [rsp+13F8h+var_38], rax
0x18001cb52  mov     r12, r8
0x18001cb55  mov     r14d, edx
0x18001cb58  xor     edx, edx; Val
0x18001cb5a  mov     r8d, 104h; Size
0x18001cb60  lea     rcx, [rsp+13F8h+Buffer]; void *
0x18001cb68  call    memset_0
0x18001cb6d  mov     ebx, 208h
0x18001cb72  mov     r8d, ebx; Size
0x18001cb75  xor     edx, edx; Val
0x18001cb77  lea     rcx, [rsp+13F8h+var_EA8]; void *
0x18001cb7f  call    memset_0
0x18001cb84  mov     r8d, ebx; Size
0x18001cb87  xor     edx, edx; Val
0x18001cb89  lea     rcx, [rsp+13F8h+var_C98]; void *
0x18001cb91  call    memset_0
0x18001cb96  mov     r8d, ebx; Size
0x18001cb99  xor     edx, edx; Val
0x18001cb9b  lea     rcx, [rsp+13F8h+var_A88]; void *
0x18001cba3  call    memset_0
0x18001cba8  mov     r8d, ebx; Size
0x18001cbab  xor     edx, edx; Val
0x18001cbad  lea     rcx, [rsp+13F8h+var_458]; void *
0x18001cbb5  call    memset_0
0x18001cbba  mov     r8d, ebx; Size
0x18001cbbd  xor     edx, edx; Val
0x18001cbbf  lea     rcx, [rsp+13F8h+var_878]; void *
0x18001cbc7  call    memset_0
0x18001cbcc  mov     r8d, ebx; Size
0x18001cbcf  xor     edx, edx; Val
0x18001cbd1  lea     rcx, [rsp+13F8h+var_668]; void *
0x18001cbd9  call    memset_0
0x18001cbde  mov     r8d, ebx; Size
0x18001cbe1  xor     edx, edx; Val
0x18001cbe3  lea     rcx, [rsp+13F8h+var_248]; void *
0x18001cbeb  call    memset_0
0x18001cbf0  lea     rax, [rsp+13F8h+var_248]
0x18001cbf8  mov     [rsp+13F8h+var_1338], rax
0x18001cc00  mov     ecx, r14d
0x18001cc03  shr     ecx, 14h
0x18001cc06  and     ecx, 1
0x18001cc09  call    InitDefaultACL
0x18001cc0e  test    eax, eax
0x18001cc10  jz      short loc_18001CC7A
0x18001cc12  call    ?IsUserAdminOrLocalService@@YAHXZ; IsUserAdminOrLocalService(void)
0x18001cc17  lea     rdi, aSetuplog; "SetupLog"
0x18001cc1e  lea     rbx, aGlobalSetuplog; "Global\\SetupLog"
0x18001cc25  test    eax, eax
0x18001cc27  cmovz   rbx, rdi
0x18001cc2b  lea     r13, aWdssetuplogini_0; "WdsSetupLogInit"
0x18001cc32  lea     rcx, aGlobalWdssetup; "Global\\WdsSetupLogInit"
0x18001cc39  cmovz   rcx, r13; lpName
0x18001cc3d  call    CreateMutexWrapperW
0x18001cc42  mov     r15, rax
0x18001cc45  mov     [rsp+13F8h+var_1380], rax
0x18001cc4a  test    rax, rax
0x18001cc4d  jnz     short loc_18001CCAA
0x18001cc4f  call    cs:__imp_GetLastError
0x18001cc56  nop     dword ptr [rax+rax+00h]
0x18001cc5b  cmp     eax, 5
0x18001cc5e  jnz     short loc_18001CC72
0x18001cc60  mov     rcx, r13; lpName
0x18001cc63  call    CreateMutexWrapperW
0x18001cc68  mov     r15, rax
0x18001cc6b  mov     [rsp+13F8h+var_1380], rax
0x18001cc70  jmp     short loc_18001CC75
0x18001cc72  mov     rdi, rbx
0x18001cc75  test    r15, r15
0x18001cc78  jnz     short loc_18001CCAD
0x18001cc7a  xor     eax, eax
0x18001cc7c  mov     rcx, [rsp+13F8h+var_38]
0x18001cc84  xor     rcx, rsp; StackCookie
0x18001cc87  call    __security_check_cookie
0x18001cc8c  lea     r11, [rsp+13F8h+var_28]
0x18001cc94  mov     rbx, [r11+30h]
0x18001cc98  mov     rsi, [r11+38h]
0x18001cc9c  mov     rsp, r11
0x18001cc9f  pop     r15
0x18001cca1  pop     r14
0x18001cca3  pop     r13
0x18001cca5  pop     r12
0x18001cca7  pop     rdi
0x18001cca8  retn
0x18001ccaa  mov     rdi, rbx
0x18001ccad  mov     r13d, r14d
0x18001ccb0  and     r13d, 10000000h
0x18001ccb7  jnz     short loc_18001CCBF
0x18001ccb9  inc     cs:?g_RefCnt@@3KA; ulong g_RefCnt
0x18001ccbf  mov     rsi, cs:?g_pLogManager@@3PEAVILogManager@@EA; ILogManager * g_pLogManager
0x18001ccc6  xor     eax, eax
0x18001ccc8  test    rsi, rsi
0x18001cccb  jz      loc_18001D181
0x18001ccd1  mov     [rsp+13F8h+var_1390], 1
0x18001ccd9  mov     [rsp+13F8h+var_1370], rsi
0x18001cce1  mov     [rsp+13F8h+var_138C], r13d
0x18001cce6  mov     ebx, r14d
0x18001cce9  and     ebx, 1
0x18001ccec  add     ebx, ebx
0x18001ccee  mov     edi, eax
0x18001ccf0  mov     [rsp+13F8h+var_1398], eax
0x18001ccf4  test    r12, r12
0x18001ccf7  jz      short loc_18001CD19
0x18001ccf9  mov     r9, r12
0x18001ccfc  lea     r8, aS; "%S"
0x18001cd03  mov     edx, 104h; unsigned __int64
0x18001cd08  lea     rcx, [rsp+13F8h+Buffer]; char *
0x18001cd10  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001cd15  test    eax, eax
0x18001cd17  jns     short loc_18001CD50
0x18001cd19  mov     edx, 0FAh; uSize
0x18001cd1e  lea     rcx, [rsp+13F8h+Buffer]; lpBuffer
0x18001cd26  call    cs:__imp_GetWindowsDirectoryA
0x18001cd2d  nop     dword ptr [rax+rax+00h]
0x18001cd32  test    eax, eax
0x18001cd34  jnz     short loc_18001CD50
0x18001cd36  lea     r8, aC; "c:\\"
0x18001cd3d  mov     edx, 104h; unsigned __int64
0x18001cd42  lea     rcx, [rsp+13F8h+Buffer]; char *
0x18001cd4a  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001cd4f  nop
0x18001cd50  lea     rax, [rsp+13F8h+var_EA8]
0x18001cd58  mov     [rsp+13F8h+var_1318], rax
0x18001cd60  mov     [rsp+13F8h+var_1310], ebx
0x18001cd67  mov     [rsp+13F8h+var_130C], 0
0x18001cd73  xor     eax, eax
0x18001cd75  mov     [rsp+13F8h+var_1304], eax
0x18001cd7c  lea     rax, [rsp+13F8h+var_C98]
0x18001cd84  mov     [rsp+13F8h+var_1300], rax
0x18001cd8c  mov     [rsp+13F8h+var_12F8], ebx
0x18001cd93  mov     [rsp+13F8h+var_12F4], 0
0x18001cd9f  xor     eax, eax
0x18001cda1  mov     [rsp+13F8h+var_12EC], eax
0x18001cda8  lea     rax, [rsp+13F8h+var_458]
0x18001cdb0  mov     [rsp+13F8h+var_12E8], rax
0x18001cdb8  mov     [rsp+13F8h+var_12E0], ebx
0x18001cdbf  mov     [rsp+13F8h+var_12DC], 0
0x18001cdcb  xor     eax, eax
0x18001cdcd  mov     [rsp+13F8h+var_12D4], eax
0x18001cdd4  lea     rax, [rsp+13F8h+var_A88]
0x18001cddc  mov     [rsp+13F8h+var_1268], rax
0x18001cde4  mov     [rsp+13F8h+var_1260], ebx
0x18001cdeb  mov     [rsp+13F8h+var_125C], 0
0x18001cdf7  lea     rax, aConout; "CONOUT$"
0x18001cdfe  mov     [rsp+13F8h+var_12D0], rax
0x18001ce06  mov     [rsp+13F8h+var_12C8], 0
0x18001ce12  mov     [rsp+13F8h+var_12C0], 0
0x18001ce1e  lea     rax, [rsp+13F8h+var_878]
0x18001ce26  mov     [rsp+13F8h+var_12B8], rax
0x18001ce2e  mov     [rsp+13F8h+var_12B0], ebx
0x18001ce35  mov     [rsp+13F8h+var_12AC], 0
0x18001ce41  xor     eax, eax
0x18001ce43  mov     [rsp+13F8h+var_12A4], eax
0x18001ce4a  lea     rax, [rsp+13F8h+var_668]
0x18001ce52  mov     [rsp+13F8h+var_1330], rax
0x18001ce5a  mov     [rsp+13F8h+var_1328], ebx
0x18001ce61  xor     ebx, ebx
0x18001ce63  mov     [rsp+13F8h+var_1324], rbx
0x18001ce6b  xor     eax, eax
0x18001ce6d  mov     [rsp+13F8h+var_131C], eax
0x18001ce74  lea     rax, aDt; "DT"
0x18001ce7b  mov     [rsp+13F8h+var_1368], rax
0x18001ce83  lea     r8, aSev; "Sev"
0x18001ce8a  mov     [rsp+13F8h+var_1360], r8
0x18001ce92  lea     rcx, aMsg; "Msg"
0x18001ce99  mov     [rsp+13F8h+var_1358], rcx
0x18001cea1  lea     rdx, aErr; "Err"
0x18001cea8  mov     [rsp+13F8h+var_1350], rdx
0x18001ceb0  lea     rax, aUid; "Uid"
0x18001ceb7  mov     [rsp+13F8h+var_1348], rax
0x18001cebf  mov     [rsp+13F8h+var_1340], rbx
0x18001cec7  mov     [rsp+13F8h+var_1250], r8
0x18001cecf  mov     [rsp+13F8h+var_1248], rcx
0x18001ced7  lea     rax, aCon; "Con"
0x18001cede  mov     [rsp+13F8h+var_1240], rax
0x18001cee6  lea     rax, aLn; "LN"
0x18001ceed  mov     [rsp+13F8h+var_1238], rax
0x18001cef5  lea     rax, aFil; "Fil"
0x18001cefc  mov     [rsp+13F8h+var_1230], rax
0x18001cf04  lea     rax, aFun; "Fun"
0x18001cf0b  mov     [rsp+13F8h+var_1228], rax
0x18001cf13  mov     [rsp+13F8h+var_1220], rdx
0x18001cf1b  lea     rax, aSacsetupact; "SACSetupAct"
0x18001cf22  mov     [rsp+13F8h+var_1288], rax
0x18001cf2a  lea     rax, aWindowsSetupAc; "Windows Setup activity log"
0x18001cf31  mov     [rsp+13F8h+var_1280], rax
0x18001cf39  lea     rax, aSacsetuperr; "SACSetupErr"
0x18001cf40  mov     [rsp+13F8h+var_1278], rax
0x18001cf48  lea     rax, aWindowsSetupEr; "Windows Setup error log"
0x18001cf4f  mov     [rsp+13F8h+var_1270], rax
0x18001cf57  mov     [rsp+13F8h+var_1218], r8
0x18001cf5f  movdqa  xmm0, cs:__xmm@00000000000000000000000104000000
0x18001cf67  movdqu  [rsp+13F8h+var_1210], xmm0
0x18001cf70  mov     [rsp+13F8h+var_12A0], r8
0x18001cf78  movdqa  xmm1, cs:__xmm@00000000000000000000000102000000
0x18001cf80  movdqu  [rsp+13F8h+var_1298], xmm1
0x18001cf89  mov     [rsp+13F8h+var_11E8], r8
0x18001cf91  movdqa  xmm0, cs:__xmm@00000000000000010000000103000000
0x18001cf99  movdqu  [rsp+13F8h+var_11E0], xmm0
0x18001cfa2  mov     [rsp+13F8h+var_1200], r8
0x18001cfaa  movdqa  xmm1, cs:__xmm@00000000000000000000000004000000
0x18001cfb2  movdqu  [rsp+13F8h+var_11F8], xmm1
0x18001cfbb  lea     rax, aSetupactLog; "setupact.log"
0x18001cfc2  mov     [rsp+13F8h+phkResult], rax
0x18001cfc7  lea     r9, [rsp+13F8h+Buffer]
0x18001cfcf  lea     r8, aSS_1; "%S\\%s"
0x18001cfd6  mov     edx, 104h; unsigned __int64
0x18001cfdb  lea     rcx, [rsp+13F8h+var_EA8]; unsigned __int16 *
0x18001cfe3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cfe8  test    eax, eax
0x18001cfea  js      loc_18001D8DA
0x18001cff0  lea     rax, aSetuperrLog; "setuperr.log"
0x18001cff7  mov     [rsp+13F8h+phkResult], rax
0x18001cffc  lea     r9, [rsp+13F8h+Buffer]
0x18001d004  lea     r8, aSS_1; "%S\\%s"
0x18001d00b  mov     edx, 104h; unsigned __int64
0x18001d010  lea     rcx, [rsp+13F8h+var_C98]; unsigned __int16 *
0x18001d018  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d01d  test    eax, eax
0x18001d01f  js      loc_18001D8DA
0x18001d025  lea     rax, aSetuplogXml; "setuplog.xml"
0x18001d02c  mov     [rsp+13F8h+phkResult], rax
0x18001d031  lea     r9, [rsp+13F8h+Buffer]
0x18001d039  lea     r8, aSS_1; "%S\\%s"
0x18001d040  mov     edx, 104h; unsigned __int64
0x18001d045  lea     rcx, [rsp+13F8h+var_A88]; unsigned __int16 *
0x18001d04d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d052  test    eax, eax
0x18001d054  js      loc_18001D8DA
0x18001d05a  lea     rax, aDiagerrXml; "diagerr.xml"
0x18001d061  mov     [rsp+13F8h+phkResult], rax
0x18001d066  lea     r9, [rsp+13F8h+Buffer]
0x18001d06e  lea     r8, aSS_1; "%S\\%s"
0x18001d075  mov     edx, 104h; unsigned __int64
0x18001d07a  lea     rcx, [rsp+13F8h+var_878]; unsigned __int16 *
0x18001d082  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d087  test    eax, eax
0x18001d089  js      loc_18001D8DA
0x18001d08f  lea     rax, aDiagwrnXml; "diagwrn.xml"
0x18001d096  mov     [rsp+13F8h+phkResult], rax
0x18001d09b  lea     r9, [rsp+13F8h+Buffer]
0x18001d0a3  lea     r8, aSS_1; "%S\\%s"
0x18001d0aa  mov     edx, 104h; unsigned __int64
0x18001d0af  lea     rcx, [rsp+13F8h+var_668]; unsigned __int16 *
0x18001d0b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d0bc  test    eax, eax
0x18001d0be  js      loc_18001D8DA
0x18001d0c4  lea     rax, aDebugLog; "debug.log"
0x18001d0cb  mov     [rsp+13F8h+phkResult], rax
0x18001d0d0  lea     r9, [rsp+13F8h+Buffer]
0x18001d0d8  lea     r8, aSS_1; "%S\\%s"
0x18001d0df  mov     edx, 104h; unsigned __int64
0x18001d0e4  lea     rcx, [rsp+13F8h+var_458]; unsigned __int16 *
0x18001d0ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d0f1  test    eax, eax
0x18001d0f3  js      loc_18001D8DA
0x18001d0f9  lea     rax, aSetuplogCfg; "setuplog.cfg"
0x18001d100  mov     [rsp+13F8h+phkResult], rax
0x18001d105  lea     r9, [rsp+13F8h+Buffer]
0x18001d10d  lea     r8, aSS_1; "%S\\%s"
0x18001d114  mov     edx, 104h; unsigned __int64
0x18001d119  lea     rcx, [rsp+13F8h+var_248]; unsigned __int16 *
0x18001d121  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d126  test    eax, eax
0x18001d128  js      loc_18001D8DA
0x18001d12e  mov     eax, 2000000h
0x18001d133  test    eax, r14d
0x18001d136  jz      loc_18001D333
0x18001d13c  test    r12, r12
0x18001d13f  jz      loc_18001D1D5
0x18001d145  test    cs:?g_dwPrevFlags@@3KA, eax; ulong g_dwPrevFlags
0x18001d14b  jnz     loc_18001D1D5
0x18001d151  mov     r9, r12
0x18001d154  lea     r8, aS_1; "%s\\"
0x18001d15b  mov     edx, 104h; unsigned __int64
0x18001d160  lea     rcx, ?g_szMiniDumpPath@@3PAGA; unsigned __int16 *
0x18001d167  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d16c  test    eax, eax
0x18001d16e  js      loc_18001D8DA
0x18001d174  bts     cs:?g_dwPrevFlags@@3KA, 19h; ulong g_dwPrevFlags
0x18001d17c  jmp     loc_18001D333
0x18001d181  mov     [rsp+13F8h+var_1390], eax
0x18001d185  call    WdsLogRegStockProviders
0x18001d18a  mov     r8d, 11h; unsigned int
0x18001d190  lea     rdx, qword_180030AA0; struct tagLOG_FIELD_INFO *
0x18001d197  mov     rcx, rdi; unsigned __int16 *
0x18001d19a  call    WdsLogCreate
0x18001d19f  mov     rsi, rax
0x18001d1a2  mov     [rsp+13F8h+var_1370], rax
  ... truncated ...
```
