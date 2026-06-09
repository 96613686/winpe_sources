# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800091d8`
- end: `0x1800094a6`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800094ac`

## callees

- `0x180008940`
- `0x18000897c`
- `0x1800091d8`
- `0x180009568`
- `0x1800098dc`
- `0x180009ea4`
- `0x180096100`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000943a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000943a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009396`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009396`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009299`

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
0x1800091d8  mov     [rsp-8+arg_18], rbx
0x1800091dd  push    rbp
0x1800091de  push    rsi
0x1800091df  push    rdi
0x1800091e0  push    r12
0x1800091e2  push    r13
0x1800091e4  push    r14
0x1800091e6  push    r15
0x1800091e8  lea     rbp, [rsp-13C0h]
0x1800091f0  mov     eax, 14C0h
0x1800091f5  call    _alloca_probe
0x1800091fa  sub     rsp, rax
0x1800091fd  mov     r14, r8
0x180009200  mov     esi, edx
0x180009202  mov     rbx, rcx
0x180009205  mov     r15, [rbp+13F0h+arg_28]
0x18000920c  xor     r13d, r13d
0x18000920f  cmp     cs:g_pfnThrowPlatformException, r13
0x180009216  setnz   dil
0x18000921a  xor     edx, edx; Val
0x18000921c  mov     r8d, 98h; Size
0x180009222  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009227  call    memset
0x18000922c  nop
0x18000922d  mov     [rbp+13F0h+OutputString], r13w
0x180009235  mov     [rbp+13F0h+var_1430], r13b
0x180009239  mov     rdx, [rbp+13F0h+arg_30]; int
0x180009240  mov     ecx, [rdx]; this
0x180009242  mov     [rsp+14F0h+var_14C8], ecx
0x180009246  mov     eax, [rdx+4]
0x180009249  mov     [rsp+14F0h+var_14C4], eax
0x18000924d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009252  mov     r12d, eax
0x180009255  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000925a  mov     ecx, r13d
0x18000925d  lea     eax, [r13+8]
0x180009261  cmp     dword ptr [rdx+8], 1
0x180009265  cmovz   ecx, eax
0x180009268  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000926c  lea     ecx, [rax-7]
0x18000926f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009277  inc     ecx
0x180009279  mov     [rsp+14F0h+var_14C0], ecx
0x18000927d  mov     rcx, [rbp+13F0h+arg_38]
0x180009284  test    rcx, rcx
0x180009287  jz      short loc_180009294
0x180009289  cmp     [rcx], r13w
0x18000928d  mov     [rsp+14F0h+var_14B8], rcx
0x180009292  jnz     short loc_180009299
0x180009294  mov     [rsp+14F0h+var_14B8], r13
0x180009299  call    cs:__imp_GetCurrentThreadId
0x18000929f  mov     [rsp+14F0h+var_14B0], eax
0x1800092a3  mov     [rsp+14F0h+var_1498], r14
0x1800092a8  mov     [rsp+14F0h+var_1490], esi
0x1800092ac  mov     [rsp+14F0h+var_148C], r12d
0x1800092b1  mov     [rsp+14F0h+var_14A8], r13
0x1800092b6  mov     [rsp+14F0h+var_14A0], r13
0x1800092bb  mov     [rbp+13F0h+var_1448], r15
0x1800092bf  mov     [rbp+13F0h+var_1440], rbx
0x1800092c3  mov     [rsp+14F0h+var_1488], r13
0x1800092c8  xorps   xmm0, xmm0
0x1800092cb  xor     eax, eax
0x1800092cd  movups  [rbp+13F0h+var_1468], xmm0
0x1800092d1  mov     [rbp+13F0h+var_1458], rax
0x1800092d5  xorps   xmm1, xmm1
0x1800092d8  movups  [rsp+14F0h+var_1480], xmm1
0x1800092dd  mov     [rbp+13F0h+var_1470], rax
0x1800092e1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800092e8  test    rax, rax
0x1800092eb  jz      short loc_1800092F8
0x1800092ed  call    _guard_dispatch_icall
0x1800092f2  mov     [rbp+13F0h+var_1450], rax
0x1800092f6  jmp     short loc_1800092FC
0x1800092f8  mov     [rbp+13F0h+var_1450], r13
0x1800092fc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009303  test    rax, rax
0x180009306  jz      short loc_180009312
0x180009308  lea     rcx, [rsp+14F0h+var_14D0]
0x18000930d  call    _guard_dispatch_icall
0x180009312  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009319  test    rax, rax
0x18000931c  jz      short loc_180009332
0x18000931e  mov     r8d, 400h
0x180009324  lea     rdx, [rbp+13F0h+var_1430]
0x180009328  lea     rcx, [rsp+14F0h+var_14D0]
0x18000932d  call    _guard_dispatch_icall
0x180009332  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009339  test    rax, rax
0x18000933c  jz      short loc_180009348
0x18000933e  lea     rcx, [rsp+14F0h+var_14D0]
0x180009343  call    _guard_dispatch_icall
0x180009348  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000934f  test    rax, rax
0x180009352  jz      short loc_18000936A
0x180009354  test    dil, dil
0x180009357  jnz     short loc_18000936A
0x180009359  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000935e  jnz     short loc_18000936A
0x180009360  lea     rcx, [rsp+14F0h+var_14D0]
0x180009365  call    _guard_dispatch_icall
0x18000936a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000936f  jl      short loc_180009377
0x180009371  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009377  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000937e  jnz     short loc_1800093A8
0x180009380  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009387  test    rax, rax
0x18000938a  jz      short loc_180009396
0x18000938c  call    _guard_dispatch_icall
0x180009391  movzx   ecx, al
0x180009394  jmp     short loc_1800093A4
0x180009396  call    cs:__imp_IsDebuggerPresent
0x18000939c  mov     ecx, r13d
0x18000939f  test    eax, eax
0x1800093a1  setnz   cl
0x1800093a4  test    ecx, ecx
0x1800093a6  jz      short loc_1800093B1
0x1800093a8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800093ad  mov     bl, 1
0x1800093af  jz      short loc_1800093B4
0x1800093b1  mov     bl, r13b
0x1800093b4  test    dil, dil
0x1800093b7  jnz     short loc_1800093E3
0x1800093b9  test    bl, bl
0x1800093bb  jnz     short loc_1800093E3
0x1800093bd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800093c4  test    rax, rax
0x1800093c7  jz      short loc_180009440
0x1800093c9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800093d0  jnz     short loc_180009440
0x1800093d2  xor     r8d, r8d
0x1800093d5  xor     edx, edx
0x1800093d7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800093dc  call    _guard_dispatch_icall
0x1800093e1  jmp     short loc_180009440
0x1800093e3  mov     esi, 800h
0x1800093e8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800093ef  test    rax, rax
0x1800093f2  jz      short loc_180009411
0x1800093f4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800093fb  jnz     short loc_180009411
0x1800093fd  mov     r8d, esi
0x180009400  lea     rdx, [rbp+13F0h+OutputString]
0x180009407  lea     rcx, [rsp+14F0h+var_14D0]
0x18000940c  call    _guard_dispatch_icall
0x180009411  cmp     [rbp+13F0h+OutputString], r13w
0x180009419  jnz     short loc_18000942F
0x18000941b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009420  mov     rdx, rsi; wchar_t *
0x180009423  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000942a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000942f  test    bl, bl
0x180009431  jz      short loc_180009440
0x180009433  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000943a  call    cs:__imp_OutputDebugStringW
0x180009440  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180009445  jnz     short loc_180009450
0x180009447  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000944e  jz      short loc_180009462
0x180009450  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009457  test    rax, rax
0x18000945a  jz      short loc_180009462
0x18000945c  call    _guard_dispatch_icall
0x180009461  nop
0x180009462  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180009467  jz      short loc_180009474
0x180009469  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000946e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009474  test    dil, dil
0x180009477  jz      short loc_180009491
0x180009479  lea     rdx, [rbp+13F0h+OutputString]
0x180009480  lea     rcx, [rsp+14F0h+var_14D0]
0x180009485  mov     rax, cs:g_pfnThrowPlatformException
0x18000948c  call    _guard_dispatch_icall
0x180009491  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009496  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000949b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800094a0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
