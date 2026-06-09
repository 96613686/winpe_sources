# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000a294`
- end: `0x18000a594`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180009cc0`

## callees

- `0x180007888`
- `0x180007d2c`
- `0x180007f90`
- `0x180008c90`
- `0x180008ef0`
- `0x180009bd0`
- `0x18000a294`
- `0x1800dd930`
- `0x1800e45c0`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3ad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a531`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a531`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a4a1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a4a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<2>(
        unsigned __int64 a1,
        int a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  unsigned int v17; // ebx
  bool v18; // zf
  const struct wil::FailureInfo *v19; // rdx
  wil::details::in1diag3 *v20; // rcx
  const struct wil::FailureInfo *v21; // r9
  int IsDebuggerPresent; // ecx
  wil::details *v23; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v24[20]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset(v24, 0, 0x98u);
  OutputString[0] = 0;
  v25[0] = 0;
  v15 = *a7;
  LODWORD(v24[1]) = v15;
  HIDWORD(v24[1]) = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v23) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v23);
    LODWORD(v24[1]) = -2147024228;
    HIDWORD(v24[1]) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  LODWORD(v24[0]) = 2;
  HIDWORD(v24[0]) = a10;
  if ( a7[2] == 1 )
    HIDWORD(v24[0]) = a10 | 8;
  LODWORD(v24[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v24[3] = (unsigned __int64)a8, v18) )
    v24[3] = 0;
  LODWORD(v24[4]) = GetCurrentThreadId();
  v24[7] = a3;
  v24[8] = __PAIR64__(v17, a2);
  v24[5] = a5;
  v24[6] = a4;
  v24[17] = a6;
  v24[18] = a1;
  memset(&v24[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v24[16] = wil::details::g_pfnGetModuleName();
  else
    v24[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v24);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v24, v25, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v24);
  if ( wil::details::g_pfnOriginateCallback && (v24[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v24);
  if ( SLODWORD(v24[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
         IsDebuggerPresent))
    && (v24[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v24, OutputString, 2048, v21);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v24, v21);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v24, 0, 0, v21);
  }
  if ( ((v24[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v24[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v24, v19);
}

```

## disassembly

