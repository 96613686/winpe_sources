# SczAllocFromSz

- ea: `0x180010de4`
- end: `0x180010fd8`
- name: `SczAllocFromSz`
- size: `500`
- prototype: `__int64 __fastcall(_QWORD *, _WORD *)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180004abc`
- `0x180004fd0`
- `0x180005260`
- `0x180005920`
- `0x180006e50`
- `0x180006f84`
- `0x180011e10`
- `0x180014054`

## callees

- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18001029c`
- `0x180010de4`
- `0x18001b7b0`

## string_xrefs

- `0x180010f73`: `Failed to copy source string to destination`

## pseudocode

```c
__int64 __fastcall SczAllocFromSz(_QWORD *a1, _WORD *a2)
{
  _WORD *v2; // rbx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdi
  unsigned __int64 v8; // rdi
  int v9; // eax
  unsigned int v10; // r14d
  _WORD *v12; // rdx
  __int64 v13; // rax
  _WORD *v14; // rcx
  __int64 v15; // rcx
  int *v16; // [rsp+20h] [rbp-20h] BYREF
  int v17; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  v2 = a2;
  if ( a1 )
  {
    if ( a2 )
    {
      v7 = -1;
      do
        ++v7;
      while ( a2[v7] );
      v8 = v7 + 1;
      v9 = SczAlloc(a1, v8);
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
          (const char *)(unsigned int)v9);
        return v10;
      }
      v12 = (_WORD *)*a1;
      if ( v8 )
      {
        if ( v8 <= 0x7FFFFFFF )
        {
          v13 = 2147483646;
          do
          {
            if ( !v13 )
              break;
            if ( !*v2 )
              break;
            *v12++ = *v2++;
            --v13;
            --v8;
          }
          while ( v8 );
          v14 = v12 - 1;
          v4 = v8 == 0 ? 0x8007007A : 0;
          if ( v8 )
            v14 = v12;
          *v14 = 0;
          if ( v8 )
            return 0;
        }
        else
        {
          v4 = -2147024809;
          *v12 = 0;
        }
      }
      else
      {
        v4 = -2147024809;
      }
      v17 = v4;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy source string to destination");
        v16 = &v17;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v15,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v16);
      }
      v5 = 404;
    }
    else
    {
      v4 = -2147024809;
      v17 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string specified");
        v16 = &v17;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v6,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v16);
      }
      v5 = 400;
    }
  }
  else
  {
    v4 = -2147467261;
    v17 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      v16 = &v17;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v17,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v16);
    }
    v5 = 399;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v5, (int)"onecore\\base\\cbs\\util\\cbsstr.cpp", (const char *)v4);
  return v4;
}

