# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800061d0`
- end: `0x18000649e`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800064a4`

## callees

- `0x180005734`
- `0x1800061d0`
- `0x18000687c`
- `0x180006bec`
- `0x1800071b4`
- `0x180007200`
- `0x1800153c0`
- `0x180015430`
- `0x1800154b0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000638e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000638e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006432`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006432`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006291`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006291`

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
0x1800061d0  mov     [rsp-8+arg_18], rbx
0x1800061d5  push    rbp
0x1800061d6  push    rsi
0x1800061d7  push    rdi
0x1800061d8  push    r12
0x1800061da  push    r13
0x1800061dc  push    r14
0x1800061de  push    r15
0x1800061e0  lea     rbp, [rsp-13C0h]
0x1800061e8  mov     eax, 14C0h
0x1800061ed  call    _alloca_probe
0x1800061f2  sub     rsp, rax
0x1800061f5  mov     r14, r8
0x1800061f8  mov     esi, edx
0x1800061fa  mov     rbx, rcx
0x1800061fd  mov     r15, [rbp+13F0h+arg_28]
0x180006204  xor     r13d, r13d
0x180006207  cmp     cs:g_pfnThrowPlatformException, r13
0x18000620e  setnz   dil
0x180006212  xor     edx, edx; Val
0x180006214  mov     r8d, 98h; Size
0x18000621a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000621f  call    memset
0x180006224  nop
0x180006225  mov     [rbp+13F0h+OutputString], r13w
0x18000622d  mov     [rbp+13F0h+var_1430], r13b
0x180006231  mov     rdx, [rbp+13F0h+arg_30]; int
0x180006238  mov     ecx, [rdx]; this
0x18000623a  mov     [rsp+14F0h+var_14C8], ecx
0x18000623e  mov     eax, [rdx+4]
0x180006241  mov     [rsp+14F0h+var_14C4], eax
0x180006245  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000624a  mov     r12d, eax
0x18000624d  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180006252  mov     ecx, r13d
0x180006255  lea     eax, [r13+8]
0x180006259  cmp     dword ptr [rdx+8], 1
0x18000625d  cmovz   ecx, eax
0x180006260  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006264  lea     ecx, [rax-7]
0x180006267  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000626f  inc     ecx
0x180006271  mov     [rsp+14F0h+var_14C0], ecx
0x180006275  mov     rcx, [rbp+13F0h+arg_38]
0x18000627c  test    rcx, rcx
0x18000627f  jz      short loc_18000628C
0x180006281  cmp     [rcx], r13w
0x180006285  mov     [rsp+14F0h+var_14B8], rcx
0x18000628a  jnz     short loc_180006291
0x18000628c  mov     [rsp+14F0h+var_14B8], r13
0x180006291  call    cs:__imp_GetCurrentThreadId
0x180006297  mov     [rsp+14F0h+var_14B0], eax
0x18000629b  mov     [rsp+14F0h+var_1498], r14
0x1800062a0  mov     [rsp+14F0h+var_1490], esi
0x1800062a4  mov     [rsp+14F0h+var_148C], r12d
0x1800062a9  mov     [rsp+14F0h+var_14A8], r13
0x1800062ae  mov     [rsp+14F0h+var_14A0], r13
0x1800062b3  mov     [rbp+13F0h+var_1448], r15
0x1800062b7  mov     [rbp+13F0h+var_1440], rbx
0x1800062bb  mov     [rsp+14F0h+var_1488], r13
0x1800062c0  xorps   xmm0, xmm0
0x1800062c3  xor     eax, eax
0x1800062c5  movups  [rbp+13F0h+var_1468], xmm0
0x1800062c9  mov     [rbp+13F0h+var_1458], rax
0x1800062cd  xorps   xmm1, xmm1
0x1800062d0  movups  [rsp+14F0h+var_1480], xmm1
0x1800062d5  mov     [rbp+13F0h+var_1470], rax
0x1800062d9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800062e0  test    rax, rax
0x1800062e3  jz      short loc_1800062F0
0x1800062e5  call    _guard_dispatch_icall
0x1800062ea  mov     [rbp+13F0h+var_1450], rax
0x1800062ee  jmp     short loc_1800062F4
0x1800062f0  mov     [rbp+13F0h+var_1450], r13
0x1800062f4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800062fb  test    rax, rax
0x1800062fe  jz      short loc_18000630A
0x180006300  lea     rcx, [rsp+14F0h+var_14D0]
0x180006305  call    _guard_dispatch_icall
0x18000630a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006311  test    rax, rax
0x180006314  jz      short loc_18000632A
0x180006316  mov     r8d, 400h
0x18000631c  lea     rdx, [rbp+13F0h+var_1430]
0x180006320  lea     rcx, [rsp+14F0h+var_14D0]
0x180006325  call    _guard_dispatch_icall
0x18000632a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006331  test    rax, rax
0x180006334  jz      short loc_180006340
0x180006336  lea     rcx, [rsp+14F0h+var_14D0]
0x18000633b  call    _guard_dispatch_icall
0x180006340  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006347  test    rax, rax
0x18000634a  jz      short loc_180006362
0x18000634c  test    dil, dil
0x18000634f  jnz     short loc_180006362
0x180006351  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006356  jnz     short loc_180006362
0x180006358  lea     rcx, [rsp+14F0h+var_14D0]
0x18000635d  call    _guard_dispatch_icall
0x180006362  cmp     [rsp+14F0h+var_14C8], r13d
0x180006367  jl      short loc_18000636F
0x180006369  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000636f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006376  jnz     short loc_1800063A0
0x180006378  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000637f  test    rax, rax
0x180006382  jz      short loc_18000638E
0x180006384  call    _guard_dispatch_icall
0x180006389  movzx   ecx, al
0x18000638c  jmp     short loc_18000639C
0x18000638e  call    cs:__imp_IsDebuggerPresent
0x180006394  mov     ecx, r13d
0x180006397  test    eax, eax
0x180006399  setnz   cl
0x18000639c  test    ecx, ecx
0x18000639e  jz      short loc_1800063A9
0x1800063a0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800063a5  mov     bl, 1
0x1800063a7  jz      short loc_1800063AC
0x1800063a9  mov     bl, r13b
0x1800063ac  test    dil, dil
0x1800063af  jnz     short loc_1800063DB
0x1800063b1  test    bl, bl
0x1800063b3  jnz     short loc_1800063DB
0x1800063b5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800063bc  test    rax, rax
0x1800063bf  jz      short loc_180006438
0x1800063c1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800063c8  jnz     short loc_180006438
0x1800063ca  xor     r8d, r8d
0x1800063cd  xor     edx, edx
0x1800063cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800063d4  call    _guard_dispatch_icall
0x1800063d9  jmp     short loc_180006438
0x1800063db  mov     esi, 800h
0x1800063e0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800063e7  test    rax, rax
0x1800063ea  jz      short loc_180006409
0x1800063ec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800063f3  jnz     short loc_180006409
0x1800063f5  mov     r8d, esi
0x1800063f8  lea     rdx, [rbp+13F0h+OutputString]
0x1800063ff  lea     rcx, [rsp+14F0h+var_14D0]
0x180006404  call    _guard_dispatch_icall
0x180006409  cmp     [rbp+13F0h+OutputString], r13w
0x180006411  jnz     short loc_180006427
0x180006413  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006418  mov     rdx, rsi; wchar_t *
0x18000641b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006422  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180006427  test    bl, bl
0x180006429  jz      short loc_180006438
0x18000642b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006432  call    cs:__imp_OutputDebugStringW
0x180006438  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000643d  jnz     short loc_180006448
0x18000643f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006446  jz      short loc_18000645A
0x180006448  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000644f  test    rax, rax
0x180006452  jz      short loc_18000645A
0x180006454  call    _guard_dispatch_icall
0x180006459  nop
0x18000645a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000645f  jz      short loc_18000646C
0x180006461  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006466  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000646c  test    dil, dil
0x18000646f  jz      short loc_180006489
0x180006471  lea     rdx, [rbp+13F0h+OutputString]
0x180006478  lea     rcx, [rsp+14F0h+var_14D0]
0x18000647d  mov     rax, cs:g_pfnThrowPlatformException
0x180006484  call    _guard_dispatch_icall
0x180006489  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000648e  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180006493  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006498  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
