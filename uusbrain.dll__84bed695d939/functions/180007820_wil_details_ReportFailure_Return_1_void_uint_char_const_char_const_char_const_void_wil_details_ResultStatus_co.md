# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007820`
- end: `0x180007acf`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `687`
- prototype: `void __fastcall(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800074b8`

## callees

- `0x180004b14`
- `0x180004f9c`
- `0x18000622c`
- `0x180006490`
- `0x180007820`
- `0x1800427d0`
- `0x1800479c0`
- `0x180047a30`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800078e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800078e6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007a6e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007a6e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800079dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800079dc`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        _WORD *a8)
{
  unsigned int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v17; // r9
  unsigned __int64 v18[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v18, 0, 0x98u);
  OutputString[0] = 0;
  v19[0] = 0;
  v18[1] = *a7;
  v11 = wil::details::RecordReturn((wil::details *)LODWORD(v18[1]), (int)a7);
  LODWORD(v18[0]) = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  HIDWORD(v18[0]) = v12;
  LODWORD(v18[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v18[3] = (unsigned __int64)a8, v14) )
    v18[3] = 0;
  LODWORD(v18[4]) = GetCurrentThreadId();
  v18[7] = a3;
  v18[8] = __PAIR64__(v11, a2);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
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
  if ( ((v18[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v18[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v18, v15);
}

```

## disassembly

