# DirectoryFromPath

- ea: `0x1800138a0`
- end: `0x180013b24`
- name: `DirectoryFromPath`
- size: `644`
- prototype: `__int64 __fastcall(wchar_t *, wchar_t **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800048bc`
- `0x180011e10`

## callees

- `0x180001de0`
- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18000f270`
- `0x18001029c`
- `0x1800138a0`
- `0x18001b7b0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180013990`
- `msvcrt!wcsrchr` at `0x180013990`

## string_xrefs

- `0x180013a49`: `Failed to copy source string to destination`
- `0x1800138f3`: `No path specified`
- `0x180013944`: `No directory result specified`
- `0x180013aba`: `Invalid path.`

## pseudocode

```c
__int64 __fastcall DirectoryFromPath(wchar_t *a1, wchar_t **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  wchar_t *v7; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // r14
  int v10; // eax
  wchar_t *v11; // rbx
  unsigned __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // r14d
  __int64 v15; // rcx
  __int64 v17; // rcx
  wchar_t **v18; // [rsp+20h] [rbp-20h] BYREF
  wchar_t *v19; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  if ( !a1 )
  {
    v4 = -2147024809;
    LODWORD(v19) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path specified");
      v18 = &v19;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v5,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v18);
    }
    v6 = 38;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v4);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    LODWORD(v19) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No directory result specified");
      v18 = &v19;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v19,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v18);
    }
    v6 = 39;
    goto LABEL_28;
  }
  if ( *a2 )
  {
    operator delete(*a2 - 4);
    *a2 = 0;
  }
  v7 = wcsrchr(a1, 0x5Cu);
  if ( !v7 || v7 == a1 )
  {
    v4 = -2147024809;
    LODWORD(v19) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid path.");
      v18 = &v19;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v17,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v18);
    }
    v6 = 46;
    goto LABEL_28;
  }
  v19 = 0;
  v8 = v7 - a1;
  v9 = v8 + 1;
  v10 = SczAlloc(&v19, v8 + 3);
  v4 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v10);
    if ( v19 )
      operator delete(v19 - 4);
    return v4;
  }
  v11 = v19;
  if ( !v19 )
    goto LABEL_24;
  v12 = -1;
  do
    ++v12;
  while ( a1[v12] );
  if ( v9 <= v12 && (v13 = StringCchCopyNW(v19, v9 + 2, a1, v9), v14 = v13, v13 < 0) )
  {
    LODWORD(v19) = v13;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy source string to destination");
      v18 = &v19;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v15,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v18);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v14);
    operator delete(v11 - 4);
    return v14;
  }
  else
  {
LABEL_24:
    *a2 = v11;
    return 0;
  }
}

