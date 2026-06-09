# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180038060`
- end: `0x18003832e`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180038334`

## callees

- `0x180002064`
- `0x1800024d0`
- `0x1800031b8`
- `0x18000377c`
- `0x1800039e0`
- `0x180038060`
- `0x1800491f0`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038121`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038121`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800382c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800382c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003821e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003821e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(v21, OutputString, 2048, v18);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v21, v18);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v21, 0, 0, v18);
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
0x180038060  mov     [rsp-8+arg_18], rbx
0x180038065  push    rbp
0x180038066  push    rsi
0x180038067  push    rdi
0x180038068  push    r12
0x18003806a  push    r13
0x18003806c  push    r14
0x18003806e  push    r15
0x180038070  lea     rbp, [rsp-13C0h]
0x180038078  mov     eax, 14C0h
0x18003807d  call    _alloca_probe
0x180038082  sub     rsp, rax
0x180038085  mov     r14, r8
0x180038088  mov     esi, edx
0x18003808a  mov     rbx, rcx
0x18003808d  mov     r15, [rbp+13F0h+arg_28]
0x180038094  xor     r13d, r13d
0x180038097  cmp     cs:g_pfnThrowPlatformException, r13
0x18003809e  setnz   dil
0x1800380a2  xor     edx, edx; Val
0x1800380a4  mov     r8d, 98h; Size
0x1800380aa  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800380af  call    memset
0x1800380b4  nop
0x1800380b5  mov     [rbp+13F0h+OutputString], r13w
0x1800380bd  mov     [rbp+13F0h+var_1430], r13b
0x1800380c1  mov     rdx, [rbp+13F0h+arg_30]; int
0x1800380c8  mov     ecx, [rdx]; this
0x1800380ca  mov     [rsp+14F0h+var_14C8], ecx
0x1800380ce  mov     eax, [rdx+4]
0x1800380d1  mov     [rsp+14F0h+var_14C4], eax
0x1800380d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800380da  mov     r12d, eax
0x1800380dd  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x1800380e2  mov     ecx, r13d
0x1800380e5  lea     eax, [r13+8]
0x1800380e9  cmp     dword ptr [rdx+8], 1
0x1800380ed  cmovz   ecx, eax
0x1800380f0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800380f4  lea     ecx, [rax-7]
0x1800380f7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800380ff  inc     ecx
0x180038101  mov     [rsp+14F0h+var_14C0], ecx
0x180038105  mov     rcx, [rbp+13F0h+arg_38]
0x18003810c  test    rcx, rcx
0x18003810f  jz      short loc_18003811C
0x180038111  cmp     [rcx], r13w
0x180038115  mov     [rsp+14F0h+var_14B8], rcx
0x18003811a  jnz     short loc_180038121
0x18003811c  mov     [rsp+14F0h+var_14B8], r13
0x180038121  call    cs:__imp_GetCurrentThreadId
0x180038127  mov     [rsp+14F0h+var_14B0], eax
0x18003812b  mov     [rsp+14F0h+var_1498], r14
0x180038130  mov     [rsp+14F0h+var_1490], esi
0x180038134  mov     [rsp+14F0h+var_148C], r12d
0x180038139  mov     [rsp+14F0h+var_14A8], r13
0x18003813e  mov     [rsp+14F0h+var_14A0], r13
0x180038143  mov     [rbp+13F0h+var_1448], r15
0x180038147  mov     [rbp+13F0h+var_1440], rbx
0x18003814b  mov     [rsp+14F0h+var_1488], r13
0x180038150  xorps   xmm0, xmm0
0x180038153  xor     eax, eax
0x180038155  movups  [rbp+13F0h+var_1468], xmm0
0x180038159  mov     [rbp+13F0h+var_1458], rax
0x18003815d  xorps   xmm1, xmm1
0x180038160  movups  [rsp+14F0h+var_1480], xmm1
0x180038165  mov     [rbp+13F0h+var_1470], rax
0x180038169  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180038170  test    rax, rax
0x180038173  jz      short loc_180038180
0x180038175  call    _guard_dispatch_icall
0x18003817a  mov     [rbp+13F0h+var_1450], rax
0x18003817e  jmp     short loc_180038184
0x180038180  mov     [rbp+13F0h+var_1450], r13
0x180038184  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003818b  test    rax, rax
0x18003818e  jz      short loc_18003819A
0x180038190  lea     rcx, [rsp+14F0h+var_14D0]
0x180038195  call    _guard_dispatch_icall
0x18003819a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800381a1  test    rax, rax
0x1800381a4  jz      short loc_1800381BA
0x1800381a6  mov     r8d, 400h
0x1800381ac  lea     rdx, [rbp+13F0h+var_1430]
0x1800381b0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800381b5  call    _guard_dispatch_icall
0x1800381ba  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800381c1  test    rax, rax
0x1800381c4  jz      short loc_1800381D0
0x1800381c6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800381cb  call    _guard_dispatch_icall
0x1800381d0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800381d7  test    rax, rax
0x1800381da  jz      short loc_1800381F2
0x1800381dc  test    dil, dil
0x1800381df  jnz     short loc_1800381F2
0x1800381e1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800381e6  jnz     short loc_1800381F2
0x1800381e8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800381ed  call    _guard_dispatch_icall
0x1800381f2  cmp     [rsp+14F0h+var_14C8], r13d
0x1800381f7  jl      short loc_1800381FF
0x1800381f9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800381ff  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180038206  jnz     short loc_180038230
0x180038208  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003820f  test    rax, rax
0x180038212  jz      short loc_18003821E
0x180038214  call    _guard_dispatch_icall
0x180038219  movzx   ecx, al
0x18003821c  jmp     short loc_18003822C
0x18003821e  call    cs:__imp_IsDebuggerPresent
0x180038224  mov     ecx, r13d
0x180038227  test    eax, eax
0x180038229  setnz   cl
0x18003822c  test    ecx, ecx
0x18003822e  jz      short loc_180038239
0x180038230  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180038235  mov     bl, 1
0x180038237  jz      short loc_18003823C
0x180038239  mov     bl, r13b
0x18003823c  test    dil, dil
0x18003823f  jnz     short loc_18003826B
0x180038241  test    bl, bl
0x180038243  jnz     short loc_18003826B
0x180038245  mov     rax, cs:g_pfnResultLoggingCallback
0x18003824c  test    rax, rax
0x18003824f  jz      short loc_1800382C8
0x180038251  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180038258  jnz     short loc_1800382C8
0x18003825a  xor     r8d, r8d
0x18003825d  xor     edx, edx
0x18003825f  lea     rcx, [rsp+14F0h+var_14D0]
0x180038264  call    _guard_dispatch_icall
0x180038269  jmp     short loc_1800382C8
0x18003826b  mov     esi, 800h
0x180038270  mov     rax, cs:g_pfnResultLoggingCallback
0x180038277  test    rax, rax
0x18003827a  jz      short loc_180038299
0x18003827c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180038283  jnz     short loc_180038299
0x180038285  mov     r8d, esi
0x180038288  lea     rdx, [rbp+13F0h+OutputString]
0x18003828f  lea     rcx, [rsp+14F0h+var_14D0]
0x180038294  call    _guard_dispatch_icall
0x180038299  cmp     [rbp+13F0h+OutputString], r13w
0x1800382a1  jnz     short loc_1800382B7
0x1800382a3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800382a8  mov     rdx, rsi; wchar_t *
0x1800382ab  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800382b2  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800382b7  test    bl, bl
0x1800382b9  jz      short loc_1800382C8
0x1800382bb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800382c2  call    cs:__imp_OutputDebugStringW
0x1800382c8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800382cd  jnz     short loc_1800382D8
0x1800382cf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800382d6  jz      short loc_1800382EA
0x1800382d8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800382df  test    rax, rax
0x1800382e2  jz      short loc_1800382EA
0x1800382e4  call    _guard_dispatch_icall
0x1800382e9  nop
0x1800382ea  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800382ef  jz      short loc_1800382FC
0x1800382f1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800382f6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800382fc  test    dil, dil
0x1800382ff  jz      short loc_180038319
0x180038301  lea     rdx, [rbp+13F0h+OutputString]
0x180038308  lea     rcx, [rsp+14F0h+var_14D0]
0x18003830d  mov     rax, cs:g_pfnThrowPlatformException
0x180038314  call    _guard_dispatch_icall
0x180038319  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18003831e  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180038323  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180038328  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
