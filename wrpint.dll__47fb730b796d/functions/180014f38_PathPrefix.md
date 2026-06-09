# PathPrefix

- ea: `0x180014f38`
- end: `0x180015173`
- name: `PathPrefix`
- size: `571`
- prototype: `__int64 __fastcall(_WORD **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180014054`

## callees

- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x180010fe0`
- `0x180011654`
- `0x180014f38`
- `0x18001b76e`
- `0x18001b7b0`

## string_xrefs

- `0x180014f7e`: `No full path result specified`
- `0x1800150a9`: `onecore\base\cbs\util\cbspath.cpp`
- `0x180015149`: `onecore\base\cbs\util\cbspath.cpp`
- `0x180014fcf`: `Invalid full path specified`
- `0x180015115`: `Invalid path provided to prefix.`

## pseudocode

```c
__int64 __fastcall PathPrefix(_WORD **a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  _WORD *v4; // rbx
  __int64 v5; // rcx
  unsigned __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v10; // rcx
  __int64 *v11; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  if ( !a1 )
  {
    v2 = -2147467261;
    LODWORD(v12) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No full path result specified");
      v11 = &v12;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v12,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v11);
    }
    v3 = 143;
    goto LABEL_30;
  }
  v4 = *a1;
  if ( !*a1 )
  {
    v2 = -2147024809;
    LODWORD(v12) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid full path specified");
      v11 = &v12;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v5,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v11);
    }
    v3 = 144;
    goto LABEL_30;
  }
  if ( (unsigned __int16)(*v4 - 97) > 0x19u && (unsigned __int16)(*v4 - 65) > 0x19u || v4[1] != 58 || v4[2] != 92 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v4[v6] );
    if ( v6 < 4 || *v4 != 92 || v4[1] != 92 )
    {
      v2 = -2147024809;
      LODWORD(v12) = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid path provided to prefix.");
        v11 = &v12;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v10,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v11);
      }
      v3 = 171;
      goto LABEL_30;
    }
    if ( v4[2] != 63 && v4[3] != 92 )
    {
      v12 = 0;
      v7 = SczSize(v4, &v12);
      v8 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA2,
          (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)(unsigned int)v7);
        return v8;
      }
      memmove_0(v4, v4 + 1, 2 * v12 - 2);
      v2 = SczAllocPrefixSz(a1, L"\\\\?\\UNC");
      if ( v2 < 0 )
      {
        v3 = 166;
        goto LABEL_30;
      }
    }
    return 0;
  }
  v2 = SczAllocPrefixSz(a1, L"\\\\?\\");
  if ( v2 >= 0 )
    return 0;
  v3 = 153;
