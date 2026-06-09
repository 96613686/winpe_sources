# PathGetWindowsDirectory

- ea: `0x180014ce0`
- end: `0x180014f32`
- name: `PathGetWindowsDirectory`
- size: `594`
- prototype: `__int64 __fastcall(LPWSTR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180011e10`

## callees

- `0x180001de0`
- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18000ed98`
- `0x18001029c`
- `0x180011248`
- `0x180014ce0`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180014d71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180014e45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180014d71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180014e45`

## string_xrefs

- `0x180014d23`: `No path result specified`
- `0x180014d99`: `Failed to get windows directory.`
- `0x180014e6c`: `Failed to get windows directory.`
- `0x180014d52`: `onecore\base\cbs\util\cbspath.cpp`
- `0x180014dde`: `onecore\base\cbs\util\cbspath.cpp`
- `0x180014e0d`: `onecore\base\cbs\util\cbspath.cpp`
- `0x180014eba`: `onecore\base\cbs\util\cbspath.cpp`

## pseudocode

```c
__int64 __fastcall PathGetWindowsDirectory(LPWSTR *a1)
{
  unsigned int v2; // ebx
  UINT SystemWindowsDirectoryW; // eax
  UINT v5; // edi
  signed int LastError; // ebx
  __int64 v7; // rcx
  unsigned int v8; // eax
  int v9; // eax
  LPWSTR v10; // rbx
  UINT v11; // eax
  signed int v12; // edi
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  unsigned int v17; // edi
  LPWSTR *p_lpBuffer; // [rsp+20h] [rbp-28h] BYREF
  LPWSTR lpBuffer; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]

  lpBuffer = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    LODWORD(lpBuffer) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path result specified");
      p_lpBuffer = &lpBuffer;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&lpBuffer,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&p_lpBuffer);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB4,
      (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
      (const char *)0x80004003LL);
    return v2;
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  v5 = SystemWindowsDirectoryW;
  if ( !SystemWindowsDirectoryW )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get windows directory.");
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      else
        v8 = LastError;
      LODWORD(lpBuffer) = v8;
      p_lpBuffer = &lpBuffer;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        v7,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&p_lpBuffer);
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xB7,
               (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
               (const char *)(unsigned int)LastError);
    return 0;
  }
  v9 = SczAlloc(&lpBuffer, SystemWindowsDirectoryW + 1);
  v2 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
      (const char *)(unsigned int)v9);
    if ( lpBuffer )
      operator delete(lpBuffer - 4);
    return v2;
  }
  v10 = lpBuffer;
  v11 = GetSystemWindowsDirectoryW(lpBuffer, v5);
  if ( v11 )
  {
    if ( v11 >= v5 )
    {
      v15 = 122;
      v16 = 192;
      goto LABEL_25;
    }
    SczEnsureBackslashTerminated(&lpBuffer);
    if ( *a1 )
      operator delete(*a1 - 4);
    *a1 = lpBuffer;
    return 0;
  }
  v12 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get windows directory.");
    if ( v12 > 0 )
      v14 = (unsigned __int16)v12 | 0x80070000;
    else
      v14 = v12;
    LODWORD(lpBuffer) = v14;
    p_lpBuffer = &lpBuffer;
    LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      v13,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
      (__int64)&p_lpBuffer);
  }
  if ( !v12 )
  {
    if ( v10 )
      operator delete(v10 - 4);
    return 0;
  }
  v15 = (unsigned int)v12;
  v16 = 188;
LABEL_25:
  v17 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v16,
          (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)v15);
  if ( v10 )
    operator delete(v10 - 4);
  return v17;
}

```

## disassembly

