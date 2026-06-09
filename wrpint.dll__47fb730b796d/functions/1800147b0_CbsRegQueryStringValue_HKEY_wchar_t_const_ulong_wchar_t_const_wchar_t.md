# CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)

- ea: `0x1800147b0`
- end: `0x180014cd9`
- name: `?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z`
- size: `1321`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, __int64, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011e10`

## callees

- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18000ed98`
- `0x18001029c`
- `0x180011654`
- `0x1800118a4`
- `0x1800147b0`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014cc5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014870`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014870`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800148ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014b1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014bf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014cbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800148ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014b1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014bf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014cbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800149fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014af7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014c2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800149fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014af7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014c2e`

## string_xrefs

- `0x1800147d7`: `LogPath`
- `0x1800147e2`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide\Configuration`
- `0x1800148fb`: `Failed to open the registry root: n/a, key: {}.`
- `0x180014a95`: `Failed initial query of value to get type, size, and value of registry value: {}`
- `0x180014b55`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x180014a27`: `Registry value is not a string type.`
- `0x180014c48`: `Failed to query registry value: {}`

## pseudocode

```c
__int64 __fastcall CbsRegQueryStringValue(HKEY a1, const wchar_t *a2, __int64 a3, const wchar_t *a4, wchar_t **a5)
{
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // ebx
  HKEY v10; // rcx
  bool v11; // zf
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  LPBYTE v18; // rcx
  unsigned __int64 v19; // rbx
  HKEY v20; // r12
  int v21; // r15d
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  LSTATUS v25; // edi
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  LSTATUS v31; // edi
  __int64 v32; // rcx
  unsigned int v33; // eax
  int v34; // eax
  unsigned int v35; // edi
  __int64 v36; // rdx
  __int64 v37; // rcx
  LSTATUS v38; // edi
  __int64 v39; // rcx
  unsigned int v40; // eax
  int phkResult; // [rsp+20h] [rbp-60h]
  unsigned int phkResulta; // [rsp+20h] [rbp-60h]
  unsigned __int64 v43; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 *v44; // [rsp+38h] [rbp-48h] BYREF
  int *v45; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-38h] BYREF
  const WCHAR *v47; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-18h] BYREF
  int v50; // [rsp+6Ch] [rbp-14h] BYREF
  DWORD Type; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  lpValueName = L"LogPath";
  v47 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide\\Configuration";
  if ( !a5 )
  {
    v5 = -2147467261;
    v50 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value result specified");
      v43 = (unsigned __int64)&v50;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v50,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v43);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return v5;
  }
  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide\\Configuration",
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
        (__int64)&v47);
      if ( v9 > 0 )
        v14 = (unsigned __int16)v9 | 0x80070000;
      else
        v14 = v9;
      v50 = v14;
      v43 = (unsigned __int64)&v50;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v13,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v43);
    }
    v15 = (unsigned int)v9;
    v16 = 182;
    goto LABEL_21;
  }
  v18 = (LPBYTE)*a5;
  v19 = 0;
  v20 = hKey;
  v21 = 0;
  v43 = 0;
  Type = 0;
  cbData = 0;
  if ( v18 )
  {
    v5 = SczSize(v18, &v43);
    if ( (v5 & 0x80000000) != 0 )
    {
      v22 = 194;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
        (const char *)v5,
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
    v19 = v43;
    if ( v43 >= 2 )
    {
      if ( 2 * v43 - 4 > 0xFFFFFFFF )
      {
        cbData = -1;
        v5 = -2147024362;
        v22 = 199;
        goto LABEL_26;
      }
      cbData = 2 * v43 - 4;
    }
    v25 = RegQueryValueExW(v20, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
    if ( !v25 )
    {
      v21 = 1;
      goto LABEL_32;
    }
    if ( v25 != 234 )
    {
      if ( v25 != 2 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<wchar_t const *>(
            v24,
            v23,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed initial query of value to get type, size, and value"
                                                              " of registry value: {}",
            (__int64)&lpValueName);
          if ( v25 > 0 )
            v28 = (unsigned __int16)v25 | 0x80070000;
          else
            v28 = v25;
          v50 = v28;
          v45 = &v50;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            v27,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
            (__int64)&v45);
        }
        v15 = (unsigned int)v25;
        v16 = 224;
        goto LABEL_21;
      }
LABEL_46:
      if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
      {
        GetLastError();
        __fastfail(7u);
      }
      return 2147942402LL;
    }
  }
  else
  {
    v31 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
    if ( v31 == 2 )
      goto LABEL_46;
    if ( v31 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<wchar_t const *>(
          v30,
          v29,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to query value to get type and size of registry root: n/a, value: {}",
          (__int64)&lpValueName);
        if ( v31 > 0 )
          v33 = (unsigned __int16)v31 | 0x80070000;
        else
          v33 = v31;
        LODWORD(v43) = v33;
        v44 = &v43;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v32,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)&v44);
      }
      v15 = (unsigned int)v31;
      v16 = 240;
