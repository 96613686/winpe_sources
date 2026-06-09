# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180026d90`
- end: `0x18002705e`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180027064`

## callees

- `0x180004b14`
- `0x180004f80`
- `0x180005c68`
- `0x18000622c`
- `0x180006490`
- `0x180026d90`
- `0x1800479c0`
- `0x180047a30`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026e51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026e51`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026ff2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026ff2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026f4e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026f4e`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        _WORD *a8)
{
  bool v11; // di
  unsigned int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  bool v15; // zf
  const struct wil::FailureInfo *v16; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v18; // r9
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  unsigned __int64 v21[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v22[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset(v21, 0, 0x98u);
  OutputString[0] = 0;
  v22[0] = 0;
  v21[1] = *a7;
  v12 = wil::details::RecordException((wil::details *)LODWORD(v21[1]), (int)a7);
  LODWORD(v21[0]) = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  HIDWORD(v21[0]) = v13;
  LODWORD(v21[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v15 = *a8 == 0, v21[3] = (unsigned __int64)a8, v15) )
    v21[3] = 0;
  LODWORD(v21[4]) = GetCurrentThreadId();
  v21[7] = a3;
  v21[8] = __PAIR64__(v12, a2);
  v21[5] = 0;
  v21[6] = 0;
  v21[17] = a6;
  v21[18] = a1;
  memset(&v21[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v21[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v21[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v21, v22, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v21[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v21);
  if ( SLODWORD(v21[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (IsDebuggerPresent = ::IsDebuggerPresent())
      : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
        !(_DWORD)IsDebuggerPresent)
    || (v19 = 1, (v21[0] & 0x200000000LL) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v21, v18);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v21, 0, 0);
  }
  if ( ((v21[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v21[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v21, v16);
  if ( v11 )
    ((void (__fastcall *)(unsigned __int64 *, WCHAR *))g_pfnThrowPlatformException)(v21, OutputString);
  wil::ThrowResultException((wil *)v21, v16);
  wil::details::WilFailFast((wil::details *)v21, v20);
}

```

## disassembly

