# SczPublicAllocFromSz

- ea: `0x180011364`
- end: `0x18001164b`
- name: `SczPublicAllocFromSz`
- size: `743`
- prototype: `__int64 __fastcall(_QWORD *, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180005920`

## callees

- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x180011364`
- `0x18001b7b0`
- `0x18001c010`

## string_xrefs

- `0x1800115e2`: `Failed to copy new string.`

## pseudocode

```c
__int64 __fastcall SczPublicAllocFromSz(_QWORD *a1, __int64 a2, _WORD *a3)
{
  _WORD *v3; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  _WORD *v10; // rax
  __int64 v11; // rdx
  unsigned int v12; // esi
  __int64 v13; // r15
  __int64 v14; // rcx
  _WORD *v16; // rax
  _WORD *v17; // r9
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  _WORD *v20; // r8
  _WORD *v21; // rcx
  __int64 v22; // rcx
  int *v23; // [rsp+20h] [rbp-20h] BYREF
  int v24; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v3 = a3;
  if ( !a1 )
  {
    v6 = -2147467261;
    v24 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      v23 = &v24;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v24,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v23);
    }
    v7 = 521;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v6);
    return v6;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    v24 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No malloc specified");
      v23 = &v24;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v8,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v23);
    }
    v7 = 522;
    goto LABEL_36;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    v24 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string specified");
      v23 = &v24;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v9,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v23);
    }
    v7 = 523;
    goto LABEL_36;
  }
  v10 = a3;
  v11 = 0x7FFFFFFF;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v6 = -2147024809;
  v12 = v11 == 0 ? 0x80070057 : 0;
  v13 = (0x7FFFFFFF - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v16 = (_WORD *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 24LL))(a2, 2 * v13 + 2);
    v17 = v16;
    if ( v16 )
    {
      v18 = v13 + 1;
      if ( v13 != -1 )
      {
        if ( v18 > 0x7FFFFFFF )
        {
          *v16 = 0;
        }
        else
        {
          v19 = 2147483646;
          v20 = v17;
          do
          {
            if ( !v19 )
              break;
            if ( !*v3 )
              break;
            *v20++ = *v3++;
            --v19;
            --v18;
          }
          while ( v18 );
          v21 = v20 - 1;
          v6 = v18 == 0 ? 0x8007007A : 0;
          if ( v18 )
            v21 = v20;
          *v21 = 0;
          if ( v18 )
          {
            *a1 = v17;
            return 0;
          }
        }
      }
      (*(void (__fastcall **)(__int64, _WORD *))(*(_QWORD *)a2 + 40LL))(a2, v17);
      v24 = v6;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy new string.");
        v23 = &v24;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v22,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v23);
      }
      v7 = 535;
    }
    else
    {
      v6 = -2147024882;
      v7 = 529;
    }
    goto LABEL_36;
  }
  v24 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get length of passed in string");
    v23 = &v24;
    LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      v14,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
      (__int64)&v23);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x20E,
    (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
    (const char *)v12);
  return v12;
}

