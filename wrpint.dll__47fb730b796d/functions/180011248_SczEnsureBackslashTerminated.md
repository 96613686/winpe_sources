# SczEnsureBackslashTerminated

- ea: `0x180011248`
- end: `0x18001135e`
- name: `SczEnsureBackslashTerminated`
- size: `278`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180004fd0`
- `0x180005260`
- `0x180006e50`
- `0x180011e10`
- `0x180014ce0`

## callees

- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x180010750`
- `0x180011248`
- `0x18001b7b0`

## string_xrefs

- `0x180011282`: `No path result specified`

## pseudocode

```c
__int64 __fastcall SczEnsureBackslashTerminated(__int64 *a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  __int64 v4; // rdx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rcx
  int v8[2]; // [rsp+20h] [rbp-28h] BYREF
  int v9; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a1 )
  {
    v1 = -2147467261;
    v9 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path result specified");
      *(_QWORD *)v8 = &v9;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v9,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v8);
    }
    v2 = 604;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v1);
    return v1;
  }
  v4 = *a1;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v4 + 2 * v5) );
  if ( *(_WORD *)(v4 + 2 * v5 - 2) != 92 )
  {
    v6 = SczAllocConcatSz(a1, L"\\");
    v1 = v6;
    if ( v6 < 0 )
    {
      v9 = v6;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to concat backslash onto string.");
        *(_QWORD *)v8 = &v9;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v7,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v8);
      }
      v2 = 610;
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011248  mov     [rsp+arg_8], rbx
0x18001124d  push    rdi
0x18001124e  sub     rsp, 40h
0x180011252  mov     rax, cs:__security_cookie
0x180011259  xor     rax, rsp
0x18001125c  mov     [rsp+48h+var_18], rax
0x180011261  xor     edi, edi
0x180011263  test    rcx, rcx
0x180011266  jnz     short loc_1800112CD
0x180011268  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001126f  mov     ebx, 80004003h
0x180011274  mov     [rsp+48h+var_20], ebx
0x180011278  test    rcx, rcx
0x18001127b  jz      short loc_1800112B0
0x18001127d  mov     edi, 3
0x180011282  lea     r9, aNoPathResultSp; "No path result specified"
0x180011289  mov     r8d, edi
0x18001128c  xor     edx, edx
0x18001128e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180011293  lea     rcx, [rsp+48h+var_20]
0x180011298  mov     edx, edi
0x18001129a  lea     r9, [rsp+48h+var_28]
0x18001129f  mov     qword ptr [rsp+48h+var_28], rcx; int
0x1800112a4  lea     r8, asc_1800233AC; ": {}"
0x1800112ab  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800112b0  mov     edx, 25Ch; void *
0x1800112b5  mov     rcx, [rsp+48h]; this
0x1800112ba  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x1800112c1  mov     r9d, ebx; char *
0x1800112c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112c9  mov     eax, ebx
0x1800112cb  jmp     short loc_180011346
0x1800112cd  mov     rdx, [rcx]
0x1800112d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800112d4  inc     rax
0x1800112d7  cmp     [rdx+rax*2], di
0x1800112db  jnz     short loc_1800112D4
0x1800112dd  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x1800112e3  jz      short loc_180011344
0x1800112e5  lea     rdx, asc_18001F814; "\\"
0x1800112ec  call    SczAllocConcatSz
0x1800112f1  mov     ebx, eax
0x1800112f3  test    eax, eax
0x1800112f5  jns     short loc_180011344
0x1800112f7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800112fe  mov     [rsp+48h+var_20], eax
0x180011302  test    rcx, rcx
0x180011305  jz      short loc_18001133A
0x180011307  mov     edi, 3
0x18001130c  lea     r9, aFailedToConcat_1; "Failed to concat backslash onto string."
0x180011313  mov     r8d, edi
0x180011316  xor     edx, edx
0x180011318  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001131d  lea     rax, [rsp+48h+var_20]
0x180011322  mov     edx, edi
0x180011324  lea     r9, [rsp+48h+var_28]
0x180011329  mov     qword ptr [rsp+48h+var_28], rax
0x18001132e  lea     r8, asc_1800233AC; ": {}"
0x180011335  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001133a  mov     edx, 262h
0x18001133f  jmp     loc_1800112B5
0x180011344  xor     eax, eax
0x180011346  mov     rcx, [rsp+48h+var_18]
0x18001134b  xor     rcx, rsp; StackCookie
0x18001134e  call    __security_check_cookie
0x180011353  mov     rbx, [rsp+48h+arg_8]
0x180011358  add     rsp, 40h
0x18001135c  pop     rdi
0x18001135d  retn
```
