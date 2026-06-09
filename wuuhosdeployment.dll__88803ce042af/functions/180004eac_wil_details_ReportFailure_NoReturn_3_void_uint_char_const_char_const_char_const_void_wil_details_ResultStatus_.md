# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180004eac`
- end: `0x18000512e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000382c`

## callees

- `0x180002064`
- `0x180002530`
- `0x180002770`
- `0x18000377c`
- `0x180004eac`
- `0x1800491f0`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f65`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050fb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005069`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005069`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        __int64 a7,
        _WORD *a8)
{
  int v11; // edx
  unsigned int v12; // r12d
  int v13; // ecx
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v17; // r9
  unsigned __int64 v18[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v18, 0, 0x98u);
  OutputString[0] = 0;
  v19[0] = 0;
  v18[1] = *(_QWORD *)a7;
  v12 = wil::details::RecordFailFast((wil::details *)LODWORD(v18[1]), v11);
  LODWORD(v18[0]) = 3;
  v13 = 0;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v13 = 8;
  HIDWORD(v18[0]) = v13;
  LODWORD(v18[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v18[3] = (unsigned __int64)a8, v14) )
    v18[3] = 0;
  LODWORD(v18[4]) = GetCurrentThreadId();
  v18[7] = a3;
  v18[8] = __PAIR64__(v12, a2);
  v18[5] = 0;
  v18[6] = 0;
  v18[17] = a6;
  v18[18] = a1;
  memset(&v18[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v18[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v18[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v18, v19, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v18);
  if ( wil::details::g_pfnOriginateCallback && (v18[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v18);
  if ( SLODWORD(v18[1]) >= 0 )
  {
    LODWORD(v18[1]) = -2147418113;
    HIDWORD(v18[1]) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v18[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v18, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v18, 0, 0, v17);
  }
  if ( (v18[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
  wil::details::WilFailFast((wil::details *)v18, v15);
}

```

## disassembly

