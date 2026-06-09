# WdsSmartLoad(wchar_t const *,wchar_t const *,HINSTANCE__ *,bool)

- ea: `0x1800130b8`
- end: `0x18001334a`
- name: `?WdsSmartLoad@@YAJPEB_W0PEAUHINSTANCE__@@_N@Z`
- size: `658`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, HINSTANCE)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002500`

## callees

- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18000ed98`
- `0x1800118a4`
- `0x180011e10`
- `0x180012e78`
- `0x1800130b8`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001310f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001313e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001310f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001313e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131e1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001317a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001318e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001317a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001318e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800130f2`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800130f2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180013105`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800131d7`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180013105`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800131d7`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x180013130`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x180013130`

## string_xrefs

- `0x1800130eb`: `wdscore.dll`
- `0x180013129`: `COMPONENT_BASED_SERVICING_LOGFILE`

## pseudocode

```c
__int64 __fastcall WdsSmartLoad(const wchar_t *a1, const wchar_t *a2, HINSTANCE a3)
{
  BOOL ModuleHandle; // eax
  HMODULE v5; // rcx
  __int64 (*ProcAddress)(void); // rdi
  FARPROC v7; // rax
  void (*v8)(void); // rbx
  HMODULE v9; // rdi
  int v10; // eax
  struct LogAdapter::Logger *v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rdx
  char *v16; // r9
  int v17; // eax
  __int64 v18; // rcx
  _QWORD v19[4]; // [rsp+20h] [rbp-38h] BYREF
  HMODULE phModule; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  v19[2] = 0;
  phModule = 0;
  ModuleHandle = GetModuleHandleExW(0, L"wdscore.dll", &phModule);
  v5 = phModule;
  if ( !ModuleHandle )
  {
LABEL_2:
    if ( v5 && !FreeLibrary(v5) )
    {
      GetLastError();
      __fastfail(7u);
    }
    v17 = WdsLoad(a1, 0);
    v11 = LogAdapter::g_Logger;
    v12 = v17;
    if ( v17 < 0 )
    {
      LODWORD(phModule) = v17;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initialize logging session");
        v19[0] = &phModule;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v18,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v19);
      }
      v14 = 1125;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
        (const char *)v12);
      return v12;
    }
    if ( LogAdapter::g_Logger )
    {
      v16 = "Module initialized WDS logging";
      goto LABEL_26;
    }
    return 0;
  }
  ProcAddress = GetProcAddress(phModule, "WdsGetSetupLog");
  v7 = GetProcAddress(phModule, "WdsSetupLogDestroy");
  v8 = (void (*)(void))v7;
  if ( !ProcAddress || !v7 || !ProcAddress() )
  {
    v5 = phModule;
    goto LABEL_2;
  }
  v9 = phModule;
  phModule = 0;
  v8();
  if ( phModule && !FreeLibrary(phModule) )
  {
    GetLastError();
    __fastfail(7u);
  }
  v10 = WdsPostLoad(v9);
  v11 = LogAdapter::g_Logger;
  v12 = v10;
  if ( v10 < 0 )
  {
    LODWORD(phModule) = v10;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load existing logging session");
      v19[0] = &phModule;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v13,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v19);
    }
    v14 = 1110;
    goto LABEL_16;
  }
  if ( LogAdapter::g_Logger )
  {
    v16 = "Module starts contributing to an existing logging session";
LABEL_26:
    LogAdapter::Logger::LogNumObjects<>((__int64)v11, 1, 1, (struct Windows::Rtl::IRtlFormattedOutputStream *)v16);
  }
  return 0;
}

