# RecursivelyCreateDirectory

- ea: `0x180014054`
- end: `0x180014469`
- name: `RecursivelyCreateDirectory`
- size: `1045`
- prototype: `__int64 __fastcall(__int64, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011e10`
- `0x180014054`

## callees

- `0x180001de0`
- `0x180001dec`
- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18000f270`
- `0x180010de4`
- `0x1800118a4`
- `0x1800134c0`
- `0x18001387c`
- `0x180014054`
- `0x180014f38`
- `0x18001ad50`
- `0x18001b048`
- `0x18001b7b0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180014266`
- `msvcrt!wcsrchr` at `0x180014266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001424d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001424d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014405`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001423f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800143fb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001423f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800143fb`

## string_xrefs

- `0x1800140b0`: `No path specified`
- `0x1800141e1`: `Failed calling GetSystemSecurity`
- `0x180014289`: `Cannot find parent for path: {}.`
- `0x180014352`: `Failed to copy parent of path: {}`
- `0x1800143c5`: `Failed to create path: {}`

## pseudocode

```c
__int64 __fastcall RecursivelyCreateDirectory(__int64 a1, struct _SECURITY_ATTRIBUTES *a2)
{
  int v3; // ebx
  __int64 v5; // rdx
  bool *v6; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v8; // rdx
  unsigned int v9; // r8d
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  int SystemSecurity; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  wchar_t *v19; // rbx
  wchar_t *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // edi
  __int64 v24; // rcx
  __int64 v25; // rdx
  unsigned __int64 v26; // rdi
  unsigned __int64 v27; // r15
  wchar_t *v28; // rax
  wchar_t *v29; // rsi
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rdx
  int Directory; // eax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rcx
  signed int LastError; // eax
  int v40; // [rsp+20h] [rbp-60h] BYREF
  LPCWSTR lpPathName; // [rsp+28h] [rbp-58h] BYREF
  wchar_t *v42; // [rsp+30h] [rbp-50h] BYREF
  __int128 v43; // [rsp+38h] [rbp-48h]
  __int64 v44; // [rsp+48h] [rbp-38h]
  __int64 v45; // [rsp+50h] [rbp-30h] BYREF
  __int64 v46; // [rsp+58h] [rbp-28h] BYREF
  __int128 v47; // [rsp+60h] [rbp-20h] BYREF
  __int64 v48; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v45 = a1;
  v48 = 0;
  lpPathName = 0;
  v47 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    LODWORD(v46) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path specified");
      lpPathName = (LPCWSTR)&v46;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v46,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&lpPathName);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL);
    return (unsigned int)v3;
  }
  v3 = SczAllocFromSz(&lpPathName, a1);
  if ( v3 < 0 )
  {
    v5 = 360;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v3);
    goto LABEL_9;
  }
  v3 = PathPrefix((_WORD **)&lpPathName);
  if ( v3 < 0 )
  {
    v5 = 361;
    goto LABEL_8;
  }
  if ( !a2 )
  {
    LOBYTE(v40) = 0;
    CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                          (Windows::WCP::Implementation::Rtl *)&v40,
                          v6);
    v10 = CanSetSystemOwner;
    if ( CanSetSystemOwner < 0 )
    {
      LODWORD(v46) = CanSetSystemOwner;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling CanSetSystemOwner");
        v42 = (wchar_t *)&v46;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(v12, v11, v13, &v42);
      }
      v14 = 367;
LABEL_18:
      v3 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)v14, v9, (const char *)v10, v40);
LABEL_9:
      if ( lpPathName )
        operator delete((void *)(lpPathName - 4));
      return (unsigned int)v3;
    }
    if ( (_BYTE)v40 )
    {
      v46 = 0;
      SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                         (Windows::WCP::Implementation::Rtl *)&v46,
                         v8);
      v10 = SystemSecurity;
      if ( SystemSecurity < 0 )
      {
        LODWORD(v46) = SystemSecurity;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling GetSystemSecurity");
          v42 = (wchar_t *)&v46;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(v17, v16, v18, &v42);
        }
        v14 = 373;
        goto LABEL_18;
      }
      a2 = (struct _SECURITY_ATTRIBUTES *)&v47;
      *((_QWORD *)&v43 + 1) = v46;
      *(_QWORD *)&v43 = 24;
      v44 = 0;
      v48 = 0;
      v47 = v43;
    }
  }
  v19 = (wchar_t *)lpPathName;
  if ( !CreateDirectoryW(lpPathName, a2) && GetLastError() != 183 )
  {
    v20 = wcsrchr(v19, 0x5Cu);
    if ( !v20 )
    {
      v23 = -2147024893;
      LODWORD(v46) = -2147024893;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<wchar_t const *>(
          v22,
          v21,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Cannot find parent for path: {}.",
          (__int64)&v45);
        v42 = (wchar_t *)&v46;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v24,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v42);
      }
      v25 = 392;
      goto LABEL_31;
    }
    v26 = v20 - v19;
    v27 = -1;
    v28 = (wchar_t *)operator new[](saturated_mul(v26 + 1, 2u));
    v29 = v28;
    if ( !v28 )
    {
      v23 = -2147024882;
      v25 = 399;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
        (const char *)v23);
LABEL_32:
      if ( v19 )
        operator delete(v19 - 4);
      return v23;
    }
    do
      ++v27;
    while ( v19[v27] );
    if ( v26 <= v27 )
    {
      v30 = StringCchCopyNW(v28, v26 + 1, v19, v26);
      v23 = v30;
      if ( v30 < 0 )
      {
        LODWORD(v46) = v30;
        if ( LogAdapter::g_Logger )
        {
          v42 = v19;
          LogAdapter::Logger::LogPartial<wchar_t const *>(
            v32,
            v31,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy parent of path: {}",
            (__int64)&v42);
          lpPathName = (LPCWSTR)&v46;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            v33,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&lpPathName);
        }
        v34 = 406;
LABEL_43:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)v23);
LABEL_44:
        operator delete(v29);
        goto LABEL_32;
      }
    }
    Directory = RecursivelyCreateDirectory(v29, a2);
    v23 = Directory;
    if ( Directory < 0 )
    {
      LODWORD(v46) = Directory;
      if ( LogAdapter::g_Logger )
      {
        v42 = v29;
        LogAdapter::Logger::LogPartial<wchar_t const *>(
          v37,
          v36,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create path: {}",
          (__int64)&v42);
        lpPathName = (LPCWSTR)&v46;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v38,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&lpPathName);
      }
      v34 = 408;
      goto LABEL_43;
    }
    if ( !CreateDirectoryW(v19, a2) )
    {
      LastError = GetLastError();
      v23 = LastError;
      if ( LastError != 183 )
      {
        if ( LastError > 0 )
          v23 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_44;
      }
    }
    operator delete(v29);
  }
  if ( v19 )
    operator delete(v19 - 4);
  return 0;
}

```

