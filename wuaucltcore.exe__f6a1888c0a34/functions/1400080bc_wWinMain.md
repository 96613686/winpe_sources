# wWinMain

- ea: `0x1400080bc`
- end: `0x1400089a7`
- name: `wWinMain`
- size: `2283`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001ae90`

## callees

- `0x1400016fc`
- `0x1400024f0`
- `0x140002ac0`
- `0x140002aec`
- `0x140003e74`
- `0x14000631c`
- `0x1400066b0`
- `0x1400080bc`
- `0x140008afc`
- `0x140008bbc`
- `0x140008c78`
- `0x140009b74`
- `0x14000bb94`
- `0x14000bda4`
- `0x14000c80c`
- `0x14000cae4`
- `0x14000d4cc`
- `0x14000fd28`
- `0x14001074c`
- `0x1400109ec`
- `0x140010c44`
- `0x14001aa60`
- `0x1400206e0`
- `0x140020760`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000878d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000878d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000887f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400088c0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000887f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400088c0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008374`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000890e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008374`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000890e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008651`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008651`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140008104`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140008104`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1400080f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1400080f2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000810f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000810f`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140008145`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140008900`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140008145`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140008900`

## string_xrefs

- `0x140008729`: `C:\__w\1\s\src\Client\UserProcess\core\dscomls.cpp`
- `0x1400087a0`: `C:\__w\1\s\src\Client\UserProcess\core\dscomls.cpp`
- `0x1400087f8`: `C:\__w\1\s\src\Client\UserProcess\core\dscomls.cpp`
- `0x14000884c`: `C:\__w\1\s\src\Client\UserProcess\core\dscomls.cpp`
- `0x140008660`: `C:\__w\1\s\src\Client\UserProcess\core\UpdateHandler.cpp`
- `0x1400086a0`: `C:\__w\1\s\src\Client\UserProcess\core\UpdateHandler.cpp`
- `0x1400081fe`: `wuaucltcore.exe launched with command line %ws`
- `0x1400083d9`: `/SignalSessionReadyHandle`
- `0x1400083ae`: `/ClassId`
- `0x140008349`: `/DeploymentHandlerFullPath`
- `0x1400084ab`: `/RunHandlerComServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  __int64 v4; // rsi
  unsigned int v5; // r12d
  LPWSTR CommandLineW; // rdi
  HMODULE v7; // rbx
  REGHANDLE v8; // rcx
  __int64 RegKeyPath; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  int ModuleHandleW; // edi
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  WUSystemInterfaceHelper *v17; // rcx
  WCHAR *v18; // rax
  unsigned int v19; // r14d
  bool v20; // dl
  WCHAR v21; // cx
  int WUSystemInterface; // eax
  const wchar_t *v23; // r13
  const wchar_t *v24; // r15
  const WCHAR *v25; // rdi
  const WCHAR *v26; // rdi
  unsigned int v27; // edx
  bool v28; // r8
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  unsigned int v34; // r9d
  __int64 v35; // rdx
  FARPROC ProcAddress; // rax
  const char *v37; // r9
  int v38; // eax
  __int64 v39; // r9
  int v40; // eax
  HRESULT Instance; // eax
  int *v42; // r8
  int v43; // eax
  int v44; // eax
  REGHANDLE v45; // rcx
  void (__fastcall ***v46)(_QWORD, __int64); // rcx
  const struct wil::FailureInfo *v48; // rdx
  const struct wil::FailureInfo *v49; // rdx
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  __int64 v52; // [rsp+48h] [rbp-C0h] BYREF
  HMODULE v53; // [rsp+50h] [rbp-B8h] BYREF
  void *lpMem; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *v55; // [rsp+60h] [rbp-A8h]
  wchar_t *v56; // [rsp+68h] [rbp-A0h]
  wchar_t *v57; // [rsp+70h] [rbp-98h]
  struct IUnknown *v58; // [rsp+78h] [rbp-90h] BYREF
  void (__fastcall ***v59)(_QWORD, __int64); // [rsp+80h] [rbp-88h] BYREF
  _DWORD v60[4]; // [rsp+88h] [rbp-80h] BYREF
  PCNZWCH lpString1[20]; // [rsp+98h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+170h] [rbp+68h]

  SetErrorMode(0x8003u);
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  LODWORD(v4) = 0;
  v5 = 0;
  CommandLineW = GetCommandLineW();
  LODWORD(v58) = 0;
  LODWORD(v52) = 0;
  lpMem = 0;
  v59 = 0;
  v7 = 0;
  v53 = 0;
  v8 = RegHandle;
  dword_14002E108 = 0;
  RegHandle = 0;
  EventUnregister(v8);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14002E108);
  if ( !byte_14002F0E0 )
  {
    RegKeyPath = GetRegKeyPath(21);
    byte_14002F0E1 = RegQueryDwordValueWithDefaultAndRangeCheck(v10, RegKeyPath, L"Flags", 0) & 1;
    if ( byte_14002F0E1 )
    {
      v11 = GetRegKeyPath(21);
      dword_14002E140 = RegQueryDwordValueWithDefaultAndRangeCheck(v12, v11, L"OutputDebugLevel", 4);
    }
    byte_14002F0E0 = 1;
  }
  if ( wil::details::g_pfnTelemetryCallback
    && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != WUFallbackTelemetryProvider::FallbackTelemetryCallback )
  {
    memset(lpString1, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)lpString1, v49);
  }
  wil::details::g_pfnTelemetryCallback = (__int64)WUFallbackTelemetryProvider::FallbackTelemetryCallback;
  if ( wil::details::g_pfnLoggingCallback
    && (__int64 (__fastcall *)())wil::details::g_pfnLoggingCallback != lambda_955477c6653d60071ef8f7f5344c886a_::_lambda_invoker_cdecl_ )
  {
    memset(lpString1, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)lpString1, v48);
  }
  wil::details::g_pfnLoggingCallback = (__int64)lambda_955477c6653d60071ef8f7f5344c886a_::_lambda_invoker_cdecl_;
  ppv = 0;
  WUTrace(0, 0, 4096, 4);
  v13 = DuplicateString<wchar_t *,wchar_t *>(CommandLineW, &lpMem);
  ModuleHandleW = v13;
  if ( v13 < 0 )
  {
    v15 = (unsigned int)v13;
    v16 = 88;
LABEL_121:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\WinMain.cpp",
      (const char *)v15,
      ppv);
    goto LABEL_128;
  }
  memset(lpString1, 0, 0x70u);
  v18 = (WCHAR *)lpMem;
  if ( !lpMem )
    goto LABEL_127;
  v19 = 0;
  if ( *(_WORD *)lpMem )
  {
    while ( 1 )
    {
      v20 = 0;
      while ( 1 )
      {
        v21 = *v18;
        if ( !*v18 || v21 == 32 && !v20 )
          break;
        if ( v21 == 34 )
          v20 = !v20;
        ++v18;
      }
      v17 = (WUSystemInterfaceHelper *)*v18;
      if ( (_WORD)v17 )
      {
        *v18++ = 0;
        v17 = (WUSystemInterfaceHelper *)*v18;
      }
      if ( (_WORD)v17 == 32 )
      {
        do
          ++v18;
        while ( *v18 == 32 );
      }
      if ( !*v18 )
        break;
      if ( *v18 == 45 )
        *v18 = 47;
      if ( v19 < 0xE )
        lpString1[v19++] = v18;
    }
  }
  if ( !v19 )
    goto LABEL_127;
  WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface(v17);
  ModuleHandleW = WUSystemInterface;
  if ( WUSystemInterface < 0 )
  {
    v15 = (unsigned int)WUSystemInterface;
    v16 = 99;
    goto LABEL_121;
  }
  v23 = 0;
  v24 = 0;
  v56 = 0;
  v55 = 0;
  v57 = 0;
  while ( 1 )
  {
    v25 = lpString1[(unsigned int)v4];
    if ( !(unsigned int)AsciiStringCompareI(v25, L"/ReportNow") )
    {
      ReportNow();
      goto LABEL_99;
    }
    if ( !(unsigned int)AsciiStringCompareI(v25, L"/IdleShutdownNow") )
    {
      IdleShutdownNow();
      goto LABEL_99;
    }
    if ( (unsigned int)AsciiStringCompareI(v25, L"/DeploymentHandlerFullPath") )
      break;
    v4 = (unsigned int)(v4 + 1);
    if ( (unsigned int)v4 >= v19 )
    {
      ModuleHandleW = -2147024809;
      v16 = 127;
      goto LABEL_120;
    }
    v26 = lpString1[v4];
    if ( v7 )
    {
      FreeLibrary(v7);
      v53 = 0;
    }
    ModuleHandleW = GetModuleHandleW(v26, (__int64)&v59, &v53);
    v7 = v53;
    if ( ModuleHandleW < 0 )
    {
      v16 = 132;
LABEL_120:
      v15 = (unsigned int)ModuleHandleW;
      goto LABEL_121;
    }
LABEL_68:
    LODWORD(v4) = v4 + 1;
    if ( (unsigned int)v4 >= v19 )
      goto LABEL_99;
  }
  if ( !(unsigned int)AsciiStringCompareI(v25, L"/ClassId") )
  {
    v29 = (unsigned int)(v4 + 1);
    LODWORD(v4) = v29;
    if ( (unsigned int)v29 >= v19 )
    {
      ModuleHandleW = -2147024809;
      v16 = 138;
      goto LABEL_120;
    }
    v24 = lpString1[v29];
    goto LABEL_68;
  }
  if ( !(unsigned int)AsciiStringCompareI(v25, L"/SignalSessionReadyHandle") )
  {
    v30 = (unsigned int)(v4 + 1);
    LODWORD(v4) = v30;
    if ( (unsigned int)v30 >= v19 )
    {
      ModuleHandleW = -2147024809;
      v16 = 145;
      goto LABEL_120;
    }
    v56 = (wchar_t *)lpString1[v30];
    goto LABEL_68;
  }
  if ( !(unsigned int)AsciiStringCompareI(v25, L"/SignalSessionExitHandle") )
  {
    v31 = (unsigned int)(v4 + 1);
    LODWORD(v4) = v31;
    if ( (unsigned int)v31 >= v19 )
    {
      ModuleHandleW = -2147024809;
      v16 = 152;
      goto LABEL_120;
    }
    v55 = (wchar_t *)lpString1[v31];
    goto LABEL_68;
  }
  if ( !(unsigned int)AsciiStringCompareI(v25, L"/ParentSyncHandle") )
  {
    v32 = (unsigned int)(v4 + 1);
    LODWORD(v4) = v32;
    if ( (unsigned int)v32 >= v19 )
    {
      ModuleHandleW = -2147024809;
      v16 = 159;
      goto LABEL_120;
    }
    v57 = (wchar_t *)lpString1[v32];
    goto LABEL_68;
  }
  if ( !(unsigned int)AsciiStringCompareI(v25, L"/DeploymentSessionVersion") )
  {
    v33 = (unsigned int)(v4 + 1);
    LODWORD(v4) = v33;
    if ( (unsigned int)v33 >= v19 )
    {
      ModuleHandleW = -2147024809;
      v16 = 166;
      goto LABEL_120;
    }
    v23 = lpString1[v33];
    goto LABEL_68;
  }
  if ( !(unsigned int)AsciiStringCompareI(v25, L"/RunDeploymentSession") )
  {
    ModuleHandleW = RunUpdateDeploymentSession(v23, v7, v24, v57, v56, v55);
    if ( ModuleHandleW < 0 )
    {
      v16 = 178;
      goto LABEL_120;
    }
    goto LABEL_99;
  }
  if ( !(unsigned int)AsciiStringCompareI(v25, L"/RunHandlerComServer") )
  {
    if ( !v7 )
    {
      v35 = 19;
      goto LABEL_92;
    }
    if ( v24 && *v24 )
    {
      ProcAddress = GetProcAddress(v7, (LPCSTR)6);
      if ( !ProcAddress )
      {
        ModuleHandleW = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x1A,
                          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\UpdateHandler.cpp",
                          v37);
        if ( ModuleHandleW >= 0 )
          goto LABEL_99;
LABEL_94:
        v16 = 185;
        goto LABEL_120;
      }
      v38 = ((__int64 (__fastcall *)(const wchar_t *))ProcAddress)(v24);
      ModuleHandleW = v38;
      if ( v38 >= 0 )
        goto LABEL_99;
      v39 = (unsigned int)v38;
      v35 = 28;
    }
    else
    {
      v35 = 20;
LABEL_92:
      ModuleHandleW = -2147024809;
      v39 = 2147942487LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\UpdateHandler.cpp",
      (const char *)v39,
      0);
    goto LABEL_94;
  }
  if ( !(unsigned int)AsciiStringCompareI(v25, L"/ResetAuthorization") )
  {
    if ( v5 >= 2 )
    {
      ModuleHandleW = -2147024809;
      v16 = 191;
      goto LABEL_120;
    }
    if ( (_DWORD)v52 )
    {
      ModuleHandleW = -2147024809;
      v16 = 192;
      goto LABEL_120;
    }
    v60[v5++] = 0;
    LODWORD(v52) = 1;
    goto LABEL_68;
  }
  if ( !(unsigned int)AsciiStringCompareI(v25, L"/ResetEulas") )
  {
    if ( v5 >= 2 )
    {
      ModuleHandleW = -2147024809;
      v16 = 200;
      goto LABEL_120;
    }
    if ( (_DWORD)v58 )
    {
      ModuleHandleW = -2147024809;
      v16 = 201;
      goto LABEL_120;
    }
    v60[v5++] = 1;
    LODWORD(v58) = 1;
    goto LABEL_68;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetImpl'::`2'::impl)
    || (unsigned int)AsciiStringCompareI(v25, L"/RemoteUHProcessHost") )
  {
    goto LABEL_68;
  }
  ModuleHandleW = RemoteUHProcessHost::ParseAndHostRemoteUHProcess(
                    (RemoteUHProcessHost *)lpString1,
                    (wchar_t **)v19,
                    v4,
                    v34);
  if ( ModuleHandleW < 0 )
  {
    v16 = 211;
    goto LABEL_120;
  }