```asm
0x180004eac  mov     [rsp-8+arg_18], rbx
0x180004eb1  push    rbp
0x180004eb2  push    rsi
0x180004eb3  push    rdi
0x180004eb4  push    r12
0x180004eb6  push    r13
0x180004eb8  push    r14
0x180004eba  push    r15
0x180004ebc  lea     rbp, [rsp-13C0h]
0x180004ec4  mov     eax, 14C0h
0x180004ec9  call    _alloca_probe
0x180004ece  sub     rsp, rax
0x180004ed1  mov     r14, r8
0x180004ed4  mov     esi, edx
0x180004ed6  mov     rdi, rcx
0x180004ed9  mov     r15, [rbp+13F0h+arg_28]
0x180004ee0  xor     edx, edx; Val
0x180004ee2  mov     r8d, 98h; Size
0x180004ee8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004eed  call    memset
0x180004ef2  nop
0x180004ef3  xor     r13d, r13d
0x180004ef6  mov     [rbp+13F0h+OutputString], r13w
0x180004efe  mov     [rbp+13F0h+var_1430], r13b
0x180004f02  mov     rbx, [rbp+13F0h+arg_30]
0x180004f09  mov     ecx, [rbx]; this
0x180004f0b  mov     [rsp+14F0h+var_14C8], ecx
0x180004f0f  mov     eax, [rbx+4]
0x180004f12  mov     [rsp+14F0h+var_14C4], eax
0x180004f16  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004f1b  mov     r12d, eax
0x180004f1e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180004f26  mov     ecx, r13d
0x180004f29  lea     eax, [r13+8]
0x180004f2d  cmp     dword ptr [rbx+8], 1
0x180004f31  cmovz   ecx, eax
0x180004f34  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004f38  lea     ecx, [rax-7]
0x180004f3b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f43  inc     ecx
0x180004f45  mov     [rsp+14F0h+var_14C0], ecx
0x180004f49  mov     rcx, [rbp+13F0h+arg_38]
0x180004f50  test    rcx, rcx
0x180004f53  jz      short loc_180004F60
0x180004f55  cmp     [rcx], r13w
0x180004f59  mov     [rsp+14F0h+var_14B8], rcx
0x180004f5e  jnz     short loc_180004F65
0x180004f60  mov     [rsp+14F0h+var_14B8], r13
0x180004f65  call    cs:__imp_GetCurrentThreadId
0x180004f6b  mov     [rsp+14F0h+var_14B0], eax
0x180004f6f  mov     [rsp+14F0h+var_1498], r14
0x180004f74  mov     [rsp+14F0h+var_1490], esi
0x180004f78  mov     [rsp+14F0h+var_148C], r12d
0x180004f7d  mov     [rsp+14F0h+var_14A8], r13
0x180004f82  mov     [rsp+14F0h+var_14A0], r13
0x180004f87  mov     [rbp+13F0h+var_1448], r15
0x180004f8b  mov     [rbp+13F0h+var_1440], rdi
0x180004f8f  mov     [rsp+14F0h+var_1488], r13
0x180004f94  xorps   xmm0, xmm0
0x180004f97  xor     eax, eax
0x180004f99  movups  [rbp+13F0h+var_1468], xmm0
0x180004f9d  mov     [rbp+13F0h+var_1458], rax
0x180004fa1  xorps   xmm1, xmm1
0x180004fa4  movups  [rsp+14F0h+var_1480], xmm1
0x180004fa9  mov     [rbp+13F0h+var_1470], rax
0x180004fad  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004fb4  test    rax, rax
0x180004fb7  jz      short loc_180004FC4
0x180004fb9  call    _guard_dispatch_icall
0x180004fbe  mov     [rbp+13F0h+var_1450], rax
0x180004fc2  jmp     short loc_180004FC8
0x180004fc4  mov     [rbp+13F0h+var_1450], r13
0x180004fc8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004fcf  test    rax, rax
0x180004fd2  jz      short loc_180004FDE
0x180004fd4  lea     rcx, [rsp+14F0h+var_14D0]
0x180004fd9  call    _guard_dispatch_icall
0x180004fde  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004fe5  test    rax, rax
0x180004fe8  jz      short loc_180004FFE
0x180004fea  mov     r8d, 400h
0x180004ff0  lea     rdx, [rbp+13F0h+var_1430]
0x180004ff4  lea     rcx, [rsp+14F0h+var_14D0]
0x180004ff9  call    _guard_dispatch_icall
0x180004ffe  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005005  test    rax, rax
0x180005008  jz      short loc_180005014
0x18000500a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000500f  call    _guard_dispatch_icall
0x180005014  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000501b  test    rax, rax
0x18000501e  jz      short loc_180005031
0x180005020  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005025  jnz     short loc_180005031
0x180005027  lea     rcx, [rsp+14F0h+var_14D0]
0x18000502c  call    _guard_dispatch_icall
0x180005031  cmp     [rsp+14F0h+var_14C8], r13d
0x180005036  jl      short loc_18000504A
0x180005038  mov     ecx, 8000FFFFh; this
0x18000503d  mov     [rsp+14F0h+var_14C8], ecx
0x180005041  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005046  mov     [rsp+14F0h+var_14C4], eax
0x18000504a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005051  jnz     short loc_18000507B
0x180005053  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000505a  test    rax, rax
0x18000505d  jz      short loc_180005069
0x18000505f  call    _guard_dispatch_icall
0x180005064  movzx   ecx, al
0x180005067  jmp     short loc_180005077
0x180005069  call    cs:__imp_IsDebuggerPresent
0x18000506f  mov     ecx, r13d
0x180005072  test    eax, eax
0x180005074  setnz   cl
0x180005077  test    ecx, ecx
0x180005079  jz      short loc_180005082
0x18000507b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005080  jz      short loc_1800050A8
0x180005082  mov     rax, cs:g_pfnResultLoggingCallback
0x180005089  test    rax, rax
0x18000508c  jz      short loc_180005101
0x18000508e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005095  jnz     short loc_180005101
0x180005097  xor     r8d, r8d
0x18000509a  xor     edx, edx
0x18000509c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800050a1  call    _guard_dispatch_icall
0x1800050a6  jmp     short loc_180005101
0x1800050a8  mov     ebx, 800h
0x1800050ad  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050b4  test    rax, rax
0x1800050b7  jz      short loc_1800050D6
0x1800050b9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800050c0  jnz     short loc_1800050D6
0x1800050c2  mov     r8d, ebx
0x1800050c5  lea     rdx, [rbp+13F0h+OutputString]
0x1800050cc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800050d1  call    _guard_dispatch_icall
0x1800050d6  cmp     [rbp+13F0h+OutputString], r13w
0x1800050de  jnz     short loc_1800050F4
0x1800050e0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800050e5  mov     rdx, rbx; wchar_t *
0x1800050e8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800050ef  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800050f4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800050fb  call    cs:__imp_OutputDebugStringW
0x180005101  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005106  jnz     short loc_180005111
0x180005108  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000510f  jz      short loc_180005123
0x180005111  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005118  test    rax, rax
0x18000511b  jz      short loc_180005123
0x18000511d  call    _guard_dispatch_icall
0x180005122  nop
0x180005123  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005128  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