## disassembly

```asm
0x180014054  mov     [rsp-38h+arg_10], rbx
0x180014059  push    rbp
0x18001405a  push    rsi
0x18001405b  push    rdi
0x18001405c  push    r12
0x18001405e  push    r13
0x180014060  push    r14
0x180014062  push    r15
0x180014064  mov     rbp, rsp
0x180014067  sub     rsp, 80h
0x18001406e  mov     rax, cs:__security_cookie
0x180014075  xor     rax, rsp
0x180014078  mov     [rbp+var_8], rax
0x18001407c  xor     eax, eax
0x18001407e  mov     [rbp+var_30], rcx
0x180014082  xor     r13d, r13d
0x180014085  mov     [rbp+var_10], rax
0x180014089  mov     [rbp+lpPathName], r13
0x18001408d  xorps   xmm0, xmm0
0x180014090  mov     r14, rdx
0x180014093  movups  [rbp+var_20], xmm0
0x180014097  test    rcx, rcx
0x18001409a  jnz     short loc_1800140FD
0x18001409c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800140a3  mov     ebx, 80070057h
0x1800140a8  mov     dword ptr [rbp+var_28], ebx
0x1800140ab  test    rcx, rcx
0x1800140ae  jz      short loc_1800140DE
0x1800140b0  lea     r9, aNoPathSpecifie; "No path specified"
0x1800140b7  xor     edx, edx
0x1800140b9  lea     r8d, [rax+3]
0x1800140bd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800140c2  lea     rcx, [rbp+var_28]
0x1800140c6  lea     r9, [rbp+lpPathName]
0x1800140ca  mov     [rbp+lpPathName], rcx
0x1800140ce  lea     r8, asc_1800233AC; ": {}"
0x1800140d5  lea     edx, [r13+3]
0x1800140d9  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800140de  mov     rcx, [rbp+38h]; this
0x1800140e2  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800140e9  mov     r9d, ebx; char *
0x1800140ec  mov     edx, 163h; void *
0x1800140f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800140f6  mov     eax, ebx
0x1800140f8  jmp     loc_180014442
0x1800140fd  mov     rdx, rcx
0x180014100  lea     rcx, [rbp+lpPathName]
0x180014104  call    SczAllocFromSz
0x180014109  mov     ebx, eax
0x18001410b  test    eax, eax
0x18001410d  jns     short loc_18001413B
0x18001410f  mov     edx, 168h; void *
0x180014114  mov     rcx, [rbp+38h]; this
0x180014118  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18001411f  mov     r9d, ebx; char *
0x180014122  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014127  mov     rcx, [rbp+lpPathName]
0x18001412b  test    rcx, rcx
0x18001412e  jz      short loc_1800140F6
0x180014130  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180014134  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014139  jmp     short loc_1800140F6
0x18001413b  lea     rcx, [rbp+lpPathName]
0x18001413f  call    PathPrefix
0x180014144  mov     ebx, eax
0x180014146  test    eax, eax
0x180014148  jns     short loc_180014151
0x18001414a  mov     edx, 169h
0x18001414f  jmp     short loc_180014114
0x180014151  test    r14, r14
0x180014154  jnz     loc_180014235
0x18001415a  lea     rcx, [rbp+var_60]; this
0x18001415e  mov     byte ptr [rbp+var_60], r13b
0x180014162  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x180014167  mov     ebx, eax
0x180014169  test    eax, eax
0x18001416b  jns     short loc_1800141B7
0x18001416d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180014174  mov     dword ptr [rbp+var_28], eax
0x180014177  test    rcx, rcx
0x18001417a  jz      short loc_18001419F
0x18001417c  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x180014183  xor     edx, edx
0x180014185  lea     r8d, [r14+3]
0x180014189  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001418e  lea     rax, [rbp+var_28]
0x180014192  lea     r9, [rbp+var_50]
0x180014196  mov     [rbp+var_50], rax
0x18001419a  call    ??$Log@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18001419f  mov     edx, 16Fh; void *
0x1800141a4  mov     rcx, [rbp+38h]; this
0x1800141a8  mov     r9d, ebx; char *
0x1800141ab  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800141b0  mov     ebx, eax
0x1800141b2  jmp     loc_180014127
0x1800141b7  cmp     byte ptr [rbp+var_60], r13b
0x1800141bb  jz      short loc_180014235
0x1800141bd  lea     rcx, [rbp+var_28]; this
0x1800141c1  mov     [rbp+var_28], r13
0x1800141c5  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x1800141ca  mov     ebx, eax
0x1800141cc  test    eax, eax
0x1800141ce  jns     short loc_180014209
0x1800141d0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800141d7  mov     dword ptr [rbp+var_28], eax
0x1800141da  test    rcx, rcx
0x1800141dd  jz      short loc_180014202
0x1800141df  xor     edx, edx
0x1800141e1  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x1800141e8  lea     r8d, [rdx+3]
0x1800141ec  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800141f1  lea     rax, [rbp+var_28]
0x1800141f5  lea     r9, [rbp+var_50]
0x1800141f9  mov     [rbp+var_50], rax
0x1800141fd  call    ??$Log@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x180014202  mov     edx, 175h
0x180014207  jmp     short loc_1800141A4
0x180014209  mov     rax, [rbp+var_28]
0x18001420d  lea     r14, [rbp+var_20]
0x180014211  mov     qword ptr [rbp+var_48+8], rax
0x180014215  xor     eax, eax
0x180014217  mov     qword ptr [rbp+var_48], 18h
0x18001421f  movups  xmm0, [rbp+var_48]
0x180014223  mov     [rbp+var_38], rax
0x180014227  movsd   xmm1, [rbp+var_38]
0x18001422c  movsd   [rbp+var_10], xmm1
0x180014231  movups  [rbp+var_20], xmm0
0x180014235  mov     rbx, [rbp+lpPathName]
0x180014239  mov     rdx, r14; lpSecurityAttributes
0x18001423c  mov     rcx, rbx; lpPathName
0x18001423f  call    cs:__imp_CreateDirectoryW
0x180014245  test    eax, eax
0x180014247  jnz     loc_180014432
0x18001424d  call    cs:__imp_GetLastError
0x180014253  cmp     eax, 0B7h
0x180014258  jz      loc_180014432
0x18001425e  mov     edx, 5Ch ; '\'; Ch
0x180014263  mov     rcx, rbx; Str
0x180014266  call    cs:__imp_wcsrchr
0x18001426c  mov     rdi, rax
0x18001426f  test    rax, rax
0x180014272  jnz     short loc_1800142DF
0x180014274  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, r13; LogAdapter::Logger * LogAdapter::g_Logger
0x18001427b  mov     edi, 80070003h
0x180014280  mov     dword ptr [rbp+var_28], edi
0x180014283  jz      short loc_1800142B2
0x180014285  lea     r9, [rbp+var_30]
0x180014289  lea     r8, aCannotFindPare; "Cannot find parent for path: {}."
0x180014290  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180014295  lea     rax, [rbp+var_28]
0x180014299  mov     edx, 3
0x18001429e  lea     r9, [rbp+var_50]
0x1800142a2  mov     [rbp+var_50], rax
0x1800142a6  lea     r8, asc_1800233AC; ": {}"
0x1800142ad  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800142b2  mov     edx, 188h; void *
0x1800142b7  mov     rcx, [rbp+38h]; this
0x1800142bb  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800142c2  mov     r9d, edi; char *
0x1800142c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800142ca  test    rbx, rbx
0x1800142cd  jz      short loc_1800142D8
0x1800142cf  lea     rcx, [rbx-8]; Block
0x1800142d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800142d8  mov     eax, edi
0x1800142da  jmp     loc_180014442
0x1800142df  sub     rdi, rbx
0x1800142e2  mov     eax, 2
0x1800142e7  sar     rdi, 1
0x1800142ea  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800142f1  lea     r12, [rdi+1]
0x1800142f5  mul     r12
0x1800142f8  cmovb   rax, r15
0x1800142fc  mov     rcx, rax; unsigned __int64
0x1800142ff  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014304  mov     rsi, rax
0x180014307  test    rax, rax
0x18001430a  jnz     short loc_180014318
0x18001430c  mov     edi, 8007000Eh
0x180014311  mov     edx, 18Fh
0x180014316  jmp     short loc_1800142B7
0x180014318  inc     r15
0x18001431b  cmp     [rbx+r15*2], r13w
0x180014320  jnz     short loc_180014318
0x180014322  cmp     rdi, r15
0x180014325  ja      short loc_1800143A0
0x180014327  mov     r9, rdi; unsigned __int64
0x18001432a  mov     r8, rbx; wchar_t *
0x18001432d  mov     rdx, r12; unsigned __int64
0x180014330  mov     rcx, rsi; wchar_t *
0x180014333  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x180014338  mov     edi, eax
0x18001433a  test    eax, eax
0x18001433c  jns     short loc_1800143A0
0x18001433e  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, r13; LogAdapter::Logger * LogAdapter::g_Logger
0x180014345  mov     dword ptr [rbp+var_28], eax
0x180014348  jz      short loc_18001437B
0x18001434a  lea     r9, [rbp+var_50]
0x18001434e  mov     [rbp+var_50], rbx
0x180014352  lea     r8, aFailedToCopyPa; "Failed to copy parent of path: {}"
0x180014359  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18001435e  lea     rax, [rbp+var_28]
0x180014362  mov     edx, 3
0x180014367  lea     r9, [rbp+lpPathName]
0x18001436b  mov     [rbp+lpPathName], rax
0x18001436f  lea     r8, asc_1800233AC; ": {}"
0x180014376  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001437b  mov     edx, 196h; void *
0x180014380  mov     rcx, [rbp+38h]; this
0x180014384  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18001438b  mov     r9d, edi; char *
0x18001438e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014393  mov     rcx, rsi; Block
0x180014396  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001439b  jmp     loc_1800142CA
0x1800143a0  mov     rdx, r14
0x1800143a3  mov     rcx, rsi
0x1800143a6  call    RecursivelyCreateDirectory
0x1800143ab  mov     edi, eax
0x1800143ad  test    eax, eax
0x1800143af  jns     short loc_1800143F5
0x1800143b1  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, r13; LogAdapter::Logger * LogAdapter::g_Logger
0x1800143b8  mov     dword ptr [rbp+var_28], eax
0x1800143bb  jz      short loc_1800143EE
0x1800143bd  lea     r9, [rbp+var_50]
0x1800143c1  mov     [rbp+var_50], rsi
0x1800143c5  lea     r8, aFailedToCreate; "Failed to create path: {}"
0x1800143cc  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800143d1  lea     rax, [rbp+var_28]
0x1800143d5  mov     edx, 3
0x1800143da  lea     r9, [rbp+lpPathName]
0x1800143de  mov     [rbp+lpPathName], rax
0x1800143e2  lea     r8, asc_1800233AC; ": {}"
0x1800143e9  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800143ee  mov     edx, 198h
0x1800143f3  jmp     short loc_180014380
0x1800143f5  mov     rdx, r14; lpSecurityAttributes
0x1800143f8  mov     rcx, rbx; lpPathName
0x1800143fb  call    cs:__imp_CreateDirectoryW
0x180014401  test    eax, eax
0x180014403  jnz     short loc_18001442A
0x180014405  call    cs:__imp_GetLastError
0x18001440b  mov     edi, eax
0x18001440d  cmp     eax, 0B7h
0x180014412  jz      short loc_18001442A
0x180014414  test    eax, eax
0x180014416  jle     loc_180014393
0x18001441c  movzx   edi, ax
0x18001441f  or      edi, 80070000h
0x180014425  jmp     loc_180014393
0x18001442a  mov     rcx, rsi; Block
0x18001442d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014432  test    rbx, rbx
0x180014435  jz      short loc_180014440
0x180014437  lea     rcx, [rbx-8]; Block
0x18001443b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014440  xor     eax, eax
0x180014442  mov     rcx, [rbp+var_8]
0x180014446  xor     rcx, rsp; StackCookie
0x180014449  call    __security_check_cookie
0x18001444e  mov     rbx, [rsp+80h+arg_10]
0x180014456  add     rsp, 80h
0x18001445d  pop     r15
0x18001445f  pop     r14
0x180014461  pop     r13
0x180014463  pop     r12
0x180014465  pop     rdi
0x180014466  pop     rsi
0x180014467  pop     rbp
0x180014468  retn
```
