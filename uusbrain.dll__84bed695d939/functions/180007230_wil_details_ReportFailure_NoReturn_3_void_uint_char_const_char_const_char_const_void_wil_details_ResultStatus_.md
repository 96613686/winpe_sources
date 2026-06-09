# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180007230`
- end: `0x1800074b2`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800062dc`

## callees

- `0x180004b14`
- `0x180004fe0`
- `0x180005220`
- `0x18000622c`
- `0x180007230`
- `0x1800479c0`
- `0x180047a30`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072e9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000747f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000747f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800073ed`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800073ed`

## pseudocode

```c
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
      g_pfnResultLoggingCallback(v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v18, 0, 0);
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
0x180007230  mov     [rsp-8+arg_18], rbx
0x180007235  push    rbp
0x180007236  push    rsi
0x180007237  push    rdi
0x180007238  push    r12
0x18000723a  push    r13
0x18000723c  push    r14
0x18000723e  push    r15
0x180007240  lea     rbp, [rsp-13C0h]
0x180007248  mov     eax, 14C0h
0x18000724d  call    _alloca_probe
0x180007252  sub     rsp, rax
0x180007255  mov     r14, r8
0x180007258  mov     esi, edx
0x18000725a  mov     rdi, rcx
0x18000725d  mov     r15, [rbp+13F0h+arg_28]
0x180007264  xor     edx, edx; Val
0x180007266  mov     r8d, 98h; Size
0x18000726c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007271  call    memset
0x180007276  nop
0x180007277  xor     r13d, r13d
0x18000727a  mov     [rbp+13F0h+OutputString], r13w
0x180007282  mov     [rbp+13F0h+var_1430], r13b
0x180007286  mov     rbx, [rbp+13F0h+arg_30]
0x18000728d  mov     ecx, [rbx]; this
0x18000728f  mov     [rsp+14F0h+var_14C8], ecx
0x180007293  mov     eax, [rbx+4]
0x180007296  mov     [rsp+14F0h+var_14C4], eax
0x18000729a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000729f  mov     r12d, eax
0x1800072a2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800072aa  mov     ecx, r13d
0x1800072ad  lea     eax, [r13+8]
0x1800072b1  cmp     dword ptr [rbx+8], 1
0x1800072b5  cmovz   ecx, eax
0x1800072b8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800072bc  lea     ecx, [rax-7]
0x1800072bf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800072c7  inc     ecx
0x1800072c9  mov     [rsp+14F0h+var_14C0], ecx
0x1800072cd  mov     rcx, [rbp+13F0h+arg_38]
0x1800072d4  test    rcx, rcx
0x1800072d7  jz      short loc_1800072E4
0x1800072d9  cmp     [rcx], r13w
0x1800072dd  mov     [rsp+14F0h+var_14B8], rcx
0x1800072e2  jnz     short loc_1800072E9
0x1800072e4  mov     [rsp+14F0h+var_14B8], r13
0x1800072e9  call    cs:__imp_GetCurrentThreadId
0x1800072ef  mov     [rsp+14F0h+var_14B0], eax
0x1800072f3  mov     [rsp+14F0h+var_1498], r14
0x1800072f8  mov     [rsp+14F0h+var_1490], esi
0x1800072fc  mov     [rsp+14F0h+var_148C], r12d
0x180007301  mov     [rsp+14F0h+var_14A8], r13
0x180007306  mov     [rsp+14F0h+var_14A0], r13
0x18000730b  mov     [rbp+13F0h+var_1448], r15
0x18000730f  mov     [rbp+13F0h+var_1440], rdi
0x180007313  mov     [rsp+14F0h+var_1488], r13
0x180007318  xorps   xmm0, xmm0
0x18000731b  xor     eax, eax
0x18000731d  movups  [rbp+13F0h+var_1468], xmm0
0x180007321  mov     [rbp+13F0h+var_1458], rax
0x180007325  xorps   xmm1, xmm1
0x180007328  movups  [rsp+14F0h+var_1480], xmm1
0x18000732d  mov     [rbp+13F0h+var_1470], rax
0x180007331  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007338  test    rax, rax
0x18000733b  jz      short loc_180007348
0x18000733d  call    _guard_dispatch_icall
0x180007342  mov     [rbp+13F0h+var_1450], rax
0x180007346  jmp     short loc_18000734C
0x180007348  mov     [rbp+13F0h+var_1450], r13
0x18000734c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007353  test    rax, rax
0x180007356  jz      short loc_180007362
0x180007358  lea     rcx, [rsp+14F0h+var_14D0]
0x18000735d  call    _guard_dispatch_icall
0x180007362  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007369  test    rax, rax
0x18000736c  jz      short loc_180007382
0x18000736e  mov     r8d, 400h
0x180007374  lea     rdx, [rbp+13F0h+var_1430]
0x180007378  lea     rcx, [rsp+14F0h+var_14D0]
0x18000737d  call    _guard_dispatch_icall
0x180007382  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007389  test    rax, rax
0x18000738c  jz      short loc_180007398
0x18000738e  lea     rcx, [rsp+14F0h+var_14D0]
0x180007393  call    _guard_dispatch_icall
0x180007398  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000739f  test    rax, rax
0x1800073a2  jz      short loc_1800073B5
0x1800073a4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800073a9  jnz     short loc_1800073B5
0x1800073ab  lea     rcx, [rsp+14F0h+var_14D0]
0x1800073b0  call    _guard_dispatch_icall
0x1800073b5  cmp     [rsp+14F0h+var_14C8], r13d
0x1800073ba  jl      short loc_1800073CE
0x1800073bc  mov     ecx, 8000FFFFh; this
0x1800073c1  mov     [rsp+14F0h+var_14C8], ecx
0x1800073c5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800073ca  mov     [rsp+14F0h+var_14C4], eax
0x1800073ce  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800073d5  jnz     short loc_1800073FF
0x1800073d7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800073de  test    rax, rax
0x1800073e1  jz      short loc_1800073ED
0x1800073e3  call    _guard_dispatch_icall
0x1800073e8  movzx   ecx, al
0x1800073eb  jmp     short loc_1800073FB
0x1800073ed  call    cs:__imp_IsDebuggerPresent
0x1800073f3  mov     ecx, r13d
0x1800073f6  test    eax, eax
0x1800073f8  setnz   cl
0x1800073fb  test    ecx, ecx
0x1800073fd  jz      short loc_180007406
0x1800073ff  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007404  jz      short loc_18000742C
0x180007406  mov     rax, cs:g_pfnResultLoggingCallback
0x18000740d  test    rax, rax
0x180007410  jz      short loc_180007485
0x180007412  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007419  jnz     short loc_180007485
0x18000741b  xor     r8d, r8d
0x18000741e  xor     edx, edx
0x180007420  lea     rcx, [rsp+14F0h+var_14D0]
0x180007425  call    _guard_dispatch_icall
0x18000742a  jmp     short loc_180007485
0x18000742c  mov     ebx, 800h
0x180007431  mov     rax, cs:g_pfnResultLoggingCallback
0x180007438  test    rax, rax
0x18000743b  jz      short loc_18000745A
0x18000743d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007444  jnz     short loc_18000745A
0x180007446  mov     r8d, ebx
0x180007449  lea     rdx, [rbp+13F0h+OutputString]
0x180007450  lea     rcx, [rsp+14F0h+var_14D0]
0x180007455  call    _guard_dispatch_icall
0x18000745a  cmp     [rbp+13F0h+OutputString], r13w
0x180007462  jnz     short loc_180007478
0x180007464  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007469  mov     rdx, rbx; wchar_t *
0x18000746c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007473  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180007478  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000747f  call    cs:__imp_OutputDebugStringW
0x180007485  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000748a  jnz     short loc_180007495
0x18000748c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180007493  jz      short loc_1800074A7
0x180007495  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000749c  test    rax, rax
0x18000749f  jz      short loc_1800074A7
0x1800074a1  call    _guard_dispatch_icall
0x1800074a6  nop
0x1800074a7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800074ac  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
