# SczAllocConcat2Sz

- ea: `0x180010448`
- end: `0x18001074a`
- name: `SczAllocConcat2Sz`
- size: `770`
- prototype: `__int64 __fastcall(const void **, wchar_t *, wchar_t *)`
- caller_count: `6`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180004fd0`
- `0x180005200`
- `0x1800056a0`
- `0x1800067ac`
- `0x180006f84`
- `0x180011e10`

## callees

- `0x180001de0`
- `0x180001dec`
- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18000f1ac`
- `0x180010448`
- `0x180011654`
- `0x18001b762`
- `0x18001b7b0`

## pseudocode

```c
__int64 __fastcall SczAllocConcat2Sz(const void **a1, wchar_t *a2, wchar_t *a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  wchar_t *v11; // rdi
  __int64 v12; // rsi
  unsigned __int64 v13; // r14
  __int64 v14; // rbx
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  _QWORD *v17; // rax
  char *v18; // rbx
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // rcx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rcx
  unsigned __int64 *v25; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int64 v26; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  if ( !a1 )
  {
    v6 = -2147467261;
    LODWORD(v26) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      v25 = &v26;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v26,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v25);
    }
    v7 = 251;
    goto LABEL_5;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    LODWORD(v26) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string to append specified");
      v25 = &v26;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v9,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v25);
    }
    v7 = 252;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    LODWORD(v26) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No second string to append specified");
      v25 = &v26;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v10,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v25);
    }
    v7 = 253;
    goto LABEL_5;
  }
  v11 = (wchar_t *)*a1;
  v12 = -1;
  v26 = 0;
  v13 = 0;
  if ( v11 )
  {
    v6 = SczSize(v11, &v26);
    if ( v6 < 0 )
    {
      v7 = 260;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
        (const char *)(unsigned int)v6);
      return (unsigned int)v6;
    }
    v11 = (wchar_t *)*a1;
    v14 = -1;
    do
      ++v14;
    while ( v11[v14] );
    v13 = v26;
  }
  else
  {
    v14 = 0;
  }
  v15 = -1;
  do
    ++v15;
  while ( a2[v15] );
  do
    ++v12;
  while ( a3[v12] );
  v16 = v14 + v12 + v15 + 1;
  if ( v13 >= v16 )
  {
    v18 = 0;
  }
  else
  {
    v13 = v14 + v12 + v15 + 1;
    v17 = operator new[](2 * v16 + 8);
    if ( !v17 )
    {
      v6 = -2147024882;
      v7 = 271;
      goto LABEL_5;
    }
    *v17 = v13;
    v11 = (wchar_t *)(v17 + 1);
    if ( *a1 )
      memcpy_0(v17 + 1, *a1, 2 * v14 + 2);
    else
      *v11 = 0;
    v18 = (char *)*a1;
    *a1 = v11;
  }
  v19 = StringCchCatW(v11, v13, a2);
  v20 = v19;
  if ( v19 < 0 )
  {
    LODWORD(v26) = v19;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to concat string.");
      v25 = &v26;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v21,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v25);
    }
    v22 = 294;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v20);
    if ( v18 )
      operator delete(v18 - 8);
    return v20;
  }
  v23 = StringCchCatW((wchar_t *)*a1, v13, a3);
  v20 = v23;
  if ( v23 < 0 )
  {
    LODWORD(v26) = v23;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to concat second string.");
      v25 = &v26;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v24,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v25);
    }
    v22 = 295;
    goto LABEL_36;
  }
  if ( v18 )
    operator delete(v18 - 8);
  return 0;
}

```

## disassembly

