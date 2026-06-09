# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180004580`
- end: `0x180004802`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000363c`

## callees

- `0x180001e74`
- `0x180002340`
- `0x180002580`
- `0x18000358c`
- `0x180004580`
- `0x180015940`
- `0x1800159b0`
- `0x180015a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004639`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004639`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000473d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000473d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800047cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800047cf`

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
0x180004580  mov     [rsp-8+arg_18], rbx
0x180004585  push    rbp
0x180004586  push    rsi
0x180004587  push    rdi
0x180004588  push    r12
0x18000458a  push    r13
0x18000458c  push    r14
0x18000458e  push    r15
0x180004590  lea     rbp, [rsp-13C0h]
0x180004598  mov     eax, 14C0h
0x18000459d  call    _alloca_probe
0x1800045a2  sub     rsp, rax
0x1800045a5  mov     r14, r8
0x1800045a8  mov     esi, edx
0x1800045aa  mov     rdi, rcx
0x1800045ad  mov     r15, [rbp+13F0h+arg_28]
0x1800045b4  xor     edx, edx; Val
0x1800045b6  mov     r8d, 98h; Size
0x1800045bc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800045c1  call    memset
0x1800045c6  nop
0x1800045c7  xor     r13d, r13d
0x1800045ca  mov     [rbp+13F0h+OutputString], r13w
0x1800045d2  mov     [rbp+13F0h+var_1430], r13b
0x1800045d6  mov     rbx, [rbp+13F0h+arg_30]
0x1800045dd  mov     ecx, [rbx]; this
0x1800045df  mov     [rsp+14F0h+var_14C8], ecx
0x1800045e3  mov     eax, [rbx+4]
0x1800045e6  mov     [rsp+14F0h+var_14C4], eax
0x1800045ea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800045ef  mov     r12d, eax
0x1800045f2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800045fa  mov     ecx, r13d
0x1800045fd  lea     eax, [r13+8]
0x180004601  cmp     dword ptr [rbx+8], 1
0x180004605  cmovz   ecx, eax
0x180004608  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000460c  lea     ecx, [rax-7]
0x18000460f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004617  inc     ecx
0x180004619  mov     [rsp+14F0h+var_14C0], ecx
0x18000461d  mov     rcx, [rbp+13F0h+arg_38]
0x180004624  test    rcx, rcx
0x180004627  jz      short loc_180004634
0x180004629  cmp     [rcx], r13w
0x18000462d  mov     [rsp+14F0h+var_14B8], rcx
0x180004632  jnz     short loc_180004639
0x180004634  mov     [rsp+14F0h+var_14B8], r13
0x180004639  call    cs:__imp_GetCurrentThreadId
0x18000463f  mov     [rsp+14F0h+var_14B0], eax
0x180004643  mov     [rsp+14F0h+var_1498], r14
0x180004648  mov     [rsp+14F0h+var_1490], esi
0x18000464c  mov     [rsp+14F0h+var_148C], r12d
0x180004651  mov     [rsp+14F0h+var_14A8], r13
0x180004656  mov     [rsp+14F0h+var_14A0], r13
0x18000465b  mov     [rbp+13F0h+var_1448], r15
0x18000465f  mov     [rbp+13F0h+var_1440], rdi
0x180004663  mov     [rsp+14F0h+var_1488], r13
0x180004668  xorps   xmm0, xmm0
0x18000466b  xor     eax, eax
0x18000466d  movups  [rbp+13F0h+var_1468], xmm0
0x180004671  mov     [rbp+13F0h+var_1458], rax
0x180004675  xorps   xmm1, xmm1
0x180004678  movups  [rsp+14F0h+var_1480], xmm1
0x18000467d  mov     [rbp+13F0h+var_1470], rax
0x180004681  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004688  test    rax, rax
0x18000468b  jz      short loc_180004698
0x18000468d  call    _guard_dispatch_icall
0x180004692  mov     [rbp+13F0h+var_1450], rax
0x180004696  jmp     short loc_18000469C
0x180004698  mov     [rbp+13F0h+var_1450], r13
0x18000469c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800046a3  test    rax, rax
0x1800046a6  jz      short loc_1800046B2
0x1800046a8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800046ad  call    _guard_dispatch_icall
0x1800046b2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800046b9  test    rax, rax
0x1800046bc  jz      short loc_1800046D2
0x1800046be  mov     r8d, 400h
0x1800046c4  lea     rdx, [rbp+13F0h+var_1430]
0x1800046c8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800046cd  call    _guard_dispatch_icall
0x1800046d2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800046d9  test    rax, rax
0x1800046dc  jz      short loc_1800046E8
0x1800046de  lea     rcx, [rsp+14F0h+var_14D0]
0x1800046e3  call    _guard_dispatch_icall
0x1800046e8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800046ef  test    rax, rax
0x1800046f2  jz      short loc_180004705
0x1800046f4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800046f9  jnz     short loc_180004705
0x1800046fb  lea     rcx, [rsp+14F0h+var_14D0]
0x180004700  call    _guard_dispatch_icall
0x180004705  cmp     [rsp+14F0h+var_14C8], r13d
0x18000470a  jl      short loc_18000471E
0x18000470c  mov     ecx, 8000FFFFh; this
0x180004711  mov     [rsp+14F0h+var_14C8], ecx
0x180004715  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000471a  mov     [rsp+14F0h+var_14C4], eax
0x18000471e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004725  jnz     short loc_18000474F
0x180004727  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000472e  test    rax, rax
0x180004731  jz      short loc_18000473D
0x180004733  call    _guard_dispatch_icall
0x180004738  movzx   ecx, al
0x18000473b  jmp     short loc_18000474B
0x18000473d  call    cs:__imp_IsDebuggerPresent
0x180004743  mov     ecx, r13d
0x180004746  test    eax, eax
0x180004748  setnz   cl
0x18000474b  test    ecx, ecx
0x18000474d  jz      short loc_180004756
0x18000474f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004754  jz      short loc_18000477C
0x180004756  mov     rax, cs:g_pfnResultLoggingCallback
0x18000475d  test    rax, rax
0x180004760  jz      short loc_1800047D5
0x180004762  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004769  jnz     short loc_1800047D5
0x18000476b  xor     r8d, r8d
0x18000476e  xor     edx, edx
0x180004770  lea     rcx, [rsp+14F0h+var_14D0]
0x180004775  call    _guard_dispatch_icall
0x18000477a  jmp     short loc_1800047D5
0x18000477c  mov     ebx, 800h
0x180004781  mov     rax, cs:g_pfnResultLoggingCallback
0x180004788  test    rax, rax
0x18000478b  jz      short loc_1800047AA
0x18000478d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004794  jnz     short loc_1800047AA
0x180004796  mov     r8d, ebx
0x180004799  lea     rdx, [rbp+13F0h+OutputString]
0x1800047a0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800047a5  call    _guard_dispatch_icall
0x1800047aa  cmp     [rbp+13F0h+OutputString], r13w
0x1800047b2  jnz     short loc_1800047C8
0x1800047b4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800047b9  mov     rdx, rbx; wchar_t *
0x1800047bc  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800047c3  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800047c8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800047cf  call    cs:__imp_OutputDebugStringW
0x1800047d5  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800047da  jnz     short loc_1800047E5
0x1800047dc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800047e3  jz      short loc_1800047F7
0x1800047e5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800047ec  test    rax, rax
0x1800047ef  jz      short loc_1800047F7
0x1800047f1  call    _guard_dispatch_icall
0x1800047f6  nop
0x1800047f7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800047fc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