LABEL_21:
      v17 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v16,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
              (const char *)v15,
              phkResulta);
      v10 = hKey;
      v5 = v17;
      if ( hKey )
      {
        v11 = ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) == 0xFFFFFFFF80000000uLL;
        goto LABEL_10;
      }
      return v5;
    }
  }
LABEL_32:
  if ( Type - 1 > 1 )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Registry value is not a string type.");
      LODWORD(v43) = -2147024883;
      v44 = &v43;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v26,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v44);
    }
    v15 = 13;
    v16 = 246;
    goto LABEL_21;
  }
  if ( !v21 )
  {
    v19 = ((unsigned __int64)cbData >> 1) + 2;
    v34 = SczAlloc(a5, v19);
    v35 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
        (const char *)(unsigned int)v34,
        phkResulta);
      if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
      {
        GetLastError();
        __fastfail(7u);
      }
      return v35;
    }
    v38 = RegQueryValueExW(v20, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
    if ( v38 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<wchar_t const *>(
          v37,
          v36,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to query registry value: {}",
          (__int64)&lpValueName);
        if ( v38 > 0 )
          v40 = (unsigned __int16)v38 | 0x80070000;
        else
          v40 = v38;
        LODWORD(v43) = v40;
        v44 = &v43;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v39,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)&v44);
      }
      v15 = (unsigned int)v38;
      v16 = 266;
      goto LABEL_21;
    }
  }
  (*a5)[v19 - 2] = 0;
  (*a5)[v19 - 1] = 0;
  if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x1800147b0  push    rbp