```asm
0x180010448  mov     [rsp-38h+arg_18], rbx
0x18001044d  push    rbp
0x18001044e  push    rsi
0x18001044f  push    rdi
0x180010450  push    r12
0x180010452  push    r13
0x180010454  push    r14
0x180010456  push    r15
0x180010458  mov     rbp, rsp
0x18001045b  sub     rsp, 40h
0x18001045f  mov     rax, cs:__security_cookie
0x180010466  xor     rax, rsp
0x180010469  mov     [rbp+var_10], rax
0x18001046d  mov     r13, rdx
0x180010470  mov     r12, r8
0x180010473  xor     edx, edx
0x180010475  mov     r15, rcx
0x180010478  test    rcx, rcx
0x18001047b  jnz     short loc_1800104DC
0x18001047d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180010484  mov     ebx, 80004003h
0x180010489  mov     dword ptr [rbp+var_18], ebx
0x18001048c  test    rcx, rcx
0x18001048f  jz      short loc_1800104BD
0x180010491  lea     edi, [rdx+3]
0x180010494  mov     r8d, edi
0x180010497  lea     r9, aNoStringResult; "No string result specified"
0x18001049e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800104a3  lea     rcx, [rbp+var_18]
0x1800104a7  mov     edx, edi
0x1800104a9  lea     r9, [rbp+var_20]
0x1800104ad  mov     [rbp+var_20], rcx
0x1800104b1  lea     r8, asc_1800233AC; ": {}"
0x1800104b8  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800104bd  mov     edx, 0FBh; void *
0x1800104c2  mov     rcx, [rbp+38h]; this
0x1800104c6  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x1800104cd  mov     r9d, ebx; char *
0x1800104d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800104d5  mov     eax, ebx
0x1800104d7  jmp     loc_180010726
0x1800104dc  test    r13, r13
0x1800104df  jnz     short loc_180010529
0x1800104e1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800104e8  mov     ebx, 80070057h
0x1800104ed  mov     dword ptr [rbp+var_18], ebx
0x1800104f0  test    rcx, rcx
0x1800104f3  jz      short loc_180010522
0x1800104f5  lea     edi, [r13+3]
0x1800104f9  mov     r8d, edi
0x1800104fc  lea     r9, aNoStringToAppe; "No string to append specified"
0x180010503  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180010508  lea     rax, [rbp+var_18]
0x18001050c  mov     edx, edi
0x18001050e  lea     r9, [rbp+var_20]
0x180010512  mov     [rbp+var_20], rax
0x180010516  lea     r8, asc_1800233AC; ": {}"
0x18001051d  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180010522  mov     edx, 0FCh
0x180010527  jmp     short loc_1800104C2
0x180010529  test    r12, r12
0x18001052c  jnz     short loc_18001057A
0x18001052e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180010535  mov     ebx, 80070057h
0x18001053a  mov     dword ptr [rbp+var_18], ebx
0x18001053d  test    rcx, rcx
0x180010540  jz      short loc_180010570
0x180010542  lea     edi, [r12+3]
0x180010547  mov     r8d, edi
0x18001054a  lea     r9, aNoSecondString; "No second string to append specified"
0x180010551  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180010556  lea     rax, [rbp+var_18]
0x18001055a  mov     edx, edi
0x18001055c  lea     r9, [rbp+var_20]
0x180010560  mov     [rbp+var_20], rax
0x180010564  lea     r8, asc_1800233AC; ": {}"
0x18001056b  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180010570  mov     edx, 0FDh
0x180010575  jmp     loc_1800104C2
0x18001057a  mov     rdi, [rcx]
0x18001057d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180010581  mov     [rbp+var_18], rdx
0x180010585  mov     r14, rdx
0x180010588  test    rdi, rdi
0x18001058b  jz      short loc_1800105C0
0x18001058d  lea     rdx, [rbp+var_18]
0x180010591  mov     rcx, rdi
0x180010594  call    SczSize
0x180010599  xor     edx, edx
0x18001059b  mov     ebx, eax
0x18001059d  test    eax, eax
0x18001059f  jns     short loc_1800105AB
0x1800105a1  mov     edx, 104h
0x1800105a6  jmp     loc_1800104C2
0x1800105ab  mov     rdi, [r15]
0x1800105ae  mov     rbx, rsi
0x1800105b1  inc     rbx
0x1800105b4  cmp     [rdi+rbx*2], dx
0x1800105b8  jnz     short loc_1800105B1
0x1800105ba  mov     r14, [rbp+var_18]
0x1800105be  jmp     short loc_1800105C3
0x1800105c0  mov     rbx, rdx
0x1800105c3  mov     rax, rsi
0x1800105c6  inc     rax
0x1800105c9  cmp     [r13+rax*2+0], dx
0x1800105cf  jnz     short loc_1800105C6
0x1800105d1  inc     rsi
0x1800105d4  cmp     [r12+rsi*2], dx
0x1800105d9  jnz     short loc_1800105D1
0x1800105db  lea     rcx, [rax+1]
0x1800105df  add     rcx, rsi
0x1800105e2  add     rcx, rbx
0x1800105e5  cmp     r14, rcx
0x1800105e8  jnb     short loc_18001063C
0x1800105ea  mov     r14, rcx
0x1800105ed  lea     rcx, ds:8[rcx*2]; unsigned __int64
0x1800105f5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800105fa  test    rax, rax
0x1800105fd  jnz     short loc_18001060E
0x1800105ff  mov     ebx, 8007000Eh
0x180010604  mov     edx, 10Fh
0x180010609  jmp     loc_1800104C2
0x18001060e  mov     [rax], r14
0x180010611  lea     rdi, [rax+8]
0x180010615  mov     rdx, [r15]; Src
0x180010618  test    rdx, rdx
0x18001061b  jz      short loc_18001062F
0x18001061d  lea     r8, ds:2[rbx*2]; Size
0x180010625  mov     rcx, rdi; void *
0x180010628  call    memcpy_0
0x18001062d  jmp     short loc_180010634
0x18001062f  xor     eax, eax
0x180010631  mov     [rdi], ax
0x180010634  mov     rbx, [r15]
0x180010637  mov     [r15], rdi
0x18001063a  jmp     short loc_18001063F
0x18001063c  mov     rbx, rdx
0x18001063f  mov     r8, r13; wchar_t *
0x180010642  mov     rdx, r14; unsigned __int64
0x180010645  mov     rcx, rdi; wchar_t *
0x180010648  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001064d  mov     esi, eax
0x18001064f  test    eax, eax
0x180010651  jns     short loc_1800106BC
0x180010653  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001065a  mov     dword ptr [rbp+var_18], eax
0x18001065d  test    rcx, rcx
0x180010660  jz      short loc_180010692
0x180010662  mov     edi, 3
0x180010667  lea     r9, aFailedToConcat; "Failed to concat string."
0x18001066e  mov     r8d, edi
0x180010671  xor     edx, edx
0x180010673  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180010678  lea     rax, [rbp+var_18]
0x18001067c  mov     edx, edi
0x18001067e  lea     r9, [rbp+var_20]
0x180010682  mov     [rbp+var_20], rax
0x180010686  lea     r8, asc_1800233AC; ": {}"
0x18001068d  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180010692  mov     edx, 126h; void *
0x180010697  mov     rcx, [rbp+38h]; this
0x18001069b  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x1800106a2  mov     r9d, esi; char *
0x1800106a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106aa  test    rbx, rbx
0x1800106ad  jz      short loc_1800106B8
0x1800106af  lea     rcx, [rbx-8]; Block
0x1800106b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800106b8  mov     eax, esi
0x1800106ba  jmp     short loc_180010726
0x1800106bc  mov     rcx, [r15]; wchar_t *
0x1800106bf  mov     r8, r12; wchar_t *
0x1800106c2  mov     rdx, r14; unsigned __int64
0x1800106c5  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800106ca  mov     esi, eax
0x1800106cc  test    eax, eax
0x1800106ce  jns     short loc_180010716
0x1800106d0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800106d7  mov     dword ptr [rbp+var_18], eax
0x1800106da  test    rcx, rcx
0x1800106dd  jz      short loc_18001070F
0x1800106df  mov     edi, 3
0x1800106e4  lea     r9, aFailedToConcat_0; "Failed to concat second string."
0x1800106eb  mov     r8d, edi
0x1800106ee  xor     edx, edx
0x1800106f0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800106f5  lea     rax, [rbp+var_18]
0x1800106f9  mov     edx, edi
0x1800106fb  lea     r9, [rbp+var_20]
0x1800106ff  mov     [rbp+var_20], rax
0x180010703  lea     r8, asc_1800233AC; ": {}"
0x18001070a  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001070f  mov     edx, 127h
0x180010714  jmp     short loc_180010697
0x180010716  test    rbx, rbx
0x180010719  jz      short loc_180010724
0x18001071b  lea     rcx, [rbx-8]; Block
0x18001071f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010724  xor     eax, eax
0x180010726  mov     rcx, [rbp+var_10]
0x18001072a  xor     rcx, rsp; StackCookie
0x18001072d  call    __security_check_cookie
0x180010732  mov     rbx, [rsp+40h+arg_18]
0x18001073a  add     rsp, 40h
0x18001073e  pop     r15
0x180010740  pop     r14
0x180010742  pop     r13
0x180010744  pop     r12
0x180010746  pop     rdi
0x180010747  pop     rsi
0x180010748  pop     rbp
0x180010749  retn
```