```asm
0x18000a294  push    rbp
0x18000a296  push    rbx
0x18000a297  push    rsi
0x18000a298  push    rdi
0x18000a299  push    r12
0x18000a29b  push    r13
0x18000a29d  push    r14
0x18000a29f  push    r15
0x18000a2a1  lea     rbp, [rsp-1408h]
0x18000a2a9  mov     eax, 1508h
0x18000a2ae  call    _alloca_probe
0x18000a2b3  sub     rsp, rax
0x18000a2b6  mov     rax, cs:__security_cookie
0x18000a2bd  xor     rax, rsp
0x18000a2c0  mov     [rbp+1440h+var_50], rax
0x18000a2c7  mov     r12, r9
0x18000a2ca  mov     r15, r8
0x18000a2cd  mov     r14d, edx
0x18000a2d0  mov     rsi, rcx
0x18000a2d3  mov     r13, [rbp+1440h+arg_20]
0x18000a2da  mov     rax, [rbp+1440h+arg_28]
0x18000a2e1  mov     [rsp+1540h+var_1500], rax
0x18000a2e6  xor     edx, edx; Val
0x18000a2e8  mov     r8d, 98h; Size
0x18000a2ee  lea     rcx, [rsp+1540h+var_14F0]; void *
0x18000a2f3  call    memset
0x18000a2f8  nop
0x18000a2f9  xor     ecx, ecx
0x18000a2fb  mov     [rbp+1440h+OutputString], cx
0x18000a302  mov     [rbp+1440h+var_1450], cl
0x18000a305  mov     rdi, [rbp+1440h+arg_30]
0x18000a30c  mov     ebx, [rdi]
0x18000a30e  mov     [rsp+1540h+var_14E8], ebx
0x18000a312  mov     eax, [rdi+4]
0x18000a315  mov     [rsp+1540h+var_14E4], eax
0x18000a319  test    ebx, ebx
0x18000a31b  js      short loc_18000A355
0x18000a31d  mov     ebx, 8007029Ch
0x18000a322  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x18000a326  mov     rax, [rsp+1540h+var_1500]
0x18000a32b  mov     [rsp+1540h+var_1518], rax; __int64
0x18000a330  mov     [rsp+1540h+var_1520], r13; __int64
0x18000a335  mov     r9, r12; int
0x18000a338  mov     r8, r15; int
0x18000a33b  mov     edx, r14d; int
0x18000a33e  mov     rcx, rsi; int
0x18000a341  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a346  mov     [rsp+1540h+var_14E8], ebx
0x18000a34a  mov     ecx, ebx; this
0x18000a34c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a351  mov     [rsp+1540h+var_14E4], eax
0x18000a355  mov     ecx, ebx; this
0x18000a357  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a35c  mov     ebx, eax
0x18000a35e  mov     dword ptr [rsp+1540h+var_14F0], 2
0x18000a366  mov     ecx, [rbp+1440h+arg_48]
0x18000a36c  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x18000a370  cmp     dword ptr [rdi+8], 1
0x18000a374  jnz     short loc_18000A37D
0x18000a376  or      ecx, 8
0x18000a379  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x18000a37d  mov     ecx, 1
0x18000a382  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a38a  inc     ecx
0x18000a38c  mov     [rsp+1540h+var_14E0], ecx
0x18000a390  mov     rax, [rbp+1440h+arg_38]
0x18000a397  xor     edi, edi
0x18000a399  test    rax, rax
0x18000a39c  jz      short loc_18000A3A8
0x18000a39e  cmp     [rax], di
0x18000a3a1  mov     [rsp+1540h+var_14D8], rax
0x18000a3a6  jnz     short loc_18000A3AD
0x18000a3a8  mov     [rsp+1540h+var_14D8], rdi
0x18000a3ad  call    cs:__imp_GetCurrentThreadId
0x18000a3b3  mov     [rsp+1540h+var_14D0], eax
0x18000a3b7  mov     [rbp+1440h+var_14B8], r15
0x18000a3bb  mov     [rbp+1440h+var_14B0], r14d
0x18000a3bf  mov     [rbp+1440h+var_14AC], ebx
0x18000a3c2  mov     [rsp+1540h+var_14C8], r13
0x18000a3c7  mov     [rbp+1440h+var_14C0], r12
0x18000a3cb  mov     rax, [rsp+1540h+var_1500]
0x18000a3d0  mov     [rbp+1440h+var_1468], rax
0x18000a3d4  mov     [rbp+1440h+var_1460], rsi
0x18000a3d8  mov     [rbp+1440h+var_14A8], rdi
0x18000a3dc  xorps   xmm0, xmm0
0x18000a3df  xor     eax, eax
0x18000a3e1  movups  [rbp+1440h+var_1488], xmm0
0x18000a3e5  mov     [rbp+1440h+var_1478], rax
0x18000a3e9  xorps   xmm1, xmm1
0x18000a3ec  movups  [rbp+1440h+var_14A0], xmm1
0x18000a3f0  mov     [rbp+1440h+var_1490], rax
0x18000a3f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a3fb  test    rax, rax
0x18000a3fe  jz      short loc_18000A40B
0x18000a400  call    _guard_dispatch_icall
0x18000a405  mov     [rbp+1440h+var_1470], rax
0x18000a409  jmp     short loc_18000A40F
0x18000a40b  mov     [rbp+1440h+var_1470], rdi
0x18000a40f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a416  test    rax, rax
0x18000a419  jz      short loc_18000A425
0x18000a41b  lea     rcx, [rsp+1540h+var_14F0]
0x18000a420  call    _guard_dispatch_icall
0x18000a425  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a42c  test    rax, rax
0x18000a42f  jz      short loc_18000A445
0x18000a431  mov     r8d, 400h
0x18000a437  lea     rdx, [rbp+1440h+var_1450]
0x18000a43b  lea     rcx, [rsp+1540h+var_14F0]
0x18000a440  call    _guard_dispatch_icall
0x18000a445  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a44c  test    rax, rax
0x18000a44f  jz      short loc_18000A45B
0x18000a451  lea     rcx, [rsp+1540h+var_14F0]
0x18000a456  call    _guard_dispatch_icall
0x18000a45b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a462  test    rax, rax
0x18000a465  jz      short loc_18000A478
0x18000a467  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x18000a46c  jnz     short loc_18000A478
0x18000a46e  lea     rcx, [rsp+1540h+var_14F0]
0x18000a473  call    _guard_dispatch_icall
0x18000a478  cmp     [rsp+1540h+var_14E8], edi
0x18000a47c  jge     loc_18000A58E
0x18000a482  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a489  jnz     short loc_18000A4B2
0x18000a48b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a492  test    rax, rax
0x18000a495  jz      short loc_18000A4A1
0x18000a497  call    _guard_dispatch_icall
0x18000a49c  movzx   ecx, al
0x18000a49f  jmp     short loc_18000A4AE
0x18000a4a1  call    cs:__imp_IsDebuggerPresent
0x18000a4a7  mov     ecx, edi
0x18000a4a9  test    eax, eax
0x18000a4ab  setnz   cl
0x18000a4ae  test    ecx, ecx
0x18000a4b0  jz      short loc_18000A4B9
0x18000a4b2  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x18000a4b7  jz      short loc_18000A4DF
0x18000a4b9  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a4c0  test    rax, rax
0x18000a4c3  jz      short loc_18000A537
0x18000a4c5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a4cc  jnz     short loc_18000A537
0x18000a4ce  xor     r8d, r8d
0x18000a4d1  xor     edx, edx
0x18000a4d3  lea     rcx, [rsp+1540h+var_14F0]
0x18000a4d8  call    _guard_dispatch_icall
0x18000a4dd  jmp     short loc_18000A537
0x18000a4df  mov     ebx, 800h
0x18000a4e4  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a4eb  test    rax, rax
0x18000a4ee  jz      short loc_18000A50D
0x18000a4f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a4f7  jnz     short loc_18000A50D
0x18000a4f9  mov     r8d, ebx
0x18000a4fc  lea     rdx, [rbp+1440h+OutputString]
0x18000a503  lea     rcx, [rsp+1540h+var_14F0]
0x18000a508  call    _guard_dispatch_icall
0x18000a50d  cmp     [rbp+1440h+OutputString], di
0x18000a514  jnz     short loc_18000A52A
0x18000a516  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x18000a51b  mov     rdx, rbx; wchar_t *
0x18000a51e  lea     rcx, [rbp+1440h+OutputString]; this
0x18000a525  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000a52a  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x18000a531  call    cs:__imp_OutputDebugStringW
0x18000a537  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x18000a53c  jnz     short loc_18000A547
0x18000a53e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a545  jz      short loc_18000A559
0x18000a547  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a54e  test    rax, rax
0x18000a551  jz      short loc_18000A559
0x18000a553  call    _guard_dispatch_icall
0x18000a558  nop
0x18000a559  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x18000a55e  jnz     short loc_18000A583
0x18000a560  mov     rcx, [rbp+1440h+var_50]
0x18000a567  xor     rcx, rsp; StackCookie
0x18000a56a  call    __security_check_cookie
0x18000a56f  add     rsp, 1508h
0x18000a576  pop     r15
0x18000a578  pop     r14
0x18000a57a  pop     r13
0x18000a57c  pop     r12
0x18000a57e  pop     rdi
0x18000a57f  pop     rsi
0x18000a580  pop     rbx
0x18000a581  pop     rbp
0x18000a582  retn
0x18000a583  lea     rcx, [rsp+1540h+var_14F0]; this
0x18000a588  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000a58e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