```asm
0x180014ce0  push    rbp
0x180014ce2  push    rbx
0x180014ce3  push    rsi
0x180014ce4  push    rdi
0x180014ce5  mov     rbp, rsp
0x180014ce8  sub     rsp, 48h
0x180014cec  mov     rax, cs:__security_cookie
0x180014cf3  xor     rax, rsp
0x180014cf6  mov     [rbp+var_18], rax
0x180014cfa  mov     [rbp+lpBuffer], 0
0x180014d02  mov     rsi, rcx
0x180014d05  test    rcx, rcx
0x180014d08  jnz     short loc_180014D6D
0x180014d0a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180014d11  mov     ebx, 80004003h
0x180014d16  mov     dword ptr [rbp+lpBuffer], ebx
0x180014d19  test    rcx, rcx
0x180014d1c  jz      short loc_180014D4E
0x180014d1e  mov     esi, 3
0x180014d23  lea     r9, aNoPathResultSp; "No path result specified"
0x180014d2a  mov     r8d, esi
0x180014d2d  xor     edx, edx
0x180014d2f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180014d34  lea     rcx, [rbp+lpBuffer]
0x180014d38  mov     edx, esi
0x180014d3a  lea     r9, [rbp+var_28]
0x180014d3e  mov     [rbp+var_28], rcx
0x180014d42  lea     r8, asc_1800233AC; ": {}"
0x180014d49  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180014d4e  mov     rcx, [rbp+20h]; this
0x180014d52  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x180014d59  mov     r9d, ebx; char *
0x180014d5c  mov     edx, 0B4h; void *
0x180014d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d66  mov     eax, ebx
0x180014d68  jmp     loc_180014F1D
0x180014d6d  xor     edx, edx; uSize
0x180014d6f  xor     ecx, ecx; lpBuffer
0x180014d71  call    cs:__imp_GetSystemWindowsDirectoryW
0x180014d77  mov     edi, eax
0x180014d79  test    eax, eax
0x180014d7b  jnz     short loc_180014DF7
0x180014d7d  call    cs:__imp_GetLastError
0x180014d83  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180014d8a  mov     ebx, eax
0x180014d8c  test    rcx, rcx
0x180014d8f  jz      short loc_180014DD2
0x180014d91  lea     esi, [rdi+3]
0x180014d94  xor     edx, edx
0x180014d96  mov     r8d, esi
0x180014d99  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x180014da0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180014da5  test    ebx, ebx
0x180014da7  jg      short loc_180014DAD
0x180014da9  mov     eax, ebx
0x180014dab  jmp     short loc_180014DB5
0x180014dad  movzx   eax, bx
0x180014db0  or      eax, 80070000h
0x180014db5  mov     dword ptr [rbp+lpBuffer], eax
0x180014db8  lea     r9, [rbp+var_28]
0x180014dbc  lea     rax, [rbp+lpBuffer]
0x180014dc0  mov     edx, esi
0x180014dc2  lea     r8, a0; ": {0}"
0x180014dc9  mov     [rbp+var_28], rax
0x180014dcd  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180014dd2  test    ebx, ebx
0x180014dd4  jz      loc_180014F1B
0x180014dda  mov     rcx, [rbp+20h]; this
0x180014dde  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x180014de5  mov     r9d, ebx; char *
0x180014de8  mov     edx, 0B7h; void *
0x180014ded  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180014df2  jmp     loc_180014F1D
0x180014df7  lea     edx, [rax+1]
0x180014dfa  lea     rcx, [rbp+lpBuffer]
0x180014dfe  call    SczAlloc
0x180014e03  mov     ebx, eax
0x180014e05  test    eax, eax
0x180014e07  jns     short loc_180014E3C
0x180014e09  mov     rcx, [rbp+20h]; this
0x180014e0d  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x180014e14  mov     r9d, eax; char *
0x180014e17  mov     edx, 0B8h; void *
0x180014e1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e21  mov     rcx, [rbp+lpBuffer]
0x180014e25  test    rcx, rcx
0x180014e28  jz      loc_180014D66
0x180014e2e  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180014e32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014e37  jmp     loc_180014D66
0x180014e3c  mov     rbx, [rbp+lpBuffer]
0x180014e40  mov     edx, edi; uSize
0x180014e42  mov     rcx, rbx; lpBuffer
0x180014e45  call    cs:__imp_GetSystemWindowsDirectoryW
0x180014e4b  test    eax, eax
0x180014e4d  jnz     loc_180014EEA
0x180014e53  call    cs:__imp_GetLastError
0x180014e59  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180014e60  mov     edi, eax
0x180014e62  test    rcx, rcx
0x180014e65  jz      short loc_180014EAA
0x180014e67  mov     esi, 3
0x180014e6c  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x180014e73  mov     r8d, esi
0x180014e76  xor     edx, edx
0x180014e78  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180014e7d  test    edi, edi
0x180014e7f  jg      short loc_180014E85
0x180014e81  mov     eax, edi
0x180014e83  jmp     short loc_180014E8D
0x180014e85  movzx   eax, di
0x180014e88  or      eax, 80070000h
0x180014e8d  mov     dword ptr [rbp+lpBuffer], eax
0x180014e90  lea     r9, [rbp+var_28]
0x180014e94  lea     rax, [rbp+lpBuffer]
0x180014e98  mov     edx, esi
0x180014e9a  lea     r8, a0; ": {0}"
0x180014ea1  mov     [rbp+var_28], rax
0x180014ea5  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180014eaa  test    edi, edi
0x180014eac  jz      short loc_180014EDA
0x180014eae  mov     r9d, edi; char *
0x180014eb1  mov     edx, 0BCh; void *
0x180014eb6  mov     rcx, [rbp+20h]; this
0x180014eba  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x180014ec1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180014ec6  mov     edi, eax
0x180014ec8  test    rbx, rbx
0x180014ecb  jz      short loc_180014ED6
0x180014ecd  lea     rcx, [rbx-8]; Block
0x180014ed1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014ed6  mov     eax, edi
0x180014ed8  jmp     short loc_180014F1D
0x180014eda  test    rbx, rbx
0x180014edd  jz      short loc_180014F1B
0x180014edf  lea     rcx, [rbx-8]; Block
0x180014ee3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014ee8  jmp     short loc_180014F1B
0x180014eea  cmp     eax, edi
0x180014eec  jb      short loc_180014EFA
0x180014eee  mov     r9d, 7Ah ; 'z'
0x180014ef4  lea     edx, [r9+46h]
0x180014ef8  jmp     short loc_180014EB6
0x180014efa  lea     rcx, [rbp+lpBuffer]
0x180014efe  call    SczEnsureBackslashTerminated
0x180014f03  mov     rcx, [rsi]
0x180014f06  test    rcx, rcx
0x180014f09  jz      short loc_180014F14
0x180014f0b  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180014f0f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014f14  mov     rax, [rbp+lpBuffer]
0x180014f18  mov     [rsi], rax
0x180014f1b  xor     eax, eax
0x180014f1d  mov     rcx, [rbp+var_18]
0x180014f21  xor     rcx, rsp; StackCookie
0x180014f24  call    __security_check_cookie
0x180014f29  add     rsp, 48h
0x180014f2d  pop     rdi
0x180014f2e  pop     rsi
0x180014f2f  pop     rbx
0x180014f30  pop     rbp
0x180014f31  retn
```