0x1800147b2  push    rbx
0x1800147b3  push    rsi
0x1800147b4  push    rdi
0x1800147b5  push    r12
0x1800147b7  push    r14
0x1800147b9  push    r15
0x1800147bb  mov     rbp, rsp
0x1800147be  sub     rsp, 80h
0x1800147c5  mov     rax, cs:__security_cookie
0x1800147cc  xor     rax, rsp
0x1800147cf  mov     [rbp+var_8], rax
0x1800147d3  mov     r14, [rbp+arg_20]
0x1800147d7  lea     rax, aLogpath; "LogPath"
0x1800147de  mov     [rbp+lpValueName], rax
0x1800147e2  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800147e9  mov     [rbp+var_30], rdx
0x1800147ed  test    r14, r14
0x1800147f0  jnz     short loc_18001484F
0x1800147f2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800147f9  mov     ebx, 80004003h
0x1800147fe  mov     [rbp+var_14], ebx
0x180014801  test    rcx, rcx
0x180014804  jz      short loc_180014835
0x180014806  lea     esi, [r14+3]
0x18001480a  xor     edx, edx
0x18001480c  mov     r8d, esi
0x18001480f  lea     r9, aNoValueResultS; "No value result specified"
0x180014816  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001481b  lea     rcx, [rbp+var_14]
0x18001481f  mov     edx, esi
0x180014821  lea     r9, [rbp+var_50]
0x180014825  mov     [rbp+var_50], rcx
0x180014829  lea     r8, asc_1800233AC; ": {}"
0x180014830  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180014835  mov     rcx, [rbp+38h]; this
0x180014839  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x180014840  mov     r9d, ebx; char *
0x180014843  mov     edx, 0A7h; void *
0x180014848  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001484d  jmp     short loc_1800148C5
0x18001484f  lea     rax, [rbp+hKey]
0x180014853  mov     [rbp+hKey], 0
0x18001485b  mov     r9d, 20019h; samDesired
0x180014861  mov     [rsp+80h+phkResult], rax; int
0x180014866  xor     r8d, r8d; ulOptions
0x180014869  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014870  call    cs:__imp_RegOpenKeyExW
0x180014876  mov     ebx, eax
0x180014878  cmp     eax, 2
0x18001487b  jz      short loc_18001488A
0x18001487d  mov     esi, 3
0x180014882  cmp     eax, esi
0x180014884  jnz     short loc_1800148E5
0x180014886  test    eax, eax
0x180014888  jle     short loc_180014893
0x18001488a  movzx   ebx, bx
0x18001488d  or      ebx, 80070000h
0x180014893  mov     rcx, [rbp+hKey]; hKey
0x180014897  test    rcx, rcx
0x18001489a  jz      short loc_1800148C5
0x18001489c  mov     r8, 0FFFFFFFF80000000h
0x1800148a3  mov     rax, rcx
0x1800148a6  and     rax, r8
0x1800148a9  cmp     rax, r8
0x1800148ac  jz      short loc_1800148C5
0x1800148ae  call    cs:__imp_RegCloseKey
0x1800148b4  test    eax, eax
0x1800148b6  jz      short loc_1800148C5
0x1800148b8  call    cs:__imp_GetLastError
0x1800148be  mov     ecx, 7
0x1800148c3  int     29h; Win8: RtlFailFast(ecx)
0x1800148c5  mov     eax, ebx
0x1800148c7  mov     rcx, [rbp+var_8]
0x1800148cb  xor     rcx, rsp; StackCookie
0x1800148ce  call    __security_check_cookie
0x1800148d3  add     rsp, 80h
0x1800148da  pop     r15
0x1800148dc  pop     r14
0x1800148de  pop     r12
0x1800148e0  pop     rdi
0x1800148e1  pop     rsi
0x1800148e2  pop     rbx
0x1800148e3  pop     rbp
0x1800148e4  retn
0x1800148e5  test    ebx, ebx
0x1800148e7  jz      loc_180014970
0x1800148ed  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x1800148f5  jz      short loc_180014934
0x1800148f7  lea     r9, [rbp+var_30]
0x1800148fb  lea     r8, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x180014902  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180014907  test    ebx, ebx
0x180014909  jg      short loc_18001490F
0x18001490b  mov     eax, ebx
0x18001490d  jmp     short loc_180014917
0x18001490f  movzx   eax, bx
0x180014912  or      eax, 80070000h
0x180014917  mov     [rbp+var_14], eax
0x18001491a  lea     r9, [rbp+var_50]
0x18001491e  lea     rax, [rbp+var_14]
0x180014922  mov     edx, esi
0x180014924  lea     r8, a0; ": {0}"
0x18001492b  mov     [rbp+var_50], rax
0x18001492f  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180014934  mov     r9d, ebx; char *
0x180014937  mov     edx, 0B6h; void *
0x18001493c  mov     rcx, [rbp+38h]; this
0x180014940  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x180014947  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001494c  mov     rcx, [rbp+hKey]
0x180014950  mov     ebx, eax
0x180014952  test    rcx, rcx
0x180014955  jz      loc_1800148C5
0x18001495b  mov     r8, 0FFFFFFFF80000000h
0x180014962  mov     rdx, rcx
0x180014965  and     rdx, r8
0x180014968  cmp     rdx, r8
0x18001496b  jmp     loc_1800148AC
0x180014970  mov     rcx, [r14]
0x180014973  xor     ebx, ebx
0x180014975  mov     r12, [rbp+hKey]
0x180014979  xor     r15d, r15d
0x18001497c  mov     [rbp+var_50], rbx
0x180014980  mov     [rbp+Type], ebx
0x180014983  mov     [rbp+cbData], ebx
0x180014986  test    rcx, rcx
0x180014989  jz      loc_180014ADB
0x18001498f  lea     rdx, [rbp+var_50]
0x180014993  call    SczSize
0x180014998  mov     ebx, eax
0x18001499a  test    eax, eax
0x18001499c  jns     short loc_1800149BB
0x18001499e  mov     edx, 0C2h; void *
0x1800149a3  mov     rcx, [rbp+38h]; this
0x1800149a7  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1800149ae  mov     r9d, ebx; char *
0x1800149b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800149b6  jmp     loc_180014893
0x1800149bb  mov     rbx, [rbp+var_50]
0x1800149bf  cmp     rbx, 2
0x1800149c3  jb      short loc_1800149DE
0x1800149c5  lea     rax, ds:0FFFFFFFFFFFFFFFCh[rbx*2]
0x1800149cd  mov     ecx, 0FFFFFFFFh
0x1800149d2  cmp     rax, rcx
0x1800149d5  ja      loc_180014A69
0x1800149db  mov     [rbp+cbData], eax
0x1800149de  mov     rdx, [rbp+lpValueName]; lpValueName
0x1800149e2  lea     rax, [rbp+cbData]
0x1800149e6  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800149eb  lea     r9, [rbp+Type]; lpType
0x1800149ef  mov     rax, [r14]
0x1800149f2  xor     r8d, r8d; lpReserved
0x1800149f5  mov     rcx, r12; hKey
0x1800149f8  mov     [rsp+80h+phkResult], rax; int
0x1800149fd  call    cs:__imp_RegQueryValueExW
0x180014a03  mov     edi, eax
0x180014a05  test    eax, eax
0x180014a07  jnz     short loc_180014A7B
0x180014a09  lea     r15d, [rax+1]
0x180014a0d  mov     eax, [rbp+Type]
0x180014a10  dec     eax
0x180014a12  cmp     eax, 1
0x180014a15  jbe     loc_180014B9B
0x180014a1b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180014a22  test    rcx, rcx
0x180014a25  jz      short loc_180014A59
0x180014a27  lea     r9, aRegistryValueI; "Registry value is not a string type."
0x180014a2e  mov     r8d, esi
0x180014a31  xor     edx, edx
0x180014a33  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180014a38  lea     rax, [rbp+var_50]
0x180014a3c  mov     dword ptr [rbp+var_50], 8007000Dh
0x180014a43  lea     r9, [rbp+var_48]
0x180014a47  mov     [rbp+var_48], rax
0x180014a4b  lea     r8, a0; ": {0}"
0x180014a52  mov     edx, esi
0x180014a54  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180014a59  mov     r9d, 0Dh
0x180014a5f  mov     edx, 0F6h
0x180014a64  jmp     loc_18001493C
0x180014a69  mov     [rbp+cbData], ecx
0x180014a6c  mov     ebx, 80070216h
0x180014a71  mov     edx, 0C7h
0x180014a76  jmp     loc_1800149A3
0x180014a7b  cmp     edi, 0EAh
0x180014a81  jz      short loc_180014A0D
0x180014a83  cmp     edi, 2
0x180014a86  jz      short loc_180014B04
0x180014a88  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, r15; LogAdapter::Logger * LogAdapter::g_Logger
0x180014a8f  jz      short loc_180014ACE
0x180014a91  lea     r9, [rbp+lpValueName]
0x180014a95  lea     r8, aFailedInitialQ; "Failed initial query of value to get ty"...
0x180014a9c  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180014aa1  test    edi, edi
0x180014aa3  jg      short loc_180014AA9
0x180014aa5  mov     eax, edi
0x180014aa7  jmp     short loc_180014AB1
0x180014aa9  movzx   eax, di
0x180014aac  or      eax, 80070000h
0x180014ab1  mov     [rbp+var_14], eax
0x180014ab4  lea     r9, [rbp+var_40]
0x180014ab8  lea     rax, [rbp+var_14]
0x180014abc  mov     edx, esi
0x180014abe  lea     r8, a0; ": {0}"
0x180014ac5  mov     [rbp+var_40], rax
0x180014ac9  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180014ace  mov     r9d, edi
0x180014ad1  mov     edx, 0E0h
0x180014ad6  jmp     loc_18001493C
0x180014adb  mov     rdx, [rbp+lpValueName]; lpValueName
0x180014adf  lea     rax, [rbp+cbData]
0x180014ae3  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180014ae8  lea     r9, [rbp+Type]; lpType
0x180014aec  xor     r8d, r8d; lpReserved
0x180014aef  mov     [rsp+80h+phkResult], rbx; lpData
0x180014af4  mov     rcx, r12; hKey
0x180014af7  call    cs:__imp_RegQueryValueExW
0x180014afd  mov     edi, eax
0x180014aff  cmp     eax, 2
0x180014b02  jnz     short loc_180014B40
0x180014b04  mov     rcx, [rbp+hKey]; hKey
0x180014b08  test    rcx, rcx
0x180014b0b  jz      short loc_180014B36
0x180014b0d  mov     r8, 0FFFFFFFF80000000h
0x180014b14  mov     rax, rcx
0x180014b17  and     rax, r8
0x180014b1a  cmp     rax, r8
0x180014b1d  jz      short loc_180014B36
0x180014b1f  call    cs:__imp_RegCloseKey
0x180014b25  test    eax, eax
0x180014b27  jz      short loc_180014B36
0x180014b29  call    cs:__imp_GetLastError
0x180014b2f  mov     ecx, 7
0x180014b34  int     29h; Win8: RtlFailFast(ecx)
0x180014b36  mov     eax, 80070002h
0x180014b3b  jmp     loc_1800148C7
0x180014b40  test    edi, edi
0x180014b42  jz      loc_180014A0D
0x180014b48  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rbx; LogAdapter::Logger * LogAdapter::g_Logger
0x180014b4f  jz      short loc_180014B8E
0x180014b51  lea     r9, [rbp+lpValueName]
0x180014b55  lea     r8, aFailedToQueryV; "Failed to query value to get type and s"...
0x180014b5c  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180014b61  test    edi, edi
0x180014b63  jg      short loc_180014B69
0x180014b65  mov     eax, edi
0x180014b67  jmp     short loc_180014B71
0x180014b69  movzx   eax, di
0x180014b6c  or      eax, 80070000h
0x180014b71  mov     dword ptr [rbp+var_50], eax
0x180014b74  lea     r9, [rbp+var_48]
0x180014b78  lea     rax, [rbp+var_50]
0x180014b7c  mov     edx, esi
0x180014b7e  lea     r8, a0; ": {0}"
0x180014b85  mov     [rbp+var_48], rax
0x180014b89  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180014b8e  mov     r9d, edi
0x180014b91  mov     edx, 0F0h
0x180014b96  jmp     loc_18001493C
0x180014b9b  test    r15d, r15d
0x180014b9e  jnz     loc_180014C8E
0x180014ba4  mov     ebx, [rbp+cbData]
0x180014ba7  mov     rcx, r14
0x180014baa  shr     rbx, 1
0x180014bad  add     rbx, 2
0x180014bb1  mov     rdx, rbx
0x180014bb4  call    SczAlloc
0x180014bb9  mov     edi, eax
0x180014bbb  test    eax, eax
0x180014bbd  jns     short loc_180014C0F
0x180014bbf  mov     rcx, [rbp+38h]; this
0x180014bc3  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x180014bca  mov     r9d, eax; char *
0x180014bcd  mov     edx, 0FFh; void *
0x180014bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014bd7  mov     rcx, [rbp+hKey]; hKey
0x180014bdb  test    rcx, rcx
0x180014bde  jz      short loc_180014C08
0x180014be0  mov     r8, 0FFFFFFFF80000000h
0x180014be7  mov     rax, rcx
0x180014bea  and     rax, r8
0x180014bed  cmp     rax, r8
0x180014bf0  jz      short loc_180014C08
0x180014bf2  call    cs:__imp_RegCloseKey
0x180014bf8  test    eax, eax
0x180014bfa  jz      short loc_180014C08
0x180014bfc  call    cs:__imp_GetLastError
0x180014c02  lea     ecx, [r15+7]
0x180014c06  int     29h; Win8: RtlFailFast(ecx)
0x180014c08  mov     eax, edi
0x180014c0a  jmp     loc_1800148C7
0x180014c0f  mov     rdx, [rbp+lpValueName]; lpValueName
0x180014c13  lea     rax, [rbp+cbData]
0x180014c17  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180014c1c  lea     r9, [rbp+Type]; lpType
0x180014c20  mov     rax, [r14]
0x180014c23  xor     r8d, r8d; lpReserved
0x180014c26  mov     rcx, r12; hKey
0x180014c29  mov     [rsp+80h+phkResult], rax; lpData
  ... truncated ...
```
