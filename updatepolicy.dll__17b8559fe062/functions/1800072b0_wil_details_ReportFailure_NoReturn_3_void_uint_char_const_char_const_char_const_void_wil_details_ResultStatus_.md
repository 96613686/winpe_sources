# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800072b0`
- end: `0x180007532`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180007538`

## callees

- `0x180006ab0`
- `0x180006bec`
- `0x180007200`
- `0x1800072b0`
- `0x180007570`
- `0x1800153c0`
- `0x180015430`
- `0x1800154b0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000746d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000746d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800074ff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800074ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007369`

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
0x1800072b0  mov     [rsp-8+arg_18], rbx
0x1800072b5  push    rbp
0x1800072b6  push    rsi
0x1800072b7  push    rdi
0x1800072b8  push    r12
0x1800072ba  push    r13
0x1800072bc  push    r14
0x1800072be  push    r15
0x1800072c0  lea     rbp, [rsp-13C0h]
0x1800072c8  mov     eax, 14C0h
0x1800072cd  call    _alloca_probe
0x1800072d2  sub     rsp, rax
0x1800072d5  mov     r14, r8
0x1800072d8  mov     esi, edx
0x1800072da  mov     rdi, rcx
0x1800072dd  mov     r15, [rbp+13F0h+arg_28]
0x1800072e4  xor     edx, edx; Val
0x1800072e6  mov     r8d, 98h; Size
0x1800072ec  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800072f1  call    memset
0x1800072f6  nop
0x1800072f7  xor     r13d, r13d
0x1800072fa  mov     [rbp+13F0h+OutputString], r13w
0x180007302  mov     [rbp+13F0h+var_1430], r13b
0x180007306  mov     rbx, [rbp+13F0h+arg_30]
0x18000730d  mov     ecx, [rbx]; this
0x18000730f  mov     [rsp+14F0h+var_14C8], ecx
0x180007313  mov     eax, [rbx+4]
0x180007316  mov     [rsp+14F0h+var_14C4], eax
0x18000731a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000731f  mov     r12d, eax
0x180007322  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000732a  mov     ecx, r13d
0x18000732d  lea     eax, [r13+8]
0x180007331  cmp     dword ptr [rbx+8], 1
0x180007335  cmovz   ecx, eax
0x180007338  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000733c  lea     ecx, [rax-7]
0x18000733f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007347  inc     ecx
0x180007349  mov     [rsp+14F0h+var_14C0], ecx
0x18000734d  mov     rcx, [rbp+13F0h+arg_38]
0x180007354  test    rcx, rcx
0x180007357  jz      short loc_180007364
0x180007359  cmp     [rcx], r13w
0x18000735d  mov     [rsp+14F0h+var_14B8], rcx
0x180007362  jnz     short loc_180007369
0x180007364  mov     [rsp+14F0h+var_14B8], r13
0x180007369  call    cs:__imp_GetCurrentThreadId
0x18000736f  mov     [rsp+14F0h+var_14B0], eax
0x180007373  mov     [rsp+14F0h+var_1498], r14
0x180007378  mov     [rsp+14F0h+var_1490], esi
0x18000737c  mov     [rsp+14F0h+var_148C], r12d
0x180007381  mov     [rsp+14F0h+var_14A8], r13
0x180007386  mov     [rsp+14F0h+var_14A0], r13
0x18000738b  mov     [rbp+13F0h+var_1448], r15
0x18000738f  mov     [rbp+13F0h+var_1440], rdi
0x180007393  mov     [rsp+14F0h+var_1488], r13
0x180007398  xorps   xmm0, xmm0
0x18000739b  xor     eax, eax
0x18000739d  movups  [rbp+13F0h+var_1468], xmm0
0x1800073a1  mov     [rbp+13F0h+var_1458], rax
0x1800073a5  xorps   xmm1, xmm1
0x1800073a8  movups  [rsp+14F0h+var_1480], xmm1
0x1800073ad  mov     [rbp+13F0h+var_1470], rax
0x1800073b1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800073b8  test    rax, rax
0x1800073bb  jz      short loc_1800073C8
0x1800073bd  call    _guard_dispatch_icall
0x1800073c2  mov     [rbp+13F0h+var_1450], rax
0x1800073c6  jmp     short loc_1800073CC
0x1800073c8  mov     [rbp+13F0h+var_1450], r13
0x1800073cc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800073d3  test    rax, rax
0x1800073d6  jz      short loc_1800073E2
0x1800073d8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800073dd  call    _guard_dispatch_icall
0x1800073e2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800073e9  test    rax, rax
0x1800073ec  jz      short loc_180007402
0x1800073ee  mov     r8d, 400h
0x1800073f4  lea     rdx, [rbp+13F0h+var_1430]
0x1800073f8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800073fd  call    _guard_dispatch_icall
0x180007402  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007409  test    rax, rax
0x18000740c  jz      short loc_180007418
0x18000740e  lea     rcx, [rsp+14F0h+var_14D0]
0x180007413  call    _guard_dispatch_icall
0x180007418  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000741f  test    rax, rax
0x180007422  jz      short loc_180007435
0x180007424  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007429  jnz     short loc_180007435
0x18000742b  lea     rcx, [rsp+14F0h+var_14D0]
0x180007430  call    _guard_dispatch_icall
0x180007435  cmp     [rsp+14F0h+var_14C8], r13d
0x18000743a  jl      short loc_18000744E
0x18000743c  mov     ecx, 8000FFFFh; this
0x180007441  mov     [rsp+14F0h+var_14C8], ecx
0x180007445  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000744a  mov     [rsp+14F0h+var_14C4], eax
0x18000744e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180007455  jnz     short loc_18000747F
0x180007457  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000745e  test    rax, rax
0x180007461  jz      short loc_18000746D
0x180007463  call    _guard_dispatch_icall
0x180007468  movzx   ecx, al
0x18000746b  jmp     short loc_18000747B
0x18000746d  call    cs:__imp_IsDebuggerPresent
0x180007473  mov     ecx, r13d
0x180007476  test    eax, eax
0x180007478  setnz   cl
0x18000747b  test    ecx, ecx
0x18000747d  jz      short loc_180007486
0x18000747f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007484  jz      short loc_1800074AC
0x180007486  mov     rax, cs:g_pfnResultLoggingCallback
0x18000748d  test    rax, rax
0x180007490  jz      short loc_180007505
0x180007492  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007499  jnz     short loc_180007505
0x18000749b  xor     r8d, r8d
0x18000749e  xor     edx, edx
0x1800074a0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800074a5  call    _guard_dispatch_icall
0x1800074aa  jmp     short loc_180007505
0x1800074ac  mov     ebx, 800h
0x1800074b1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800074b8  test    rax, rax
0x1800074bb  jz      short loc_1800074DA
0x1800074bd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800074c4  jnz     short loc_1800074DA
0x1800074c6  mov     r8d, ebx
0x1800074c9  lea     rdx, [rbp+13F0h+OutputString]
0x1800074d0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800074d5  call    _guard_dispatch_icall
0x1800074da  cmp     [rbp+13F0h+OutputString], r13w
0x1800074e2  jnz     short loc_1800074F8
0x1800074e4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800074e9  mov     rdx, rbx; wchar_t *
0x1800074ec  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800074f3  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800074f8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800074ff  call    cs:__imp_OutputDebugStringW
0x180007505  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000750a  jnz     short loc_180007515
0x18000750c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180007513  jz      short loc_180007527
0x180007515  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000751c  test    rax, rax
0x18000751f  jz      short loc_180007527
0x180007521  call    _guard_dispatch_icall
0x180007526  nop
0x180007527  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000752c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