LABEL_99:
  if ( v5 )
  {
    LODWORD(v52) = 0;
    v58 = 0;
    v40 = CCoInit::Initialize((CCoInit *)&v52, v27, v28);
    ModuleHandleW = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\dscomls.cpp",
        (const char *)(unsigned int)v40,
        ppv);
      if ( v58 )
        ((void (__fastcall *)(struct IUnknown *))v58->lpVtbl->Release)(v58);
LABEL_117:
      if ( (_DWORD)v52 )
        CoUninitialize();
      v16 = 219;
      goto LABEL_120;
    }
    if ( v58 )
      ((void (__fastcall *)(struct IUnknown *))v58->lpVtbl->Release)(v58);
    Instance = CoCreateInstance(
                 &GUID_e60687f7_01a1_40aa_86ac_db1cbf673334,
                 0,
                 0x8004u,
                 &GUID_26e0bf69_a997_4acb_b0e6_37b491094b19,
                 (LPVOID *)&v58);
    ModuleHandleW = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\dscomls.cpp",
        (const char *)(unsigned int)Instance,
        ppva);
      if ( v58 )
      {
        ((void (__fastcall *)(struct IUnknown *))v58->lpVtbl->Release)(v58);
        v58 = 0;
      }
      goto LABEL_117;
    }
    RegisterProxyStubCLSIDs(3u);
    v43 = SetProxyBlanketImpersonationLevel(v58, 2, v42);
    ModuleHandleW = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\dscomls.cpp",
        (const char *)(unsigned int)v43,
        ppva);
      if ( v58 )
      {
        ((void (__fastcall *)(struct IUnknown *))v58->lpVtbl->Release)(v58);
        v58 = 0;
      }
      goto LABEL_117;
    }
    v44 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _DWORD *))v58->lpVtbl[1].QueryInterface)(v58, v5, v60);
    ModuleHandleW = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\dscomls.cpp",
        (const char *)(unsigned int)v44,
        ppva);
      if ( v58 )
      {
        ((void (__fastcall *)(struct IUnknown *))v58->lpVtbl->Release)(v58);
        v58 = 0;
      }
      goto LABEL_117;
    }
    if ( v58 )
    {
      ((void (__fastcall *)(struct IUnknown *))v58->lpVtbl->Release)(v58);
      v58 = 0;
    }
    if ( (_DWORD)v52 )
      CoUninitialize();
  }
  WUTrace(0, 0, 4096, 5);