```asm
0x180007820  push    rbp
0x180007822  push    rbx
0x180007823  push    rsi
0x180007824  push    rdi
0x180007825  push    r12
0x180007827  push    r14
0x180007829  push    r15
0x18000782b  lea     rbp, [rsp-13D0h]
0x180007833  mov     eax, 14D0h
0x180007838  call    _alloca_probe
0x18000783d  sub     rsp, rax
0x180007840  mov     rax, cs:__security_cookie
0x180007847  xor     rax, rsp
0x18000784a  mov     [rbp+1400h+var_40], rax
0x180007851  mov     rsi, r8
0x180007854  mov     edi, edx
0x180007856  mov     rbx, rcx
0x180007859  mov     r14, [rbp+1400h+arg_28]
0x180007860  xor     edx, edx; Val
0x180007862  mov     r8d, 98h; Size
0x180007868  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000786d  call    memset
0x180007872  nop
0x180007873  xor     r12d, r12d
0x180007876  mov     [rbp+1400h+OutputString], r12w
0x18000787e  mov     [rbp+1400h+var_1440], r12b
0x180007882  mov     rdx, [rbp+1400h+arg_30]; int
0x180007889  mov     ecx, [rdx]; this
0x18000788b  mov     [rsp+1500h+var_14D8], ecx
0x18000788f  mov     eax, [rdx+4]
0x180007892  mov     [rsp+1500h+var_14D4], eax
0x180007896  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000789b  mov     r15d, eax
0x18000789e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800078a6  mov     ecx, r12d
0x1800078a9  lea     eax, [r12+8]
0x1800078ae  cmp     dword ptr [rdx+8], 1
0x1800078b2  cmovz   ecx, eax
0x1800078b5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800078b9  lea     ecx, [rax-7]
0x1800078bc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800078c4  inc     ecx
0x1800078c6  mov     [rsp+1500h+var_14D0], ecx
0x1800078ca  mov     rcx, [rbp+1400h+arg_38]
0x1800078d1  test    rcx, rcx
0x1800078d4  jz      short loc_1800078E1
0x1800078d6  cmp     [rcx], r12w
0x1800078da  mov     [rsp+1500h+var_14C8], rcx
0x1800078df  jnz     short loc_1800078E6
0x1800078e1  mov     [rsp+1500h+var_14C8], r12
0x1800078e6  call    cs:__imp_GetCurrentThreadId
0x1800078ec  mov     [rsp+1500h+var_14C0], eax
0x1800078f0  mov     [rsp+1500h+var_14A8], rsi
0x1800078f5  mov     [rsp+1500h+var_14A0], edi
0x1800078f9  mov     [rsp+1500h+var_149C], r15d
0x1800078fe  mov     [rsp+1500h+var_14B8], r12
0x180007903  mov     [rsp+1500h+var_14B0], r12
0x180007908  mov     [rbp+1400h+var_1458], r14
0x18000790c  mov     [rbp+1400h+var_1450], rbx
0x180007910  mov     [rsp+1500h+var_1498], r12
0x180007915  xorps   xmm0, xmm0
0x180007918  xor     eax, eax
0x18000791a  movups  [rbp+1400h+var_1478], xmm0
0x18000791e  mov     [rbp+1400h+var_1468], rax
0x180007922  xorps   xmm1, xmm1
0x180007925  movups  [rsp+1500h+var_1490], xmm1
0x18000792a  mov     [rbp+1400h+var_1480], rax
0x18000792e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007935  test    rax, rax
0x180007938  jz      short loc_180007945
0x18000793a  call    _guard_dispatch_icall
0x18000793f  mov     [rbp+1400h+var_1460], rax
0x180007943  jmp     short loc_180007949
0x180007945  mov     [rbp+1400h+var_1460], r12
0x180007949  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007950  test    rax, rax
0x180007953  jz      short loc_18000795F
0x180007955  lea     rcx, [rsp+1500h+var_14E0]
0x18000795a  call    _guard_dispatch_icall
0x18000795f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007966  test    rax, rax
0x180007969  jz      short loc_18000797F
0x18000796b  mov     r8d, 400h
0x180007971  lea     rdx, [rbp+1400h+var_1440]
0x180007975  lea     rcx, [rsp+1500h+var_14E0]
0x18000797a  call    _guard_dispatch_icall
0x18000797f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007986  test    rax, rax
0x180007989  jz      short loc_180007995
0x18000798b  lea     rcx, [rsp+1500h+var_14E0]
0x180007990  call    _guard_dispatch_icall
0x180007995  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000799c  test    rax, rax
0x18000799f  jz      short loc_1800079B2
0x1800079a1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800079a6  jnz     short loc_1800079B2
0x1800079a8  lea     rcx, [rsp+1500h+var_14E0]
0x1800079ad  call    _guard_dispatch_icall
0x1800079b2  cmp     [rsp+1500h+var_14D8], r12d
0x1800079b7  jge     loc_180007AC9
0x1800079bd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800079c4  jnz     short loc_1800079EE
0x1800079c6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800079cd  test    rax, rax
0x1800079d0  jz      short loc_1800079DC
0x1800079d2  call    _guard_dispatch_icall
0x1800079d7  movzx   ecx, al
0x1800079da  jmp     short loc_1800079EA
0x1800079dc  call    cs:__imp_IsDebuggerPresent
0x1800079e2  mov     ecx, r12d
0x1800079e5  test    eax, eax
0x1800079e7  setnz   cl
0x1800079ea  test    ecx, ecx
0x1800079ec  jz      short loc_1800079F5
0x1800079ee  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800079f3  jz      short loc_180007A1B
0x1800079f5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800079fc  test    rax, rax
0x1800079ff  jz      short loc_180007A74
0x180007a01  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007a08  jnz     short loc_180007A74
0x180007a0a  xor     r8d, r8d
0x180007a0d  xor     edx, edx
0x180007a0f  lea     rcx, [rsp+1500h+var_14E0]
0x180007a14  call    _guard_dispatch_icall
0x180007a19  jmp     short loc_180007A74
0x180007a1b  mov     ebx, 800h
0x180007a20  mov     rax, cs:g_pfnResultLoggingCallback
0x180007a27  test    rax, rax
0x180007a2a  jz      short loc_180007A49
0x180007a2c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007a33  jnz     short loc_180007A49
0x180007a35  mov     r8d, ebx
0x180007a38  lea     rdx, [rbp+1400h+OutputString]
0x180007a3f  lea     rcx, [rsp+1500h+var_14E0]
0x180007a44  call    _guard_dispatch_icall
0x180007a49  cmp     [rbp+1400h+OutputString], r12w
0x180007a51  jnz     short loc_180007A67
0x180007a53  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180007a58  mov     rdx, rbx; wchar_t *
0x180007a5b  lea     rcx, [rbp+1400h+OutputString]; this
0x180007a62  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180007a67  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180007a6e  call    cs:__imp_OutputDebugStringW
0x180007a74  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180007a79  jnz     short loc_180007A84
0x180007a7b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180007a82  jz      short loc_180007A96
0x180007a84  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007a8b  test    rax, rax
0x180007a8e  jz      short loc_180007A96
0x180007a90  call    _guard_dispatch_icall
0x180007a95  nop
0x180007a96  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180007a9b  jnz     short loc_180007ABE
0x180007a9d  mov     rcx, [rbp+1400h+var_40]
0x180007aa4  xor     rcx, rsp; StackCookie
0x180007aa7  call    __security_check_cookie
0x180007aac  add     rsp, 14D0h
0x180007ab3  pop     r15
0x180007ab5  pop     r14
0x180007ab7  pop     r12
0x180007ab9  pop     rdi
0x180007aba  pop     rsi
0x180007abb  pop     rbx
0x180007abc  pop     rbp
0x180007abd  retn
0x180007abe  lea     rcx, [rsp+1500h+var_14E0]; this
0x180007ac3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007ac9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