```

## disassembly

```asm
0x180010de4  mov     [rsp-28h+arg_10], rbx
0x180010de9  push    rbp
0x180010dea  push    rsi
0x180010deb  push    rdi
0x180010dec  push    r14
0x180010dee  push    r15
0x180010df0  mov     rbp, rsp
0x180010df3  sub     rsp, 40h
0x180010df7  mov     rax, cs:__security_cookie
0x180010dfe  xor     rax, rsp
0x180010e01  mov     [rbp+var_10], rax
0x180010e05  xor     r15d, r15d
0x180010e08  mov     rbx, rdx
0x180010e0b  mov     rsi, rcx
0x180010e0e  test    rcx, rcx
0x180010e11  jnz     short loc_180010E5F
0x180010e13  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180010e1a  mov     ebx, 80004003h
0x180010e1f  mov     [rbp+var_18], ebx
0x180010e22  test    rcx, rcx
0x180010e25  jz      short loc_180010E55
0x180010e27  lea     edi, [rsi+3]
0x180010e2a  xor     edx, edx
0x180010e2c  mov     r8d, edi
0x180010e2f  lea     r9, aNoStringResult; "No string result specified"
0x180010e36  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180010e3b  lea     rcx, [rbp+var_18]
0x180010e3f  mov     edx, edi
0x180010e41  lea     r9, [rbp+var_20]
0x180010e45  mov     [rbp+var_20], rcx
0x180010e49  lea     r8, asc_1800233AC; ": {}"
0x180010e50  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180010e55  mov     edx, 18Fh
0x180010e5a  jmp     loc_180010FA3
0x180010e5f  test    rdx, rdx
0x180010e62  jnz     short loc_180010EAE
0x180010e64  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180010e6b  mov     ebx, 80070057h
0x180010e70  mov     [rbp+var_18], ebx
0x180010e73  test    rcx, rcx
0x180010e76  jz      short loc_180010EA4
0x180010e78  lea     edi, [rdx+3]
0x180010e7b  mov     r8d, edi
0x180010e7e  lea     r9, aNoStringSpecif; "No string specified"
0x180010e85  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180010e8a  lea     rax, [rbp+var_18]
0x180010e8e  mov     edx, edi
0x180010e90  lea     r9, [rbp+var_20]
0x180010e94  mov     [rbp+var_20], rax
0x180010e98  lea     r8, asc_1800233AC; ": {}"
0x180010e9f  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180010ea4  mov     edx, 190h
0x180010ea9  jmp     loc_180010FA3
0x180010eae  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010eb2  inc     rdi
0x180010eb5  cmp     [rdx+rdi*2], r15w
0x180010eba  jnz     short loc_180010EB2
0x180010ebc  inc     rdi
0x180010ebf  mov     rdx, rdi
0x180010ec2  call    SczAlloc
0x180010ec7  mov     r14d, eax
0x180010eca  test    eax, eax
0x180010ecc  jns     short loc_180010EEE
0x180010ece  mov     rcx, [rbp+28h]; this
0x180010ed2  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x180010ed9  mov     r9d, eax; char *
0x180010edc  mov     edx, 193h; void *
0x180010ee1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ee6  mov     eax, r14d
0x180010ee9  jmp     loc_180010FB8
0x180010eee  mov     rdx, [rsi]
0x180010ef1  test    rdi, rdi
0x180010ef4  jz      short loc_180010F51
0x180010ef6  cmp     rdi, 7FFFFFFFh
0x180010efd  jbe     short loc_180010F06
0x180010eff  mov     ebx, 80070057h
0x180010f04  jmp     short loc_180010F5B
0x180010f06  mov     eax, 7FFFFFFEh
0x180010f0b  test    rax, rax
0x180010f0e  jz      short loc_180010F2C
0x180010f10  movzx   ecx, word ptr [rbx]
0x180010f13  test    cx, cx
0x180010f16  jz      short loc_180010F2C
0x180010f18  mov     [rdx], cx
0x180010f1b  add     rbx, 2
0x180010f1f  add     rdx, 2
0x180010f23  dec     rax
0x180010f26  sub     rdi, 1
0x180010f2a  jnz     short loc_180010F0B
0x180010f2c  mov     rax, rdi
0x180010f2f  lea     rcx, [rdx-2]
0x180010f33  neg     rax
0x180010f36  sbb     ebx, ebx
0x180010f38  not     ebx
0x180010f3a  and     ebx, 8007007Ah
0x180010f40  test    rdi, rdi
0x180010f43  cmovnz  rcx, rdx
0x180010f47  mov     [rcx], r15w
0x180010f4b  jz      short loc_180010F5F
0x180010f4d  xor     eax, eax
0x180010f4f  jmp     short loc_180010FB8
0x180010f51  mov     ebx, 80070057h
0x180010f56  test    rdi, rdi
0x180010f59  jz      short loc_180010F5F
0x180010f5b  mov     [rdx], r15w
0x180010f5f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180010f66  mov     [rbp+var_18], ebx
0x180010f69  test    rcx, rcx
0x180010f6c  jz      short loc_180010F9E
0x180010f6e  mov     edi, 3
0x180010f73  lea     r9, aFailedToCopySo; "Failed to copy source string to destina"...
0x180010f7a  mov     r8d, edi
0x180010f7d  xor     edx, edx
0x180010f7f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180010f84  lea     rax, [rbp+var_18]
0x180010f88  mov     edx, edi
0x180010f8a  lea     r9, [rbp+var_20]
0x180010f8e  mov     [rbp+var_20], rax
0x180010f92  lea     r8, asc_1800233AC; ": {}"
0x180010f99  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180010f9e  mov     edx, 194h; void *
0x180010fa3  mov     rcx, [rbp+28h]; this
0x180010fa7  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x180010fae  mov     r9d, ebx; char *
0x180010fb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010fb6  mov     eax, ebx
0x180010fb8  mov     rcx, [rbp+var_10]
0x180010fbc  xor     rcx, rsp; StackCookie
0x180010fbf  call    __security_check_cookie
0x180010fc4  mov     rbx, [rsp+40h+arg_10]
0x180010fcc  add     rsp, 40h
0x180010fd0  pop     r15
0x180010fd2  pop     r14
0x180010fd4  pop     rdi
0x180010fd5  pop     rsi
0x180010fd6  pop     rbp
0x180010fd7  retn
```