LABEL_30:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
    (const char *)(unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180014f38  push    rbp
0x180014f3a  push    rbx
0x180014f3b  push    rsi
0x180014f3c  push    rdi
0x180014f3d  push    r14
0x180014f3f  push    r15
0x180014f41  mov     rbp, rsp
0x180014f44  sub     rsp, 48h
0x180014f48  mov     rax, cs:__security_cookie
0x180014f4f  xor     rax, rsp
0x180014f52  mov     [rbp+var_18], rax
0x180014f56  xor     r15d, r15d
0x180014f59  mov     rdi, rcx
0x180014f5c  test    rcx, rcx
0x180014f5f  jnz     short loc_180014FAE
0x180014f61  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180014f68  mov     ebx, 80004003h
0x180014f6d  mov     dword ptr [rbp+var_20], ebx
0x180014f70  test    rcx, rcx
0x180014f73  jz      short loc_180014FA4
0x180014f75  lea     edi, [r15+3]
0x180014f79  xor     edx, edx
0x180014f7b  mov     r8d, edi
0x180014f7e  lea     r9, aNoFullPathResu; "No full path result specified"
0x180014f85  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180014f8a  lea     rcx, [rbp+var_20]
0x180014f8e  mov     edx, edi
0x180014f90  lea     r9, [rbp+var_28]
0x180014f94  mov     [rbp+var_28], rcx
0x180014f98  lea     r8, asc_1800233AC; ": {}"
0x180014f9f  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180014fa4  mov     edx, 8Fh
0x180014fa9  jmp     loc_180015145
0x180014fae  mov     rbx, [rcx]
0x180014fb1  test    rbx, rbx
0x180014fb4  jnz     short loc_180015004
0x180014fb6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180014fbd  mov     ebx, 80070057h
0x180014fc2  mov     dword ptr [rbp+var_20], ebx
0x180014fc5  test    rcx, rcx
0x180014fc8  jz      short loc_180014FFA
0x180014fca  mov     edi, 3
0x180014fcf  lea     r9, aInvalidFullPat; "Invalid full path specified"
0x180014fd6  mov     r8d, edi
0x180014fd9  xor     edx, edx
0x180014fdb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180014fe0  lea     rax, [rbp+var_20]
0x180014fe4  mov     edx, edi
0x180014fe6  lea     r9, [rbp+var_28]
0x180014fea  mov     [rbp+var_28], rax
0x180014fee  lea     r8, asc_1800233AC; ": {}"
0x180014ff5  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180014ffa  mov     edx, 90h
0x180014fff  jmp     loc_180015145
0x180015004  movzx   eax, word ptr [rbx]
0x180015007  mov     ecx, 5Ch ; '\'
0x18001500c  sub     ax, 61h ; 'a'
0x180015010  cmp     ax, 19h
0x180015014  jbe     short loc_180015023
0x180015016  movzx   eax, word ptr [rbx]
0x180015019  sub     ax, 41h ; 'A'
0x18001501d  cmp     ax, 19h
0x180015021  ja      short loc_180015057
0x180015023  mov     eax, 3Ah ; ':'
0x180015028  cmp     ax, [rbx+2]
0x18001502c  jnz     short loc_180015057
0x18001502e  cmp     cx, [rbx+4]
0x180015032  jnz     short loc_180015057
0x180015034  lea     rdx, Buf2; "\\\\?\\"
0x18001503b  mov     rcx, rdi
0x18001503e  call    SczAllocPrefixSz
0x180015043  mov     ebx, eax
0x180015045  test    eax, eax
0x180015047  jns     loc_1800150F8
0x18001504d  mov     edx, 99h
0x180015052  jmp     loc_180015145
0x180015057  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001505b  inc     rax
0x18001505e  cmp     [rbx+rax*2], r15w
0x180015063  jnz     short loc_18001505B
0x180015065  cmp     rax, 4
0x180015069  jb      loc_1800150FC
0x18001506f  cmp     cx, [rbx]
0x180015072  jnz     loc_1800150FC
0x180015078  cmp     cx, [rbx+2]
0x18001507c  jnz     short loc_1800150FC
0x18001507e  mov     eax, 3Fh ; '?'
0x180015083  cmp     ax, [rbx+4]
0x180015087  jz      short loc_1800150F8
0x180015089  cmp     cx, [rbx+6]
0x18001508d  jz      short loc_1800150F8
0x18001508f  lea     rdx, [rbp+var_20]
0x180015093  mov     [rbp+var_20], r15
0x180015097  mov     rcx, rbx
0x18001509a  call    SczSize
0x18001509f  mov     esi, eax
0x1800150a1  test    eax, eax
0x1800150a3  jns     short loc_1800150C4
0x1800150a5  mov     rcx, [rbp+30h]; this
0x1800150a9  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x1800150b0  mov     r9d, eax; char *
0x1800150b3  mov     edx, 0A2h; void *
0x1800150b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800150bd  mov     eax, esi
0x1800150bf  jmp     loc_18001515A
0x1800150c4  mov     r8, [rbp+var_20]
0x1800150c8  lea     rdx, [rbx+2]; Src
0x1800150cc  mov     rcx, rbx; void *
0x1800150cf  lea     r8, ds:0FFFFFFFFFFFFFFFEh[r8*2]; Size
0x1800150d7  call    memmove_0
0x1800150dc  lea     rdx, aUnc; "\\\\?\\UNC"
0x1800150e3  mov     rcx, rdi
0x1800150e6  call    SczAllocPrefixSz
0x1800150eb  mov     ebx, eax
0x1800150ed  test    eax, eax
0x1800150ef  jns     short loc_1800150F8
0x1800150f1  mov     edx, 0A6h
0x1800150f6  jmp     short loc_180015145
0x1800150f8  xor     eax, eax
0x1800150fa  jmp     short loc_18001515A
0x1800150fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180015103  mov     ebx, 80070057h
0x180015108  mov     dword ptr [rbp+var_20], ebx
0x18001510b  test    rcx, rcx
0x18001510e  jz      short loc_180015140
0x180015110  mov     edi, 3
0x180015115  lea     r9, aInvalidPathPro; "Invalid path provided to prefix."
0x18001511c  mov     r8d, edi
0x18001511f  xor     edx, edx
0x180015121  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180015126  lea     rax, [rbp+var_20]
0x18001512a  mov     edx, edi
0x18001512c  lea     r9, [rbp+var_28]
0x180015130  mov     [rbp+var_28], rax
0x180015134  lea     r8, asc_1800233AC; ": {}"
0x18001513b  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180015140  mov     edx, 0ABh; void *
0x180015145  mov     rcx, [rbp+30h]; this
0x180015149  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x180015150  mov     r9d, ebx; char *
0x180015153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015158  mov     eax, ebx
0x18001515a  mov     rcx, [rbp+var_18]
0x18001515e  xor     rcx, rsp; StackCookie
0x180015161  call    __security_check_cookie
0x180015166  add     rsp, 48h
0x18001516a  pop     r15
0x18001516c  pop     r14
0x18001516e  pop     rdi
0x18001516f  pop     rsi
0x180015170  pop     rbx
0x180015171  pop     rbp
0x180015172  retn
```
