# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000549c`
- end: `0x18000574b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005134`

## callees

- `0x180002064`
- `0x1800024ec`
- `0x18000377c`
- `0x1800039e0`
- `0x18000549c`
- `0x180042630`
- `0x1800491f0`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005562`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005562`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800056ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800056ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005658`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005658`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(v18, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v18, 0, 0, v17);
  }
  if ( ((v18[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v18[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v18, v15);
}

```

## disassembly

```asm
0x18000549c  push    rbp
0x18000549e  push    rbx
0x18000549f  push    rsi
0x1800054a0  push    rdi
0x1800054a1  push    r12
0x1800054a3  push    r14
0x1800054a5  push    r15
0x1800054a7  lea     rbp, [rsp-13D0h]
0x1800054af  mov     eax, 14D0h
0x1800054b4  call    _alloca_probe
0x1800054b9  sub     rsp, rax
0x1800054bc  mov     rax, cs:__security_cookie
0x1800054c3  xor     rax, rsp
0x1800054c6  mov     [rbp+1400h+var_40], rax
0x1800054cd  mov     rsi, r8
0x1800054d0  mov     edi, edx
0x1800054d2  mov     rbx, rcx
0x1800054d5  mov     r14, [rbp+1400h+arg_28]
0x1800054dc  xor     edx, edx; Val
0x1800054de  mov     r8d, 98h; Size
0x1800054e4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800054e9  call    memset
0x1800054ee  nop
0x1800054ef  xor     r12d, r12d
0x1800054f2  mov     [rbp+1400h+OutputString], r12w
0x1800054fa  mov     [rbp+1400h+var_1440], r12b
0x1800054fe  mov     rdx, [rbp+1400h+arg_30]; int
0x180005505  mov     ecx, [rdx]; this
0x180005507  mov     [rsp+1500h+var_14D8], ecx
0x18000550b  mov     eax, [rdx+4]
0x18000550e  mov     [rsp+1500h+var_14D4], eax
0x180005512  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005517  mov     r15d, eax
0x18000551a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005522  mov     ecx, r12d
0x180005525  lea     eax, [r12+8]
0x18000552a  cmp     dword ptr [rdx+8], 1
0x18000552e  cmovz   ecx, eax
0x180005531  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005535  lea     ecx, [rax-7]
0x180005538  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005540  inc     ecx
0x180005542  mov     [rsp+1500h+var_14D0], ecx
0x180005546  mov     rcx, [rbp+1400h+arg_38]
0x18000554d  test    rcx, rcx
0x180005550  jz      short loc_18000555D
0x180005552  cmp     [rcx], r12w
0x180005556  mov     [rsp+1500h+var_14C8], rcx
0x18000555b  jnz     short loc_180005562
0x18000555d  mov     [rsp+1500h+var_14C8], r12
0x180005562  call    cs:__imp_GetCurrentThreadId
0x180005568  mov     [rsp+1500h+var_14C0], eax
0x18000556c  mov     [rsp+1500h+var_14A8], rsi
0x180005571  mov     [rsp+1500h+var_14A0], edi
0x180005575  mov     [rsp+1500h+var_149C], r15d
0x18000557a  mov     [rsp+1500h+var_14B8], r12
0x18000557f  mov     [rsp+1500h+var_14B0], r12
0x180005584  mov     [rbp+1400h+var_1458], r14
0x180005588  mov     [rbp+1400h+var_1450], rbx
0x18000558c  mov     [rsp+1500h+var_1498], r12
0x180005591  xorps   xmm0, xmm0
0x180005594  xor     eax, eax
0x180005596  movups  [rbp+1400h+var_1478], xmm0
0x18000559a  mov     [rbp+1400h+var_1468], rax
0x18000559e  xorps   xmm1, xmm1
0x1800055a1  movups  [rsp+1500h+var_1490], xmm1
0x1800055a6  mov     [rbp+1400h+var_1480], rax
0x1800055aa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800055b1  test    rax, rax
0x1800055b4  jz      short loc_1800055C1
0x1800055b6  call    _guard_dispatch_icall
0x1800055bb  mov     [rbp+1400h+var_1460], rax
0x1800055bf  jmp     short loc_1800055C5
0x1800055c1  mov     [rbp+1400h+var_1460], r12
0x1800055c5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800055cc  test    rax, rax
0x1800055cf  jz      short loc_1800055DB
0x1800055d1  lea     rcx, [rsp+1500h+var_14E0]
0x1800055d6  call    _guard_dispatch_icall
0x1800055db  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800055e2  test    rax, rax
0x1800055e5  jz      short loc_1800055FB
0x1800055e7  mov     r8d, 400h
0x1800055ed  lea     rdx, [rbp+1400h+var_1440]
0x1800055f1  lea     rcx, [rsp+1500h+var_14E0]
0x1800055f6  call    _guard_dispatch_icall
0x1800055fb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005602  test    rax, rax
0x180005605  jz      short loc_180005611
0x180005607  lea     rcx, [rsp+1500h+var_14E0]
0x18000560c  call    _guard_dispatch_icall
0x180005611  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005618  test    rax, rax
0x18000561b  jz      short loc_18000562E
0x18000561d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005622  jnz     short loc_18000562E
0x180005624  lea     rcx, [rsp+1500h+var_14E0]
0x180005629  call    _guard_dispatch_icall
0x18000562e  cmp     [rsp+1500h+var_14D8], r12d
0x180005633  jge     loc_180005745
0x180005639  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005640  jnz     short loc_18000566A
0x180005642  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005649  test    rax, rax
0x18000564c  jz      short loc_180005658
0x18000564e  call    _guard_dispatch_icall
0x180005653  movzx   ecx, al
0x180005656  jmp     short loc_180005666
0x180005658  call    cs:__imp_IsDebuggerPresent
0x18000565e  mov     ecx, r12d
0x180005661  test    eax, eax
0x180005663  setnz   cl
0x180005666  test    ecx, ecx
0x180005668  jz      short loc_180005671
0x18000566a  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000566f  jz      short loc_180005697
0x180005671  mov     rax, cs:g_pfnResultLoggingCallback
0x180005678  test    rax, rax
0x18000567b  jz      short loc_1800056F0
0x18000567d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005684  jnz     short loc_1800056F0
0x180005686  xor     r8d, r8d
0x180005689  xor     edx, edx
0x18000568b  lea     rcx, [rsp+1500h+var_14E0]
0x180005690  call    _guard_dispatch_icall
0x180005695  jmp     short loc_1800056F0
0x180005697  mov     ebx, 800h
0x18000569c  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056a3  test    rax, rax
0x1800056a6  jz      short loc_1800056C5
0x1800056a8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800056af  jnz     short loc_1800056C5
0x1800056b1  mov     r8d, ebx
0x1800056b4  lea     rdx, [rbp+1400h+OutputString]
0x1800056bb  lea     rcx, [rsp+1500h+var_14E0]
0x1800056c0  call    _guard_dispatch_icall
0x1800056c5  cmp     [rbp+1400h+OutputString], r12w
0x1800056cd  jnz     short loc_1800056E3
0x1800056cf  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800056d4  mov     rdx, rbx; wchar_t *
0x1800056d7  lea     rcx, [rbp+1400h+OutputString]; this
0x1800056de  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800056e3  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800056ea  call    cs:__imp_OutputDebugStringW
0x1800056f0  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800056f5  jnz     short loc_180005700
0x1800056f7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800056fe  jz      short loc_180005712
0x180005700  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005707  test    rax, rax
0x18000570a  jz      short loc_180005712
0x18000570c  call    _guard_dispatch_icall
0x180005711  nop
0x180005712  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005717  jnz     short loc_18000573A
0x180005719  mov     rcx, [rbp+1400h+var_40]
0x180005720  xor     rcx, rsp; StackCookie
0x180005723  call    __security_check_cookie
0x180005728  add     rsp, 14D0h
0x18000572f  pop     r15
0x180005731  pop     r14
0x180005733  pop     r12
0x180005735  pop     rdi
0x180005736  pop     rsi
0x180005737  pop     rbx
0x180005738  pop     rbp
0x180005739  retn
0x18000573a  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000573f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005745  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
