# SczAlloc

- ea: `0x18001029c`
- end: `0x180010442`
- name: `SczAlloc`
- size: `422`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `6`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180007288`
- `0x180010af0`
- `0x180010de4`
- `0x1800138a0`
- `0x1800147b0`
- `0x180014ce0`

## callees

- `0x180001de0`
- `0x180001dec`
- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18001029c`
- `0x180011654`
- `0x18001b7b0`

## pseudocode

```c
__int64 __fastcall SczAlloc(_QWORD *a1, unsigned __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  _WORD *v7; // rcx
  int v8; // eax
  unsigned int v9; // esi
  _WORD *v10; // rax
  unsigned __int64 *v11; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int64 v12; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

  if ( !a1 )
  {
    v4 = -2147467261;
    LODWORD(v12) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      v11 = &v12;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v12,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v11);
    }
    v5 = 12;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v4);
    return v4;
  }
  if ( a2 > 0x3FFFFFFF )
  {
    v4 = -2147317563;
    LODWORD(v12) = -2147317563;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"string size too big");
      v11 = &v12;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v12,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v11);
    }
    v5 = 13;
    goto LABEL_5;
  }
  v7 = (_WORD *)*a1;
  v12 = 0;
  if ( !v7 )
  {
LABEL_17:
    if ( *a1 )
      return 0;
    goto LABEL_18;
  }
  v8 = SczSize(v7, &v12);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)(unsigned int)v8);
    return v9;
  }
  if ( v12 >= a2 )
  {
    if ( v12 )
      *(_WORD *)*a1 = 0;
    goto LABEL_17;
  }
  operator delete((void *)(*a1 - 8LL));
  *a1 = 0;
LABEL_18:
  v10 = operator new[](2 * a2 + 8);
  if ( !v10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)0x8007000ELL);
    return 2147942414LL;
  }
  *(_QWORD *)v10 = a2;
  *a1 = v10 + 4;
  v10[4] = 0;
  return 0;
}

```

## disassembly

```asm
0x18001029c  mov     [rsp-18h+arg_10], rbx
0x1800102a1  push    rbp
0x1800102a2  push    rsi
0x1800102a3  push    rdi
0x1800102a4  mov     rbp, rsp
0x1800102a7  sub     rsp, 40h
0x1800102ab  mov     rax, cs:__security_cookie
0x1800102b2  xor     rax, rsp
0x1800102b5  mov     [rbp+var_10], rax
0x1800102b9  mov     rdi, rdx
0x1800102bc  mov     rbx, rcx
0x1800102bf  test    rcx, rcx
0x1800102c2  jnz     short loc_180010327
0x1800102c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800102cb  mov     edi, 80004003h
0x1800102d0  mov     dword ptr [rbp+var_18], edi
0x1800102d3  test    rcx, rcx
0x1800102d6  jz      short loc_180010308
0x1800102d8  mov     ebx, 3
0x1800102dd  lea     r9, aNoStringResult; "No string result specified"
0x1800102e4  mov     r8d, ebx
0x1800102e7  xor     edx, edx
0x1800102e9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800102ee  lea     rcx, [rbp+var_18]
0x1800102f2  mov     edx, ebx
0x1800102f4  lea     r9, [rbp+var_20]
0x1800102f8  mov     [rbp+var_20], rcx
0x1800102fc  lea     r8, asc_1800233AC; ": {}"
0x180010303  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180010308  mov     edx, 0Ch; void *
0x18001030d  mov     rcx, [rbp+18h]; this
0x180010311  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x180010318  mov     r9d, edi; char *
0x18001031b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010320  mov     eax, edi
0x180010322  jmp     loc_180010429
0x180010327  cmp     rdi, 3FFFFFFFh
0x18001032e  jbe     short loc_18001037B
0x180010330  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180010337  mov     edi, 800288C5h
0x18001033c  mov     dword ptr [rbp+var_18], edi
0x18001033f  test    rcx, rcx
0x180010342  jz      short loc_180010374
0x180010344  mov     ebx, 3
0x180010349  lea     r9, aStringSizeTooB; "string size too big"
0x180010350  mov     r8d, ebx
0x180010353  xor     edx, edx
0x180010355  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001035a  lea     rcx, [rbp+var_18]
0x18001035e  mov     edx, ebx
0x180010360  lea     r9, [rbp+var_20]
0x180010364  mov     [rbp+var_20], rcx
0x180010368  lea     r8, asc_1800233AC; ": {}"
0x18001036f  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180010374  mov     edx, 0Dh
0x180010379  jmp     short loc_18001030D
0x18001037b  mov     rcx, [rcx]
0x18001037e  mov     [rbp+var_18], 0
0x180010386  test    rcx, rcx
0x180010389  jz      short loc_1800103E1
0x18001038b  lea     rdx, [rbp+var_18]
0x18001038f  call    SczSize
0x180010394  mov     esi, eax
0x180010396  test    eax, eax
0x180010398  jns     short loc_1800103B6
0x18001039a  mov     rcx, [rbp+18h]; this
0x18001039e  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x1800103a5  mov     r9d, eax; char *
0x1800103a8  mov     edx, 15h; void *
0x1800103ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103b2  mov     eax, esi
0x1800103b4  jmp     short loc_180010429
0x1800103b6  mov     rax, [rbp+var_18]
0x1800103ba  cmp     rax, rdi
0x1800103bd  jnb     short loc_1800103D4
0x1800103bf  mov     rcx, [rbx]
0x1800103c2  sub     rcx, 8; Block
0x1800103c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800103cb  mov     qword ptr [rbx], 0
0x1800103d2  jmp     short loc_1800103E7
0x1800103d4  test    rax, rax
0x1800103d7  jz      short loc_1800103E1
0x1800103d9  mov     rcx, [rbx]
0x1800103dc  xor     eax, eax
0x1800103de  mov     [rcx], ax
0x1800103e1  cmp     qword ptr [rbx], 0
0x1800103e5  jnz     short loc_180010427
0x1800103e7  lea     rcx, ds:8[rdi*2]; unsigned __int64
0x1800103ef  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800103f4  test    rax, rax
0x1800103f7  jnz     short loc_180010418
0x1800103f9  mov     rcx, [rbp+18h]; this
0x1800103fd  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x180010404  mov     ebx, 8007000Eh
0x180010409  lea     edx, [rax+27h]; void *
0x18001040c  mov     r9d, ebx; char *
0x18001040f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010414  mov     eax, ebx
0x180010416  jmp     short loc_180010429
0x180010418  mov     [rax], rdi
0x18001041b  lea     rcx, [rax+8]
0x18001041f  xor     eax, eax
0x180010421  mov     [rbx], rcx
0x180010424  mov     [rcx], ax
0x180010427  xor     eax, eax
0x180010429  mov     rcx, [rbp+var_10]
0x18001042d  xor     rcx, rsp; StackCookie
0x180010430  call    __security_check_cookie
0x180010435  mov     rbx, [rsp+40h+arg_10]
0x18001043a  add     rsp, 40h
0x18001043e  pop     rdi
0x18001043f  pop     rsi
0x180010440  pop     rbp
0x180010441  retn
```
