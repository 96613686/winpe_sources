# CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)

- ea: `0x180014470`
- end: `0x1800147a9`
- name: `?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z`
- size: `825`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, __int64, const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011e10`

## callees

- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18000ed98`
- `0x1800118a4`
- `0x180014470`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014795`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001452e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001452e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014568`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001468e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001478b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014568`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001468e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001478b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014666`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014666`

## string_xrefs

- `0x1800144a2`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing`
- `0x1800145b8`: `Failed to open the registry root: n/a, key: {}.`
- `0x1800146bf`: `Failed to query registry value: {}`
- `0x180014721`: `Registry value is not a DWORD type.`

## pseudocode

```c
__int64 __fastcall CbsRegQueryDWORDValue(HKEY a1, const wchar_t *a2, __int64 a3, const wchar_t *a4, unsigned int *a5)
{
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  LSTATUS v9; // ebx
  HKEY v10; // rcx
  bool v11; // zf
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rcx
  HKEY v22; // rcx
  int phkResult; // [rsp+20h] [rbp-60h]
  unsigned int phkResulta; // [rsp+20h] [rbp-60h]
  int **v25; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR lpValueName; // [rsp+38h] [rbp-48h] BYREF
  const WCHAR *v27; // [rsp+40h] [rbp-40h] BYREF
  int v28; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-28h] BYREF
  DWORD Type; // [rsp+60h] [rbp-20h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-1Ch] BYREF
  int *v32; // [rsp+68h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  lpValueName = L"EnableLog";
  v27 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing";
  if ( !a5 )
  {
    v5 = -2147467261;
    v28 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value result specified");
      v32 = &v28;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v28,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v32);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return v5;
  }
  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing",
         0,
         0x20019u,
         &hKey);
  v9 = v6;
  if ( v6 == 2 || v6 == 3 )
  {
    v5 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_8;
  }
  if ( v6 )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogPartial<wchar_t const *>(
        v8,
        v7,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open the registry root: n/a, key: {}.",
        (__int64)&v27);
      if ( v9 > 0 )
        v14 = (unsigned __int16)v9 | 0x80070000;
      else
        v14 = v9;
      v28 = v14;
      v32 = &v28;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v13,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v32);
    }
    v15 = 367;
    goto LABEL_21;
  }
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, Data, &cbData);
  if ( v9 == 2 )
  {
    if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
    {
      GetLastError();
      __fastfail(7u);
    }
    return 2147942402LL;
  }
  else
  {
    if ( v9 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<wchar_t const *>(
          v18,
          v17,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to query registry value: {}",
          (__int64)&lpValueName);
        if ( v9 > 0 )
          v20 = (unsigned __int16)v9 | 0x80070000;
        else
          v20 = v9;
        v28 = v20;
        v25 = (int **)&v28;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v19,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)&v25);
      }
      v15 = 380;
LABEL_21:
      v16 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v15,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
              (const char *)(unsigned int)v9,
              phkResulta);
      v10 = hKey;
      v5 = v16;
      if ( hKey )
      {
        v11 = ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) == 0xFFFFFFFF80000000uLL;
        goto LABEL_10;
      }
      return v5;
    }
    if ( Type != 4 )
    {
      v5 = -2147024883;
      LODWORD(v32) = -2147024883;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Registry value is not a DWORD type.");
        v25 = &v32;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v21,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v25);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17E,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
        (const char *)0x8007000DLL,
        phkResulta);
LABEL_8:
      v10 = hKey;
      if ( hKey )
      {
        v11 = ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) == 0xFFFFFFFF80000000uLL;
LABEL_10:
        if ( !v11 && RegCloseKey(v10) )
        {
          GetLastError();
          __fastfail(7u);
        }
        return v5;
      }
      return v5;
    }
    v22 = hKey;
    *a5 = *(_DWORD *)Data;
    if ( v22 && ((unsigned __int64)v22 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(v22) )
    {
      GetLastError();
      __fastfail(7u);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180014470  mov     [rsp-8+arg_0], rbx
0x180014475  mov     [rsp-8+arg_8], rsi
0x18001447a  push    rbp
0x18001447b  mov     rbp, rsp
0x18001447e  sub     rsp, 80h
0x180014485  mov     rax, cs:__security_cookie
0x18001448c  xor     rax, rsp
0x18001448f  mov     [rbp+var_8], rax
0x180014493  mov     rsi, [rbp+arg_20]
0x180014497  lea     rax, aEnablelog; "EnableLog"
0x18001449e  mov     [rbp+lpValueName], rax
0x1800144a2  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800144a9  mov     [rbp+var_40], rdx
0x1800144ad  test    rsi, rsi
0x1800144b0  jnz     short loc_18001450D
0x1800144b2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800144b9  mov     ebx, 80004003h
0x1800144be  mov     [rbp+var_30], ebx
0x1800144c1  test    rcx, rcx
0x1800144c4  jz      short loc_1800144F3
0x1800144c6  lea     r9, aNoValueResultS; "No value result specified"
0x1800144cd  xor     edx, edx
0x1800144cf  lea     r8d, [rsi+3]
0x1800144d3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800144d8  lea     rcx, [rbp+var_30]
0x1800144dc  lea     r9, [rbp+var_18]
0x1800144e0  mov     [rbp+var_18], rcx
0x1800144e4  lea     r8, asc_1800233AC; ": {}"
0x1800144eb  lea     edx, [rsi+3]
0x1800144ee  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800144f3  mov     rcx, [rbp+8]; this
0x1800144f7  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1800144fe  mov     r9d, ebx; char *
0x180014501  mov     edx, 163h; void *
0x180014506  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001450b  jmp     short loc_18001457F
0x18001450d  lea     rax, [rbp+hKey]
0x180014511  mov     [rbp+hKey], 0
0x180014519  mov     r9d, 20019h; samDesired
0x18001451f  mov     [rsp+80h+phkResult], rax; unsigned int
0x180014524  xor     r8d, r8d; ulOptions
0x180014527  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001452e  call    cs:__imp_RegOpenKeyExW
0x180014534  mov     ebx, eax
0x180014536  cmp     eax, 2
0x180014539  jz      short loc_180014544
0x18001453b  cmp     eax, 3
0x18001453e  jnz     short loc_1800145A2
0x180014540  test    eax, eax
0x180014542  jle     short loc_18001454D
0x180014544  movzx   ebx, bx
0x180014547  or      ebx, 80070000h
0x18001454d  mov     rcx, [rbp+hKey]; hKey
0x180014551  test    rcx, rcx
0x180014554  jz      short loc_18001457F
0x180014556  mov     r8, 0FFFFFFFF80000000h
0x18001455d  mov     rax, rcx
0x180014560  and     rax, r8
0x180014563  cmp     rax, r8
0x180014566  jz      short loc_18001457F
0x180014568  call    cs:__imp_RegCloseKey
0x18001456e  test    eax, eax
0x180014570  jz      short loc_18001457F
0x180014572  call    cs:__imp_GetLastError
0x180014578  mov     ecx, 7
0x18001457d  int     29h; Win8: RtlFailFast(ecx)
0x18001457f  mov     eax, ebx
0x180014581  mov     rcx, [rbp+var_8]
0x180014585  xor     rcx, rsp; StackCookie
0x180014588  call    __security_check_cookie
0x18001458d  lea     r11, [rsp+80h+var_s0]
0x180014595  mov     rbx, [r11+10h]
0x180014599  mov     rsi, [r11+18h]
0x18001459d  mov     rsp, r11
0x1800145a0  pop     rbp
0x1800145a1  retn
0x1800145a2  test    ebx, ebx
0x1800145a4  jz      loc_180014630
0x1800145aa  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x1800145b2  jz      short loc_1800145F4
0x1800145b4  lea     r9, [rbp+var_40]
0x1800145b8  lea     r8, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x1800145bf  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800145c4  test    ebx, ebx
0x1800145c6  jg      short loc_1800145CC
0x1800145c8  mov     eax, ebx
0x1800145ca  jmp     short loc_1800145D4
0x1800145cc  movzx   eax, bx
0x1800145cf  or      eax, 80070000h
0x1800145d4  mov     [rbp+var_30], eax
0x1800145d7  lea     r9, [rbp+var_18]
0x1800145db  lea     rax, [rbp+var_30]
0x1800145df  mov     edx, 3
0x1800145e4  lea     r8, a0; ": {0}"
0x1800145eb  mov     [rbp+var_18], rax
0x1800145ef  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800145f4  mov     edx, 16Fh; void *
0x1800145f9  mov     rcx, [rbp+8]; this
0x1800145fd  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x180014604  mov     r9d, ebx; char *
0x180014607  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001460c  mov     rcx, [rbp+hKey]
0x180014610  mov     ebx, eax
0x180014612  test    rcx, rcx
0x180014615  jz      loc_18001457F
0x18001461b  mov     r8, 0FFFFFFFF80000000h
0x180014622  mov     rdx, rcx
0x180014625  and     rdx, r8
0x180014628  cmp     rdx, r8
0x18001462b  jmp     loc_180014566
0x180014630  mov     rdx, [rbp+lpValueName]; lpValueName
0x180014634  lea     rax, [rbp+cbData]
0x180014638  mov     rcx, [rbp+hKey]; hKey
0x18001463c  lea     r9, [rbp+Type]; lpType
0x180014640  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180014645  xor     r8d, r8d; lpReserved
0x180014648  lea     rax, [rbp+Data]
0x18001464c  mov     [rbp+Type], 0
0x180014653  mov     [rsp+80h+phkResult], rax; int
0x180014658  mov     dword ptr [rbp+Data], 0
0x18001465f  mov     [rbp+cbData], 4
0x180014666  call    cs:__imp_RegQueryValueExW
0x18001466c  mov     ebx, eax
0x18001466e  cmp     eax, 2
0x180014671  jnz     short loc_1800146AD
0x180014673  mov     rcx, [rbp+hKey]; hKey
0x180014677  test    rcx, rcx
0x18001467a  jz      short loc_1800146A3
0x18001467c  mov     r8, 0FFFFFFFF80000000h
0x180014683  mov     rax, rcx
0x180014686  and     rax, r8
0x180014689  cmp     rax, r8
0x18001468c  jz      short loc_1800146A3
0x18001468e  call    cs:__imp_RegCloseKey
0x180014694  test    eax, eax
0x180014696  jz      short loc_1800146A3
0x180014698  call    cs:__imp_GetLastError
0x18001469e  lea     ecx, [rbx+5]
0x1800146a1  int     29h; Win8: RtlFailFast(ecx)
0x1800146a3  mov     eax, 80070002h
0x1800146a8  jmp     loc_180014581
0x1800146ad  test    ebx, ebx
0x1800146af  jz      short loc_180014705
0x1800146b1  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x1800146b9  jz      short loc_1800146FB
0x1800146bb  lea     r9, [rbp+lpValueName]
0x1800146bf  lea     r8, aFailedToQueryR; "Failed to query registry value: {}"
0x1800146c6  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800146cb  test    ebx, ebx
0x1800146cd  jg      short loc_1800146D3
0x1800146cf  mov     eax, ebx
0x1800146d1  jmp     short loc_1800146DB
0x1800146d3  movzx   eax, bx
0x1800146d6  or      eax, 80070000h
0x1800146db  mov     [rbp+var_30], eax
0x1800146de  lea     r9, [rbp+var_50]
0x1800146e2  lea     rax, [rbp+var_30]
0x1800146e6  mov     edx, 3
0x1800146eb  lea     r8, a0; ": {0}"
0x1800146f2  mov     [rbp+var_50], rax
0x1800146f6  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800146fb  mov     edx, 17Ch
0x180014700  jmp     loc_1800145F9
0x180014705  cmp     [rbp+Type], 4
0x180014709  jz      short loc_18001476B
0x18001470b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180014712  mov     ebx, 8007000Dh
0x180014717  mov     dword ptr [rbp+var_18], ebx
0x18001471a  test    rcx, rcx
0x18001471d  jz      short loc_18001474E
0x18001471f  xor     edx, edx
0x180014721  lea     r9, aRegistryValueI_0; "Registry value is not a DWORD type."
0x180014728  lea     r8d, [rdx+3]
0x18001472c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180014731  lea     rax, [rbp+var_18]
0x180014735  mov     edx, 3
0x18001473a  lea     r9, [rbp+var_50]
0x18001473e  mov     [rbp+var_50], rax
0x180014742  lea     r8, asc_1800233AC; ": {}"
0x180014749  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001474e  mov     rcx, [rbp+8]; this
0x180014752  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x180014759  mov     r9d, ebx; char *
0x18001475c  mov     edx, 17Eh; void *
0x180014761  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014766  jmp     loc_18001454D
0x18001476b  mov     rcx, [rbp+hKey]; hKey
0x18001476f  mov     eax, dword ptr [rbp+Data]
0x180014772  mov     [rsi], eax
0x180014774  test    rcx, rcx
0x180014777  jz      short loc_1800147A2
0x180014779  mov     r8, 0FFFFFFFF80000000h
0x180014780  mov     rax, rcx
0x180014783  and     rax, r8
0x180014786  cmp     rax, r8
0x180014789  jz      short loc_1800147A2
0x18001478b  call    cs:__imp_RegCloseKey
0x180014791  test    eax, eax
0x180014793  jz      short loc_1800147A2
0x180014795  call    cs:__imp_GetLastError
0x18001479b  mov     ecx, 7
0x1800147a0  int     29h; Win8: RtlFailFast(ecx)
0x1800147a2  xor     eax, eax
0x1800147a4  jmp     loc_180014581
```