LABEL_127:
  ModuleHandleW = 0;
LABEL_128:
  v45 = RegHandle;
  dword_14002E108 = 0;
  RegHandle = 0;
  EventUnregister(v45);
  if ( v7 )
    FreeLibrary(v7);
  v46 = v59;
  v59 = 0;
  if ( v46 )
    (**v46)(v46, 1);
  if ( lpMem )
    SusFree(lpMem);
  return ModuleHandleW;
}

```

## disassembly

```asm
0x1400080bc  mov     rax, rsp
0x1400080bf  mov     [rax+8], rbx
0x1400080c3  mov     [rax+10h], rsi
0x1400080c7  mov     [rax+18h], rdi
0x1400080cb  push    rbp
0x1400080cc  push    r12
0x1400080ce  push    r13
0x1400080d0  push    r14
0x1400080d2  push    r15
0x1400080d4  lea     rbp, [rax-68h]
0x1400080d8  sub     rsp, 140h
0x1400080df  mov     rax, cs:__security_cookie
0x1400080e6  xor     rax, rsp
0x1400080e9  mov     [rbp+60h+var_30], rax
0x1400080ed  mov     ecx, 8003h; uMode
0x1400080f2  call    cs:__imp_SetErrorMode
0x1400080f8  xor     r9d, r9d; HeapInformationLength
0x1400080fb  xor     r8d, r8d; HeapInformation
0x1400080fe  lea     edx, [r9+1]; HeapInformationClass
0x140008102  xor     ecx, ecx; HeapHandle
0x140008104  call    cs:__imp_HeapSetInformation
0x14000810a  xor     esi, esi
0x14000810c  mov     r12d, esi
0x14000810f  call    cs:__imp_GetCommandLineW
0x140008115  mov     rdi, rax
0x140008118  mov     dword ptr [rsp+160h+var_F0], esi
0x14000811c  mov     dword ptr [rsp+160h+var_120], esi
0x140008120  mov     [rsp+160h+lpMem], rsi
0x140008125  mov     [rsp+160h+var_E8], rsi
0x14000812a  mov     ebx, esi
0x14000812c  mov     [rsp+160h+var_118], rbx
0x140008131  mov     rcx, cs:RegHandle; RegHandle
0x140008138  mov     cs:dword_14002E108, esi
0x14000813e  mov     cs:RegHandle, rsi
0x140008145  call    cs:__imp_EventUnregister
0x14000814b  lea     rcx, dword_14002E108; CallbackContext
0x140008152  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140008157  lea     r15d, [rsi+4]
0x14000815b  cmp     cs:byte_14002F0E0, sil
0x140008162  jnz     short loc_1400081B3
0x140008164  lea     r14d, [rsi+15h]
0x140008168  mov     ecx, r14d
0x14000816b  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x140008170  xor     r9d, r9d
0x140008173  lea     r8, aFlags_0; "Flags"
0x14000817a  mov     rdx, rax
0x14000817d  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140008182  and     al, 1
0x140008184  mov     cs:byte_14002F0E1, al
0x14000818a  jz      short loc_1400081AC
0x14000818c  mov     ecx, r14d
0x14000818f  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x140008194  mov     r9d, r15d
0x140008197  lea     r8, aOutputdebuglev; "OutputDebugLevel"
0x14000819e  mov     rdx, rax
0x1400081a1  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1400081a6  mov     cs:dword_14002E140, eax
0x1400081ac  mov     cs:byte_14002F0E0, 1
0x1400081b3  lea     rcx, ?FallbackTelemetryCallback@WUFallbackTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z; WUFallbackTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x1400081ba  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400081c1  test    rax, rax
0x1400081c4  jz      short loc_1400081CF
0x1400081c6  cmp     rax, rcx
0x1400081c9  jnz     loc_14000898C
0x1400081cf  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x1400081d6  lea     rcx, _lambda_955477c6653d60071ef8f7f5344c886a____lambda_invoker_cdecl_
0x1400081dd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400081e4  test    rax, rax
0x1400081e7  jz      short loc_1400081F2
0x1400081e9  cmp     rax, rcx
0x1400081ec  jnz     loc_140008971
0x1400081f2  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x1400081f9  mov     [rsp+160h+var_130], rdi
0x1400081fe  lea     rax, aWuaucltcoreExe; "wuaucltcore.exe launched with command l"...
0x140008205  mov     [rsp+160h+var_138], rax
0x14000820a  mov     [rsp+160h+ppv], rsi; int
0x14000820f  mov     r9d, r15d
0x140008212  xor     edx, edx
0x140008214  xor     ecx, ecx
0x140008216  mov     r8d, 1000h
0x14000821c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140008221  lea     rdx, [rsp+160h+lpMem]
0x140008226  mov     rcx, rdi
0x140008229  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x14000822e  mov     edi, eax
0x140008230  test    eax, eax
0x140008232  jns     short loc_140008241
0x140008234  mov     r9d, eax
0x140008237  mov     edx, 58h ; 'X'
0x14000823c  jmp     loc_14000888D
0x140008241  xor     edx, edx; Val
0x140008243  lea     r8d, [rdx+70h]; Size
0x140008247  lea     rcx, [rbp+60h+lpString1]; void *
0x14000824b  call    memset
0x140008250  mov     rax, [rsp+160h+lpMem]
0x140008255  test    rax, rax
0x140008258  jz      loc_1400088EA
0x14000825e  mov     r14d, esi
0x140008261  cmp     [rax], si
0x140008264  jz      short loc_1400082D5
0x140008266  mov     r8d, r14d
0x140008269  mov     dl, sil
0x14000826c  jmp     short loc_140008287
0x14000826e  cmp     cx, 20h ; ' '
0x140008272  jnz     short loc_140008278
0x140008274  test    dl, dl
0x140008276  jz      short loc_14000828F
0x140008278  cmp     cx, 22h ; '"'
0x14000827c  jnz     short loc_140008283
0x14000827e  test    dl, dl
0x140008280  setz    dl
0x140008283  add     rax, 2
0x140008287  movzx   ecx, word ptr [rax]
0x14000828a  test    cx, cx
0x14000828d  jnz     short loc_14000826E
0x14000828f  movzx   ecx, word ptr [rax]
0x140008292  test    cx, cx
0x140008295  jz      short loc_1400082A1
0x140008297  mov     [rax], si
0x14000829a  add     rax, 2
0x14000829e  movzx   ecx, word ptr [rax]
0x1400082a1  cmp     cx, 20h ; ' '
0x1400082a5  jnz     short loc_1400082B1
0x1400082a7  add     rax, 2
0x1400082ab  cmp     word ptr [rax], 20h ; ' '
0x1400082af  jz      short loc_1400082A7
0x1400082b1  cmp     [rax], si
0x1400082b4  jz      short loc_1400082D5
0x1400082b6  cmp     word ptr [rax], 2Dh ; '-'
0x1400082ba  jnz     short loc_1400082C1
0x1400082bc  mov     word ptr [rax], 2Fh ; '/'
0x1400082c1  mov     r14d, r8d
0x1400082c4  cmp     r8d, 0Eh
0x1400082c8  jnb     short loc_140008266
0x1400082ca  mov     [rbp+r8*8+60h+lpString1], rax
0x1400082cf  lea     r14d, [r8+1]
0x1400082d3  jmp     short loc_140008266
0x1400082d5  test    r14d, r14d
0x1400082d8  jz      loc_1400088EA
0x1400082de  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x1400082e3  mov     edi, eax
0x1400082e5  test    eax, eax
0x1400082e7  jns     short loc_1400082F6
0x1400082e9  mov     r9d, eax
0x1400082ec  mov     edx, 63h ; 'c'
0x1400082f1  jmp     loc_14000888D
0x1400082f6  mov     r13, rsi
0x1400082f9  mov     r15, rsi
0x1400082fc  mov     [rsp+160h+var_100], rsi
0x140008301  mov     [rsp+160h+var_108], rsi
0x140008306  mov     [rsp+160h+var_F8], rsi
0x14000830b  test    r14d, r14d
0x14000830e  jz      loc_1400088C6
0x140008314  mov     eax, esi
0x140008316  mov     rdi, [rbp+rax*8+60h+lpString1]
0x14000831b  lea     rdx, aReportnow; "/ReportNow"
0x140008322  mov     rcx, rdi; lpString1
0x140008325  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x14000832a  test    eax, eax
0x14000832c  jz      loc_1400086F9
0x140008332  lea     rdx, aIdleshutdownno; "/IdleShutdownNow"
0x140008339  mov     rcx, rdi; lpString1
0x14000833c  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x140008341  test    eax, eax
0x140008343  jz      loc_1400086F2
0x140008349  lea     rdx, aDeploymenthand; "/DeploymentHandlerFullPath"
0x140008350  mov     rcx, rdi; lpString1
0x140008353  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x140008358  test    eax, eax
0x14000835a  jnz     short loc_1400083AE
0x14000835c  inc     esi
0x14000835e  cmp     esi, r14d
0x140008361  jnb     loc_140008577
0x140008367  mov     rdi, [rbp+rsi*8+60h+lpString1]
0x14000836c  test    rbx, rbx
0x14000836f  jz      short loc_140008383
0x140008371  mov     rcx, rbx; hLibModule
0x140008374  call    cs:__imp_FreeLibrary
0x14000837a  mov     [rsp+160h+var_118], 0
0x140008383  lea     r8, [rsp+160h+var_118]
0x140008388  lea     rdx, [rsp+160h+var_E8]
0x14000838d  mov     rcx, rdi
0x140008390  call    ?GetModuleHandleW@@YAJPEB_WAEAV?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@wistd@@@wistd@@PEAPEAUHINSTANCE__@@@Z; GetModuleHandleW(wchar_t const *,wistd::unique_ptr<uus::Session,wistd::default_delete<uus::Session>> &,HINSTANCE__ * *)
0x140008395  mov     edi, eax
0x140008397  mov     rbx, [rsp+160h+var_118]
0x14000839c  test    eax, eax
0x14000839e  jns     loc_140008567
0x1400083a4  mov     edx, 84h
0x1400083a9  jmp     loc_1400086EB
0x1400083ae  lea     rdx, aClassid_0; "/ClassId"
0x1400083b5  mov     rcx, rdi; lpString1
0x1400083b8  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x1400083bd  test    eax, eax
0x1400083bf  jnz     short loc_1400083D9
0x1400083c1  lea     eax, [rsi+1]
0x1400083c4  mov     esi, eax
0x1400083c6  cmp     eax, r14d
0x1400083c9  jnb     loc_140008586
0x1400083cf  mov     r15, [rbp+rax*8+60h+lpString1]
0x1400083d4  jmp     loc_140008567
0x1400083d9  lea     rdx, aSignalsessionr; "/SignalSessionReadyHandle"
0x1400083e0  mov     rcx, rdi; lpString1
0x1400083e3  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x1400083e8  test    eax, eax
0x1400083ea  jnz     short loc_140008409
0x1400083ec  lea     eax, [rsi+1]
0x1400083ef  mov     esi, eax
0x1400083f1  cmp     eax, r14d
0x1400083f4  jnb     loc_140008595
0x1400083fa  mov     rax, [rbp+rax*8+60h+lpString1]
0x1400083ff  mov     [rsp+160h+var_100], rax
0x140008404  jmp     loc_140008567
0x140008409  lea     rdx, aSignalsessione; "/SignalSessionExitHandle"
0x140008410  mov     rcx, rdi; lpString1
0x140008413  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x140008418  test    eax, eax
0x14000841a  jnz     short loc_140008439
0x14000841c  lea     eax, [rsi+1]
0x14000841f  mov     esi, eax
0x140008421  cmp     eax, r14d
0x140008424  jnb     loc_1400085A4
0x14000842a  mov     rax, [rbp+rax*8+60h+lpString1]
0x14000842f  mov     [rsp+160h+var_108], rax
0x140008434  jmp     loc_140008567
0x140008439  lea     rdx, aParentsynchand; "/ParentSyncHandle"
0x140008440  mov     rcx, rdi; lpString1
0x140008443  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x140008448  test    eax, eax
0x14000844a  jnz     short loc_140008469
0x14000844c  lea     eax, [rsi+1]
0x14000844f  mov     esi, eax
0x140008451  cmp     eax, r14d
0x140008454  jnb     loc_1400085B3
0x14000845a  mov     rax, [rbp+rax*8+60h+lpString1]
0x14000845f  mov     [rsp+160h+var_F8], rax
0x140008464  jmp     loc_140008567
0x140008469  lea     rdx, aDeploymentsess_1; "/DeploymentSessionVersion"
0x140008470  mov     rcx, rdi; lpString1
0x140008473  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x140008478  test    eax, eax
0x14000847a  jnz     short loc_140008494
0x14000847c  lea     eax, [rsi+1]
0x14000847f  mov     esi, eax
0x140008481  cmp     eax, r14d
0x140008484  jnb     loc_1400085C2
0x14000848a  mov     r13, [rbp+rax*8+60h+lpString1]
0x14000848f  jmp     loc_140008567
0x140008494  lea     rdx, aRundeployments; "/RunDeploymentSession"
0x14000849b  mov     rcx, rdi; lpString1
0x14000849e  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x1400084a3  test    eax, eax
0x1400084a5  jz      loc_1400086B7
0x1400084ab  lea     rdx, aRunhandlercoms; "/RunHandlerComServer"
0x1400084b2  mov     rcx, rdi; lpString1
0x1400084b5  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x1400084ba  test    eax, eax
0x1400084bc  jz      loc_140008632
0x1400084c2  lea     rdx, aResetauthoriza; "/ResetAuthorization"
0x1400084c9  mov     rcx, rdi; lpString1
0x1400084cc  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x1400084d1  test    eax, eax
0x1400084d3  jnz     short loc_140008501
0x1400084d5  cmp     r12d, 2
0x1400084d9  jnb     loc_1400085E0
0x1400084df  cmp     dword ptr [rsp+160h+var_120], eax
0x1400084e3  jnz     loc_1400085D1
0x1400084e9  mov     eax, r12d
0x1400084ec  mov     [rbp+rax*4+60h+var_E0], 0
0x1400084f4  inc     r12d
0x1400084f7  mov     dword ptr [rsp+160h+var_120], 1
0x1400084ff  jmp     short loc_140008567
0x140008501  lea     rdx, aReseteulas; "/ResetEulas"
0x140008508  mov     rcx, rdi; lpString1
0x14000850b  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x140008510  test    eax, eax
0x140008512  jnz     short loc_140008540
0x140008514  cmp     r12d, 2
0x140008518  jnb     loc_1400085FE
0x14000851e  cmp     dword ptr [rsp+160h+var_F0], eax
0x140008522  jnz     loc_1400085EF
0x140008528  mov     eax, r12d
0x14000852b  mov     [rbp+rax*4+60h+var_E0], 1
0x140008533  inc     r12d
0x140008536  mov     dword ptr [rsp+160h+var_F0], 1
0x14000853e  jmp     short loc_140008567
0x140008540  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetImpl(void)'::`2'::impl
0x140008547  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::__private_IsEnabled(void)
0x14000854c  test    al, al
0x14000854e  jz      short loc_140008567
0x140008550  lea     rdx, aRemoteuhproces; "/RemoteUHProcessHost"
0x140008557  mov     rcx, rdi; lpString1
0x14000855a  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x14000855f  test    eax, eax
0x140008561  jz      loc_14000860D
0x140008567  inc     esi
0x140008569  cmp     esi, r14d
0x14000856c  jb      loc_140008314
0x140008572  jmp     loc_1400086FE
0x140008577  mov     edi, 80070057h
0x14000857c  mov     edx, 7Fh
  ... truncated ...
```