```asm
0x180026d90  mov     [rsp-8+arg_18], rbx
0x180026d95  push    rbp
0x180026d96  push    rsi
0x180026d97  push    rdi
0x180026d98  push    r12
0x180026d9a  push    r13
0x180026d9c  push    r14
0x180026d9e  push    r15
0x180026da0  lea     rbp, [rsp-13C0h]
0x180026da8  mov     eax, 14C0h
0x180026dad  call    _alloca_probe
0x180026db2  sub     rsp, rax
0x180026db5  mov     r14, r8
0x180026db8  mov     esi, edx
0x180026dba  mov     rbx, rcx
0x180026dbd  mov     r15, [rbp+13F0h+arg_28]
0x180026dc4  xor     r13d, r13d
0x180026dc7  cmp     cs:g_pfnThrowPlatformException, r13
0x180026dce  setnz   dil
0x180026dd2  xor     edx, edx; Val
0x180026dd4  mov     r8d, 98h; Size
0x180026dda  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180026ddf  call    memset
0x180026de4  nop
0x180026de5  mov     [rbp+13F0h+OutputString], r13w
0x180026ded  mov     [rbp+13F0h+var_1430], r13b
0x180026df1  mov     rdx, [rbp+13F0h+arg_30]; int
0x180026df8  mov     ecx, [rdx]; this
0x180026dfa  mov     [rsp+14F0h+var_14C8], ecx
0x180026dfe  mov     eax, [rdx+4]
0x180026e01  mov     [rsp+14F0h+var_14C4], eax
0x180026e05  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180026e0a  mov     r12d, eax
0x180026e0d  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180026e12  mov     ecx, r13d
0x180026e15  lea     eax, [r13+8]
0x180026e19  cmp     dword ptr [rdx+8], 1
0x180026e1d  cmovz   ecx, eax
0x180026e20  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180026e24  lea     ecx, [rax-7]
0x180026e27  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180026e2f  inc     ecx
0x180026e31  mov     [rsp+14F0h+var_14C0], ecx
0x180026e35  mov     rcx, [rbp+13F0h+arg_38]
0x180026e3c  test    rcx, rcx
0x180026e3f  jz      short loc_180026E4C
0x180026e41  cmp     [rcx], r13w
0x180026e45  mov     [rsp+14F0h+var_14B8], rcx
0x180026e4a  jnz     short loc_180026E51
0x180026e4c  mov     [rsp+14F0h+var_14B8], r13
0x180026e51  call    cs:__imp_GetCurrentThreadId
0x180026e57  mov     [rsp+14F0h+var_14B0], eax
0x180026e5b  mov     [rsp+14F0h+var_1498], r14
0x180026e60  mov     [rsp+14F0h+var_1490], esi
0x180026e64  mov     [rsp+14F0h+var_148C], r12d
0x180026e69  mov     [rsp+14F0h+var_14A8], r13
0x180026e6e  mov     [rsp+14F0h+var_14A0], r13
0x180026e73  mov     [rbp+13F0h+var_1448], r15
0x180026e77  mov     [rbp+13F0h+var_1440], rbx
0x180026e7b  mov     [rsp+14F0h+var_1488], r13
0x180026e80  xorps   xmm0, xmm0
0x180026e83  xor     eax, eax
0x180026e85  movups  [rbp+13F0h+var_1468], xmm0
0x180026e89  mov     [rbp+13F0h+var_1458], rax
0x180026e8d  xorps   xmm1, xmm1
0x180026e90  movups  [rsp+14F0h+var_1480], xmm1
0x180026e95  mov     [rbp+13F0h+var_1470], rax
0x180026e99  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180026ea0  test    rax, rax
0x180026ea3  jz      short loc_180026EB0
0x180026ea5  call    _guard_dispatch_icall
0x180026eaa  mov     [rbp+13F0h+var_1450], rax
0x180026eae  jmp     short loc_180026EB4
0x180026eb0  mov     [rbp+13F0h+var_1450], r13
0x180026eb4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180026ebb  test    rax, rax
0x180026ebe  jz      short loc_180026ECA
0x180026ec0  lea     rcx, [rsp+14F0h+var_14D0]
0x180026ec5  call    _guard_dispatch_icall
0x180026eca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180026ed1  test    rax, rax
0x180026ed4  jz      short loc_180026EEA
0x180026ed6  mov     r8d, 400h
0x180026edc  lea     rdx, [rbp+13F0h+var_1430]
0x180026ee0  lea     rcx, [rsp+14F0h+var_14D0]
0x180026ee5  call    _guard_dispatch_icall
0x180026eea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026ef1  test    rax, rax
0x180026ef4  jz      short loc_180026F00
0x180026ef6  lea     rcx, [rsp+14F0h+var_14D0]
0x180026efb  call    _guard_dispatch_icall
0x180026f00  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026f07  test    rax, rax
0x180026f0a  jz      short loc_180026F22
0x180026f0c  test    dil, dil
0x180026f0f  jnz     short loc_180026F22
0x180026f11  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180026f16  jnz     short loc_180026F22
0x180026f18  lea     rcx, [rsp+14F0h+var_14D0]
0x180026f1d  call    _guard_dispatch_icall
0x180026f22  cmp     [rsp+14F0h+var_14C8], r13d
0x180026f27  jl      short loc_180026F2F
0x180026f29  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180026f2f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180026f36  jnz     short loc_180026F60
0x180026f38  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180026f3f  test    rax, rax
0x180026f42  jz      short loc_180026F4E
0x180026f44  call    _guard_dispatch_icall
0x180026f49  movzx   ecx, al
0x180026f4c  jmp     short loc_180026F5C
0x180026f4e  call    cs:__imp_IsDebuggerPresent
0x180026f54  mov     ecx, r13d
0x180026f57  test    eax, eax
0x180026f59  setnz   cl
0x180026f5c  test    ecx, ecx
0x180026f5e  jz      short loc_180026F69
0x180026f60  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180026f65  mov     bl, 1
0x180026f67  jz      short loc_180026F6C
0x180026f69  mov     bl, r13b
0x180026f6c  test    dil, dil
0x180026f6f  jnz     short loc_180026F9B
0x180026f71  test    bl, bl
0x180026f73  jnz     short loc_180026F9B
0x180026f75  mov     rax, cs:g_pfnResultLoggingCallback
0x180026f7c  test    rax, rax
0x180026f7f  jz      short loc_180026FF8
0x180026f81  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180026f88  jnz     short loc_180026FF8
0x180026f8a  xor     r8d, r8d
0x180026f8d  xor     edx, edx
0x180026f8f  lea     rcx, [rsp+14F0h+var_14D0]
0x180026f94  call    _guard_dispatch_icall
0x180026f99  jmp     short loc_180026FF8
0x180026f9b  mov     esi, 800h
0x180026fa0  mov     rax, cs:g_pfnResultLoggingCallback
0x180026fa7  test    rax, rax
0x180026faa  jz      short loc_180026FC9
0x180026fac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180026fb3  jnz     short loc_180026FC9
0x180026fb5  mov     r8d, esi
0x180026fb8  lea     rdx, [rbp+13F0h+OutputString]
0x180026fbf  lea     rcx, [rsp+14F0h+var_14D0]
0x180026fc4  call    _guard_dispatch_icall
0x180026fc9  cmp     [rbp+13F0h+OutputString], r13w
0x180026fd1  jnz     short loc_180026FE7
0x180026fd3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180026fd8  mov     rdx, rsi; wchar_t *
0x180026fdb  lea     rcx, [rbp+13F0h+OutputString]; this
0x180026fe2  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180026fe7  test    bl, bl
0x180026fe9  jz      short loc_180026FF8
0x180026feb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180026ff2  call    cs:__imp_OutputDebugStringW
0x180026ff8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180026ffd  jnz     short loc_180027008
0x180026fff  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180027006  jz      short loc_18002701A
0x180027008  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002700f  test    rax, rax
0x180027012  jz      short loc_18002701A
0x180027014  call    _guard_dispatch_icall
0x180027019  nop
0x18002701a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002701f  jz      short loc_18002702C
0x180027021  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180027026  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002702c  test    dil, dil
0x18002702f  jz      short loc_180027049
0x180027031  lea     rdx, [rbp+13F0h+OutputString]
0x180027038  lea     rcx, [rsp+14F0h+var_14D0]
0x18002703d  mov     rax, cs:g_pfnThrowPlatformException
0x180027044  call    _guard_dispatch_icall
0x180027049  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002704e  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180027053  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180027058  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