```

## disassembly

```asm
0x1800130b8  push    rbp
0x1800130ba  push    rbx
0x1800130bb  push    rsi
0x1800130bc  push    rdi
0x1800130bd  mov     rbp, rsp
0x1800130c0  sub     rsp, 58h
0x1800130c4  mov     rax, cs:__security_cookie
0x1800130cb  xor     rax, rsp
0x1800130ce  mov     [rbp+var_10], rax
0x1800130d2  mov     rsi, rcx
0x1800130d5  mov     [rbp+lpValue], 0
0x1800130dd  xor     ecx, ecx; dwFlags
0x1800130df  mov     [rbp+phModule], 0
0x1800130e7  lea     r8, [rbp+phModule]; phModule
0x1800130eb  lea     rdx, ModuleName; "wdscore.dll"
0x1800130f2  call    cs:__imp_GetModuleHandleExW
0x1800130f8  mov     rcx, [rbp+phModule]; hModule
0x1800130fc  test    eax, eax
0x1800130fe  jnz     short loc_180013173
0x180013100  test    rcx, rcx
0x180013103  jz      short loc_18001311C
0x180013105  call    cs:__imp_FreeLibrary
0x18001310b  test    eax, eax
0x18001310d  jnz     short loc_18001311C
0x18001310f  call    cs:__imp_GetLastError
0x180013115  mov     ecx, 7
0x18001311a  int     29h; Win8: RtlFailFast(ecx)
0x18001311c  mov     rdx, [rbp+lpValue]; lpValue
0x180013120  test    rdx, rdx
0x180013123  jz      loc_1800132C1
0x180013129  lea     rcx, Name; "COMPONENT_BASED_SERVICING_LOGFILE"
0x180013130  call    cs:__imp_SetEnvironmentVariableW
0x180013136  test    eax, eax
0x180013138  jnz     loc_1800132C1
0x18001313e  call    cs:__imp_GetLastError
0x180013144  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x18001314c  mov     ebx, eax
0x18001314e  jz      loc_18001329F
0x180013154  lea     r9, [rbp+lpValue]
0x180013158  lea     r8, aFailedSettingO; "Failed setting offline CBS text log fil"...
0x18001315f  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180013164  test    ebx, ebx
0x180013166  jg      loc_180013277
0x18001316c  mov     eax, ebx
0x18001316e  jmp     loc_18001327F
0x180013173  lea     rdx, aWdsgetsetuplog; "WdsGetSetupLog"
0x18001317a  call    cs:__imp_GetProcAddress
0x180013180  mov     rcx, [rbp+phModule]; hModule
0x180013184  lea     rdx, aWdssetuplogdes; "WdsSetupLogDestroy"
0x18001318b  mov     rdi, rax
0x18001318e  call    cs:__imp_GetProcAddress
0x180013194  mov     rbx, rax
0x180013197  test    rdi, rdi
0x18001319a  jz      loc_18001326E
0x1800131a0  test    rax, rax
0x1800131a3  jz      loc_18001326E
0x1800131a9  mov     rax, rdi
0x1800131ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131b1  test    rax, rax
0x1800131b4  jz      loc_18001326E
0x1800131ba  mov     rdi, [rbp+phModule]
0x1800131be  mov     rax, rbx
0x1800131c1  mov     [rbp+phModule], 0
0x1800131c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131ce  mov     rcx, [rbp+phModule]; hLibModule
0x1800131d2  test    rcx, rcx
0x1800131d5  jz      short loc_1800131EE
0x1800131d7  call    cs:__imp_FreeLibrary
0x1800131dd  test    eax, eax
0x1800131df  jnz     short loc_1800131EE
0x1800131e1  call    cs:__imp_GetLastError
0x1800131e7  mov     ecx, 7
0x1800131ec  int     29h; Win8: RtlFailFast(ecx)
0x1800131ee  mov     rcx, rdi; hModule
0x1800131f1  call    ?WdsPostLoad@@YAJPEAUHINSTANCE__@@@Z; WdsPostLoad(HINSTANCE__ *)
0x1800131f6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800131fd  mov     ebx, eax
0x1800131ff  test    eax, eax
0x180013201  jns     short loc_180013259
0x180013203  mov     dword ptr [rbp+phModule], eax
0x180013206  test    rcx, rcx
0x180013209  jz      short loc_18001323A
0x18001320b  xor     edx, edx
0x18001320d  lea     r9, aFailedToLoadEx; "Failed to load existing logging session"
0x180013214  lea     r8d, [rdx+3]
0x180013218  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001321d  lea     rax, [rbp+phModule]
0x180013221  mov     edx, 3
0x180013226  lea     r9, [rbp+var_38]
0x18001322a  mov     [rbp+var_38], rax
0x18001322e  lea     r8, asc_1800233AC; ": {}"
0x180013235  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001323a  mov     edx, 456h; void *
0x18001323f  mov     rcx, [rbp+20h]; this
0x180013243  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x18001324a  mov     r9d, ebx; char *
0x18001324d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013252  mov     eax, ebx
0x180013254  jmp     loc_180013335
0x180013259  test    rcx, rcx
0x18001325c  jz      loc_180013333
0x180013262  lea     r9, aModuleStartsCo; "Module starts contributing to an existi"...
0x180013269  jmp     loc_180013325
0x18001326e  mov     rcx, [rbp+phModule]
0x180013272  jmp     loc_180013100
0x180013277  movzx   eax, bx
0x18001327a  or      eax, 80070000h
0x18001327f  mov     dword ptr [rbp+phModule], eax
0x180013282  lea     r9, [rbp+var_38]
0x180013286  lea     rax, [rbp+phModule]
0x18001328a  mov     edx, 3
0x18001328f  lea     r8, a0; ": {0}"
0x180013296  mov     [rbp+var_38], rax
0x18001329a  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001329f  test    ebx, ebx
0x1800132a1  jz      loc_180013333
0x1800132a7  mov     rcx, [rbp+20h]; this
0x1800132ab  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x1800132b2  mov     r9d, ebx; char *
0x1800132b5  mov     edx, 462h; void *
0x1800132ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800132bf  jmp     short loc_180013335
0x1800132c1  xor     edx, edx; HINSTANCE
0x1800132c3  mov     rcx, rsi; wchar_t *
0x1800132c6  call    ?WdsLoad@@YAJPEB_WPEAUHINSTANCE__@@@Z; WdsLoad(wchar_t const *,HINSTANCE__ *)
0x1800132cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800132d2  mov     ebx, eax
0x1800132d4  test    eax, eax
0x1800132d6  jns     short loc_180013319
0x1800132d8  mov     dword ptr [rbp+phModule], eax
0x1800132db  test    rcx, rcx
0x1800132de  jz      short loc_18001330F
0x1800132e0  xor     edx, edx
0x1800132e2  lea     r9, aFailedToInitia_0; "Failed to initialize logging session"
0x1800132e9  lea     r8d, [rdx+3]
0x1800132ed  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800132f2  lea     rax, [rbp+phModule]
0x1800132f6  mov     edx, 3
0x1800132fb  lea     r9, [rbp+var_38]
0x1800132ff  mov     [rbp+var_38], rax
0x180013303  lea     r8, asc_1800233AC; ": {}"
0x18001330a  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001330f  mov     edx, 465h
0x180013314  jmp     loc_18001323F
0x180013319  test    rcx, rcx
0x18001331c  jz      short loc_180013333
0x18001331e  lea     r9, aModuleInitiali; "Module initialized WDS logging"
0x180013325  mov     r8d, 1
0x18001332b  mov     dl, r8b
0x18001332e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180013333  xor     eax, eax
0x180013335  mov     rcx, [rbp+var_10]
0x180013339  xor     rcx, rsp; StackCookie
0x18001333c  call    __security_check_cookie
0x180013341  add     rsp, 58h
0x180013345  pop     rdi
0x180013346  pop     rsi
0x180013347  pop     rbx
0x180013348  pop     rbp
0x180013349  retn
```