```

## disassembly

```asm
0x180011364  mov     [rsp-38h+arg_10], rbx
0x180011369  push    rbp
0x18001136a  push    rsi
0x18001136b  push    rdi
0x18001136c  push    r12
0x18001136e  push    r13
0x180011370  push    r14
0x180011372  push    r15
0x180011374  mov     rbp, rsp
0x180011377  sub     rsp, 40h
0x18001137b  mov     rax, cs:__security_cookie
0x180011382  xor     rax, rsp
0x180011385  mov     [rbp+var_10], rax
0x180011389  xor     r13d, r13d
0x18001138c  mov     rdi, r8
0x18001138f  mov     r14, rdx
0x180011392  mov     r12, rcx
0x180011395  test    rcx, rcx
0x180011398  jnz     short loc_1800113E8
0x18001139a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800113a1  mov     ebx, 80004003h
0x1800113a6  mov     [rbp+var_18], ebx
0x1800113a9  test    rcx, rcx
0x1800113ac  jz      short loc_1800113DE
0x1800113ae  lea     edi, [r12+3]
0x1800113b3  xor     edx, edx
0x1800113b5  mov     r8d, edi
0x1800113b8  lea     r9, aNoStringResult; "No string result specified"
0x1800113bf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800113c4  lea     rcx, [rbp+var_18]
0x1800113c8  mov     edx, edi
0x1800113ca  lea     r9, [rbp+var_20]
0x1800113ce  mov     [rbp+var_20], rcx
0x1800113d2  lea     r8, asc_1800233AC; ": {}"
0x1800113d9  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800113de  mov     edx, 209h
0x1800113e3  jmp     loc_180011612
0x1800113e8  test    r14, r14
0x1800113eb  jnz     short loc_18001143A
0x1800113ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800113f4  mov     ebx, 80070057h
0x1800113f9  mov     [rbp+var_18], ebx
0x1800113fc  test    rcx, rcx
0x1800113ff  jz      short loc_180011430
0x180011401  lea     edi, [r14+3]
0x180011405  xor     edx, edx
0x180011407  mov     r8d, edi
0x18001140a  lea     r9, aNoMallocSpecif; "No malloc specified"
0x180011411  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180011416  lea     rax, [rbp+var_18]
0x18001141a  mov     edx, edi
0x18001141c  lea     r9, [rbp+var_20]
0x180011420  mov     [rbp+var_20], rax
0x180011424  lea     r8, asc_1800233AC; ": {}"
0x18001142b  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011430  mov     edx, 20Ah
0x180011435  jmp     loc_180011612
0x18001143a  test    r8, r8
0x18001143d  jnz     short loc_18001148C
0x18001143f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011446  mov     ebx, 80070057h
0x18001144b  mov     [rbp+var_18], ebx
0x18001144e  test    rcx, rcx
0x180011451  jz      short loc_180011482
0x180011453  lea     edi, [r8+3]
0x180011457  xor     edx, edx
0x180011459  mov     r8d, edi
0x18001145c  lea     r9, aNoStringSpecif; "No string specified"
0x180011463  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180011468  lea     rax, [rbp+var_18]
0x18001146c  mov     edx, edi
0x18001146e  lea     r9, [rbp+var_20]
0x180011472  mov     [rbp+var_20], rax
0x180011476  lea     r8, asc_1800233AC; ": {}"
0x18001147d  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011482  mov     edx, 20Bh
0x180011487  jmp     loc_180011612
0x18001148c  mov     ecx, 7FFFFFFFh
0x180011491  mov     rax, r8
0x180011494  mov     edx, ecx
0x180011496  cmp     [rax], r13w
0x18001149a  jz      short loc_1800114A6
0x18001149c  add     rax, 2
0x1800114a0  sub     rdx, 1
0x1800114a4  jnz     short loc_180011496
0x1800114a6  mov     rax, rdx
0x1800114a9  mov     ebx, 80070057h
0x1800114ae  neg     rax
0x1800114b1  mov     rax, rdx
0x1800114b4  sbb     esi, esi
0x1800114b6  sub     rcx, rdx
0x1800114b9  not     esi
0x1800114bb  and     esi, ebx
0x1800114bd  neg     rax
0x1800114c0  sbb     r15, r15
0x1800114c3  and     r15, rcx
0x1800114c6  test    rdx, rdx
0x1800114c9  jnz     short loc_180011525
0x1800114cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800114d2  mov     [rbp+var_18], esi
0x1800114d5  test    rcx, rcx
0x1800114d8  jz      short loc_180011506
0x1800114da  lea     edi, [rdx+3]
0x1800114dd  mov     r8d, edi
0x1800114e0  lea     r9, aFailedToGetLen; "Failed to get length of passed in strin"...
0x1800114e7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800114ec  lea     rax, [rbp+var_18]
0x1800114f0  mov     edx, edi
0x1800114f2  lea     r9, [rbp+var_20]
0x1800114f6  mov     [rbp+var_20], rax
0x1800114fa  lea     r8, asc_1800233AC; ": {}"
0x180011501  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011506  mov     rcx, [rbp+38h]; this
0x18001150a  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x180011511  mov     r9d, esi; char *
0x180011514  mov     edx, 20Eh; void *
0x180011519  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001151e  mov     eax, esi
0x180011520  jmp     loc_180011627
0x180011525  mov     rax, [r14]
0x180011528  lea     rdx, ds:2[r15*2]
0x180011530  mov     rcx, r14
0x180011533  mov     rax, [rax+18h]
0x180011537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001153c  mov     r9, rax
0x18001153f  test    rax, rax
0x180011542  jnz     short loc_180011553
0x180011544  mov     ebx, 8007000Eh
0x180011549  mov     edx, 211h
0x18001154e  jmp     loc_180011612
0x180011553  lea     rdx, [r15+1]
0x180011557  test    rdx, rdx
0x18001155a  jz      short loc_1800115BC
0x18001155c  cmp     rdx, 7FFFFFFFh
0x180011563  ja      short loc_1800115B8
0x180011565  mov     eax, 7FFFFFFEh
0x18001156a  mov     r8, r9
0x18001156d  test    rax, rax
0x180011570  jz      short loc_18001158F
0x180011572  movzx   ecx, word ptr [rdi]
0x180011575  test    cx, cx
0x180011578  jz      short loc_18001158F
0x18001157a  mov     [r8], cx
0x18001157e  add     rdi, 2
0x180011582  add     r8, 2
0x180011586  dec     rax
0x180011589  sub     rdx, 1
0x18001158d  jnz     short loc_18001156D
0x18001158f  mov     rax, rdx
0x180011592  lea     rcx, [r8-2]
0x180011596  neg     rax
0x180011599  sbb     ebx, ebx
0x18001159b  not     ebx
0x18001159d  and     ebx, 8007007Ah
0x1800115a3  test    rdx, rdx
0x1800115a6  cmovnz  rcx, r8
0x1800115aa  mov     [rcx], r13w
0x1800115ae  jz      short loc_1800115BC
0x1800115b0  mov     [r12], r9
0x1800115b4  xor     eax, eax
0x1800115b6  jmp     short loc_180011627
0x1800115b8  mov     [rax], r13w
0x1800115bc  mov     rax, [r14]
0x1800115bf  mov     rdx, r9
0x1800115c2  mov     rcx, r14
0x1800115c5  mov     rax, [rax+28h]
0x1800115c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115ce  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800115d5  mov     [rbp+var_18], ebx
0x1800115d8  test    rcx, rcx
0x1800115db  jz      short loc_18001160D
0x1800115dd  mov     edi, 3
0x1800115e2  lea     r9, aFailedToCopyNe; "Failed to copy new string."
0x1800115e9  mov     r8d, edi
0x1800115ec  xor     edx, edx
0x1800115ee  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800115f3  lea     rax, [rbp+var_18]
0x1800115f7  mov     edx, edi
0x1800115f9  lea     r9, [rbp+var_20]
0x1800115fd  mov     [rbp+var_20], rax
0x180011601  lea     r8, asc_1800233AC; ": {}"
0x180011608  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001160d  mov     edx, 217h; void *
0x180011612  mov     rcx, [rbp+38h]; this
0x180011616  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x18001161d  mov     r9d, ebx; char *
0x180011620  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011625  mov     eax, ebx
0x180011627  mov     rcx, [rbp+var_10]
0x18001162b  xor     rcx, rsp; StackCookie
0x18001162e  call    __security_check_cookie
0x180011633  mov     rbx, [rsp+40h+arg_10]
0x18001163b  add     rsp, 40h
0x18001163f  pop     r15
0x180011641  pop     r14
0x180011643  pop     r13
0x180011645  pop     r12
0x180011647  pop     rdi
0x180011648  pop     rsi
0x180011649  pop     rbp
0x18001164a  retn
```
