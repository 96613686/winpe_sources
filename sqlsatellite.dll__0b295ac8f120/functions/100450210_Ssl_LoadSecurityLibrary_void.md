# Ssl::LoadSecurityLibrary(void)

- ea: `0x100450210`
- end: `0x100450536`
- name: `?LoadSecurityLibrary@Ssl@@CAKXZ`
- size: `806`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10044f2e0`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100450210`
- `0x100486af0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1004503a3`
- `KERNEL32!FreeLibrary` at `0x10045044a`
- `KERNEL32!FreeLibrary` at `0x1004503a3`
- `KERNEL32!FreeLibrary` at `0x10045044a`
- `KERNEL32!SetLastError` at `0x1004502a8`
- `KERNEL32!SetLastError` at `0x1004502a8`
- `KERNEL32!GetProcAddress` at `0x100450385`
- `KERNEL32!GetProcAddress` at `0x100450385`
- `KERNEL32!GetLastError` at `0x1004502fe`
- `KERNEL32!GetLastError` at `0x100450394`
- `KERNEL32!GetLastError` at `0x10045043b`
- `KERNEL32!GetLastError` at `0x1004502fe`
- `KERNEL32!GetLastError` at `0x100450394`
- `KERNEL32!GetLastError` at `0x10045043b`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x1004502ec`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x1004502ec`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1004502d7`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1004502d7`

## string_xrefs

- `0x10045037b`: `InitSecurityInterfaceW`
- `0x100450284`: `secforwarder.dll`
- `0x1004502ce`: `secforwarder.dll`
- `0x10045023e`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10045024a`: `Ssl::LoadSecurityLibrary`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Ssl::LoadSecurityLibrary(void)
{
  __int64 v0; // rcx
  const char *v1; // rax
  HMODULE v2; // rax
  DWORD LastError; // eax
  DWORD v4; // ebx
  const wchar_t *v5; // r9
  __int64 (*ProcAddress)(void); // rax
  __int64 v8; // [rsp+20h] [rbp-268h]
  wchar_t v9[264]; // [rsp+60h] [rbp-228h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::LoadSecurityLibrary", 3908, L"API|SNI\n");
  v0 = 261;
  v1 = "secforwarder.dll";
  while ( *v1 )
  {
    ++v1;
    if ( !--v0 )
    {
      SetLastError(0x7Bu);
      Ssl::s_hSecurity = 0;
LABEL_8:
      LastError = GetLastError();
      v4 = LastError;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v8) = 6;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::LoadSecurityLibrary",
          3922,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v8,
          0,
          LastError);
      }
      SNISetLastError(6u, v4, 0xC3B4u);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v8) = v4;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::LoadSecurityLibrary",
          3924,
          L"RET|SNI%d{WINERR}\n",
          v8);
      }
      goto LABEL_25;
    }
  }
  FastDBCSToUnicode(0, "secforwarder.dll", -1, v9, 261);
  v2 = SOS_OS::SOSLoadLibraryW(v9, 1, 0, 0);
  Ssl::s_hSecurity = v2;
  if ( !v2 )
    goto LABEL_8;
  ProcAddress = GetProcAddress(v2, "InitSecurityInterfaceW");
  if ( ProcAddress )
  {
    Ssl::s_pfTable = (struct _SECURITY_FUNCTION_TABLE_W *)ProcAddress();
    if ( Ssl::s_pfTable )
    {
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::LoadSecurityLibrary",
          3963,
          L"RET|SNI%d{WINERR}\n",
          0);
      v4 = 0;
    }
    else
    {
      v4 = GetLastError();
      FreeLibrary(Ssl::s_hSecurity);
      Ssl::s_hSecurity = 0;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v8) = 6;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::LoadSecurityLibrary",
          3956,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v8,
          0,
          v4);
      }
      SNISetLastError(6u, v4, 0xC3B4u);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v8) = v4;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::LoadSecurityLibrary",
          3958,
          L"RET|SNI%d{WINERR}\n",
          v8);
      }
    }
  }
  else
  {
    v4 = GetLastError();
    FreeLibrary(Ssl::s_hSecurity);
    Ssl::s_hSecurity = 0;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v8) = 6;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::LoadSecurityLibrary",
        3941,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v8,
        0,
        v4);
    }
    SNISetLastError(6u, v4, 0xC3B4u);
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v8) = v4;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::LoadSecurityLibrary",
        3943,
        L"RET|SNI%d{WINERR}\n",
        v8);
    }
  }
LABEL_25:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::LoadSecurityLibrary", 3908, v5);
  return v4;
}

```