```

## disassembly

```asm
0x1800138a0  mov     [rsp-28h+arg_10], rbx
0x1800138a5  mov     [rsp-28h+arg_18], rsi
0x1800138aa  push    rbp
0x1800138ab  push    rdi
0x1800138ac  push    r12
0x1800138ae  push    r14
0x1800138b0  push    r15
0x1800138b2  mov     rbp, rsp
0x1800138b5  sub     rsp, 40h
0x1800138b9  mov     rax, cs:__security_cookie
0x1800138c0  xor     rax, rsp
0x1800138c3  mov     [rbp+var_10], rax
0x1800138c7  xor     r12d, r12d
0x1800138ca  mov     rsi, rdx
0x1800138cd  mov     rdi, rcx
0x1800138d0  test    rcx, rcx
0x1800138d3  jnz     short loc_180013923
0x1800138d5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800138dc  mov     ebx, 80070057h
0x1800138e1  mov     dword ptr [rbp+var_18], ebx
0x1800138e4  test    rcx, rcx
0x1800138e7  jz      short loc_180013919
0x1800138e9  lea     edi, [r12+3]
0x1800138ee  xor     edx, edx
0x1800138f0  mov     r8d, edi
0x1800138f3  lea     r9, aNoPathSpecifie; "No path specified"
0x1800138fa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800138ff  lea     rax, [rbp+var_18]
0x180013903  mov     edx, edi
0x180013905  lea     r9, [rbp+var_20]
0x180013909  mov     [rbp+var_20], rax
0x18001390d  lea     r8, asc_1800233AC; ": {}"
0x180013914  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013919  mov     edx, 26h ; '&'
0x18001391e  jmp     loc_180013AEA
0x180013923  test    rsi, rsi
0x180013926  jnz     short loc_180013974
0x180013928  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001392f  mov     ebx, 80004003h
0x180013934  mov     dword ptr [rbp+var_18], ebx
0x180013937  test    rcx, rcx
0x18001393a  jz      short loc_18001396A
0x18001393c  lea     edi, [rsi+3]
0x18001393f  xor     edx, edx
0x180013941  mov     r8d, edi
0x180013944  lea     r9, aNoDirectoryRes; "No directory result specified"
0x18001394b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180013950  lea     rcx, [rbp+var_18]
0x180013954  mov     edx, edi
0x180013956  lea     r9, [rbp+var_20]
0x18001395a  mov     [rbp+var_20], rcx
0x18001395e  lea     r8, asc_1800233AC; ": {}"
0x180013965  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001396a  mov     edx, 27h ; '''
0x18001396f  jmp     loc_180013AEA
0x180013974  mov     rcx, [rdx]
0x180013977  test    rcx, rcx
0x18001397a  jz      short loc_180013988
0x18001397c  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180013980  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013985  mov     [rsi], r12
0x180013988  mov     edx, 5Ch ; '\'; Ch
0x18001398d  mov     rcx, rdi; Str
0x180013990  call    cs:__imp_wcsrchr
0x180013996  test    rax, rax
0x180013999  jz      loc_180013AA1
0x18001399f  cmp     rax, rdi
0x1800139a2  jz      loc_180013AA1
0x1800139a8  sub     rax, rdi
0x1800139ab  mov     [rbp+var_18], r12
0x1800139af  sar     rax, 1
0x1800139b2  lea     rcx, [rbp+var_18]
0x1800139b6  lea     r14, [rax+1]
0x1800139ba  lea     rdx, [r14+2]
0x1800139be  call    SczAlloc
0x1800139c3  mov     ebx, eax
0x1800139c5  test    eax, eax
0x1800139c7  jns     short loc_1800139FC
0x1800139c9  mov     rcx, [rbp+28h]; this
0x1800139cd  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800139d4  mov     r9d, eax; char *
0x1800139d7  mov     edx, 34h ; '4'; void *
0x1800139dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800139e1  mov     rcx, [rbp+var_18]
0x1800139e5  test    rcx, rcx
0x1800139e8  jz      loc_180013AFD
0x1800139ee  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800139f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800139f7  jmp     loc_180013AFD
0x1800139fc  mov     rbx, [rbp+var_18]
0x180013a00  test    rbx, rbx
0x180013a03  jz      loc_180013A9A
0x180013a09  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013a0d  inc     rax
0x180013a10  cmp     [rdi+rax*2], r12w
0x180013a15  jnz     short loc_180013A0D
0x180013a17  cmp     r14, rax
0x180013a1a  ja      short loc_180013A9A
0x180013a1c  mov     r9, r14; unsigned __int64
0x180013a1f  lea     rdx, [r14+2]; unsigned __int64
0x180013a23  mov     r8, rdi; wchar_t *
0x180013a26  mov     rcx, rbx; wchar_t *
0x180013a29  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x180013a2e  mov     r14d, eax
0x180013a31  test    eax, eax
0x180013a33  jns     short loc_180013A9A
0x180013a35  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180013a3c  mov     dword ptr [rbp+var_18], eax
0x180013a3f  test    rcx, rcx
0x180013a42  jz      short loc_180013A74
0x180013a44  mov     edi, 3
0x180013a49  lea     r9, aFailedToCopySo; "Failed to copy source string to destina"...
0x180013a50  mov     r8d, edi
0x180013a53  xor     edx, edx
0x180013a55  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180013a5a  lea     rax, [rbp+var_18]
0x180013a5e  mov     edx, edi
0x180013a60  lea     r9, [rbp+var_20]
0x180013a64  mov     [rbp+var_20], rax
0x180013a68  lea     r8, asc_1800233AC; ": {}"
0x180013a6f  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013a74  mov     rcx, [rbp+28h]; this
0x180013a78  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180013a7f  mov     r9d, r14d; char *
0x180013a82  mov     edx, 3Bh ; ';'; void *
0x180013a87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013a8c  lea     rcx, [rbx-8]; Block
0x180013a90  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013a95  mov     eax, r14d
0x180013a98  jmp     short loc_180013AFF
0x180013a9a  mov     [rsi], rbx
0x180013a9d  xor     eax, eax
0x180013a9f  jmp     short loc_180013AFF
0x180013aa1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180013aa8  mov     ebx, 80070057h
0x180013aad  mov     dword ptr [rbp+var_18], ebx
0x180013ab0  test    rcx, rcx
0x180013ab3  jz      short loc_180013AE5
0x180013ab5  mov     edi, 3
0x180013aba  lea     r9, aInvalidPath; "Invalid path."
0x180013ac1  mov     r8d, edi
0x180013ac4  xor     edx, edx
0x180013ac6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180013acb  lea     rax, [rbp+var_18]
0x180013acf  mov     edx, edi
0x180013ad1  lea     r9, [rbp+var_20]
0x180013ad5  mov     [rbp+var_20], rax
0x180013ad9  lea     r8, asc_1800233AC; ": {}"
0x180013ae0  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013ae5  mov     edx, 2Eh ; '.'; void *
0x180013aea  mov     rcx, [rbp+28h]; this
0x180013aee  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180013af5  mov     r9d, ebx; char *
0x180013af8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013afd  mov     eax, ebx
0x180013aff  mov     rcx, [rbp+var_10]
0x180013b03  xor     rcx, rsp; StackCookie
0x180013b06  call    __security_check_cookie
0x180013b0b  lea     r11, [rsp+40h+var_s0]
0x180013b10  mov     rbx, [r11+40h]
0x180013b14  mov     rsi, [r11+48h]
0x180013b18  mov     rsp, r11
0x180013b1b  pop     r15
0x180013b1d  pop     r14
0x180013b1f  pop     r12
0x180013b21  pop     rdi
0x180013b22  pop     rbp
0x180013b23  retn
```