## disassembly

```asm
0x100450210  mov     rax, rsp
0x100450213  push    rdi
0x100450214  sub     rsp, 280h
0x10045021b  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x100450224  mov     [rax+8], rbx
0x100450228  mov     [rax+10h], rsi
0x10045022c  mov     rax, cs:__security_cookie
0x100450233  xor     rax, rsp
0x100450236  mov     [rsp+288h+var_18], rax
0x10045023e  lea     rdi, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x100450245  mov     [rsp+288h+var_240], rdi
0x10045024a  lea     rsi, aSslLoadsecurit; "Ssl::LoadSecurityLibrary"
0x100450251  mov     [rsp+288h+var_238], rsi
0x100450256  mov     [rsp+288h+var_230], 0F44h
0x10045025e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100450265  jz      short loc_10045027F
0x100450267  lea     r9, aApiSni_0; "API|SNI\n"
0x10045026e  mov     r8d, 0F44h; int
0x100450274  mov     rdx, rsi; char *
0x100450277  mov     rcx, rdi; char *
0x10045027a  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10045027f  mov     ecx, 105h
0x100450284  lea     rax, aSecforwarderDl; "secforwarder.dll"
0x10045028b  nop     dword ptr [rax+rax+00h]
0x100450290  cmp     byte ptr [rax], 0
0x100450293  jz      short loc_1004502BB
0x100450295  inc     rax
0x100450298  sub     rcx, 1
0x10045029c  jnz     short loc_100450290
0x10045029e  test    rcx, rcx
0x1004502a1  jnz     short loc_1004502BB
0x1004502a3  mov     ecx, 7Bh ; '{'; dwErrCode
0x1004502a8  call    cs:__imp_SetLastError
0x1004502ae  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Ssl::s_hSecurity
0x1004502b9  jmp     short loc_1004502FE
0x1004502bb  mov     dword ptr [rsp+288h+var_268], 105h
0x1004502c3  lea     r9, [rsp+288h+var_228]
0x1004502c8  mov     r8d, 0FFFFFFFFh
0x1004502ce  lea     rdx, aSecforwarderDl; "secforwarder.dll"
0x1004502d5  xor     ecx, ecx
0x1004502d7  call    cs:__imp_?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x1004502dd  xor     r9d, r9d
0x1004502e0  xor     r8d, r8d
0x1004502e3  lea     edx, [r9+1]
0x1004502e7  lea     rcx, [rsp+288h+var_228]
0x1004502ec  call    cs:__imp_?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z; SOS_OS::SOSLoadLibraryW(wchar_t const *,int,wchar_t const *,int)
0x1004502f2  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Ssl::s_hSecurity
0x1004502f9  test    rax, rax
0x1004502fc  jnz     short loc_10045037B
0x1004502fe  call    cs:__imp_GetLastError
0x100450304  mov     ebx, eax
0x100450306  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045030d  jz      short loc_10045033B
0x10045030f  mov     [rsp+288h+var_258], eax
0x100450313  mov     [rsp+288h+var_260], 0
0x10045031b  mov     dword ptr [rsp+288h+var_268], 6
0x100450323  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10045032a  mov     r8d, 0F52h; int
0x100450330  mov     rdx, rsi; char *
0x100450333  mov     rcx, rdi; char *
0x100450336  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10045033b  mov     r8d, 0C3B4h
0x100450341  mov     edx, ebx
0x100450343  mov     ecx, 6
0x100450348  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10045034d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100450354  jz      loc_1004504F5
0x10045035a  mov     dword ptr [rsp+288h+var_268], ebx
0x10045035e  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100450365  mov     r8d, 0F54h; int
0x10045036b  mov     rdx, rsi; char *
0x10045036e  mov     rcx, rdi; char *
0x100450371  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100450376  jmp     loc_1004504F5
0x10045037b  lea     rdx, aInitsecurityin; "InitSecurityInterfaceW"
0x100450382  mov     rcx, rax; hModule
0x100450385  call    cs:__imp_GetProcAddress
0x10045038b  test    rax, rax
0x10045038e  jnz     loc_100450429
0x100450394  call    cs:__imp_GetLastError
0x10045039a  mov     ebx, eax
0x10045039c  mov     rcx, cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA; hLibModule
0x1004503a3  call    cs:__imp_FreeLibrary
0x1004503a9  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Ssl::s_hSecurity
0x1004503b4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004503bb  jz      short loc_1004503E9
0x1004503bd  mov     [rsp+288h+var_258], ebx
0x1004503c1  mov     [rsp+288h+var_260], 0
0x1004503c9  mov     dword ptr [rsp+288h+var_268], 6
0x1004503d1  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004503d8  mov     r8d, 0F65h; int
0x1004503de  mov     rdx, rsi; char *
0x1004503e1  mov     rcx, rdi; char *
0x1004503e4  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004503e9  mov     r8d, 0C3B4h
0x1004503ef  mov     edx, ebx
0x1004503f1  mov     ecx, 6
0x1004503f6  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004503fb  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100450402  jz      loc_1004504F5
0x100450408  mov     dword ptr [rsp+288h+var_268], ebx
0x10045040c  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100450413  mov     r8d, 0F67h; int
0x100450419  mov     rdx, rsi; char *
0x10045041c  mov     rcx, rdi; char *
0x10045041f  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100450424  jmp     loc_1004504F5
0x100450429  call    rax
0x10045042b  mov     cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA, rax; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x100450432  test    rax, rax
0x100450435  jnz     loc_1004504C9
0x10045043b  call    cs:__imp_GetLastError
0x100450441  mov     ebx, eax
0x100450443  mov     rcx, cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA; hLibModule
0x10045044a  call    cs:__imp_FreeLibrary
0x100450450  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Ssl::s_hSecurity
0x10045045b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100450462  jz      short loc_100450490
0x100450464  mov     [rsp+288h+var_258], ebx
0x100450468  mov     [rsp+288h+var_260], 0
0x100450470  mov     dword ptr [rsp+288h+var_268], 6
0x100450478  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10045047f  mov     r8d, 0F74h; int
0x100450485  mov     rdx, rsi; char *
0x100450488  mov     rcx, rdi; char *
0x10045048b  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100450490  mov     r8d, 0C3B4h
0x100450496  mov     edx, ebx
0x100450498  mov     ecx, 6
0x10045049d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004504a2  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004504a9  jz      short loc_1004504F5
0x1004504ab  mov     dword ptr [rsp+288h+var_268], ebx
0x1004504af  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004504b6  mov     r8d, 0F76h; int
0x1004504bc  mov     rdx, rsi; char *
0x1004504bf  mov     rcx, rdi; char *
0x1004504c2  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004504c7  jmp     short loc_1004504F5
0x1004504c9  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004504d0  jz      short loc_1004504F3
0x1004504d2  mov     [rsp+288h+var_268], 0
0x1004504db  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004504e2  mov     r8d, 0F7Bh; int
0x1004504e8  mov     rdx, rsi; char *
0x1004504eb  mov     rcx, rdi; char *
0x1004504ee  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004504f3  xor     ebx, ebx
0x1004504f5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004504fc  jz      short loc_10045050F
0x1004504fe  mov     r8d, 0F44h; int
0x100450504  mov     rdx, rsi; char *
0x100450507  mov     rcx, rdi; char *
0x10045050a  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10045050f  mov     eax, ebx
0x100450511  mov     rcx, [rsp+288h+var_18]
0x100450519  xor     rcx, rsp; StackCookie
0x10045051c  call    __security_check_cookie
0x100450521  lea     r11, [rsp+288h+var_8]
0x100450529  mov     rbx, [r11+10h]
0x10045052d  mov     rsi, [r11+18h]
0x100450531  mov     rsp, r11
0x100450534  pop     rdi
0x100450535  retn
```
