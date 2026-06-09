# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180003394`
- end: `0x180003640`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002e90`

## callees

- `0x1800028b4`
- `0x180003394`
- `0x180006b04`
- `0x1800085e0`
- `0x18000b780`
- `0x18000c2e0`
- `0x18000c558`
- `0x180019850`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000343d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000343d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003538`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003538`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800035d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800035d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x180003394  mov     [rsp-8+arg_18], rbx
0x180003399  push    rbp
0x18000339a  push    rsi
0x18000339b  push    rdi
0x18000339c  push    r12
0x18000339e  push    r13
0x1800033a0  push    r14
0x1800033a2  push    r15
0x1800033a4  lea     rbp, [rsp-13C0h]
0x1800033ac  mov     eax, 14C0h
0x1800033b1  call    _alloca_probe
0x1800033b6  sub     rsp, rax
0x1800033b9  mov     r14, r8
0x1800033bc  mov     esi, edx
0x1800033be  mov     r15, rcx
0x1800033c1  mov     rdi, [rbp+13F0h+arg_28]
0x1800033c8  xor     r13d, r13d
0x1800033cb  cmp     cs:g_pfnThrowPlatformException, r13
0x1800033d2  setnz   r12b
0x1800033d6  xor     edx, edx; Val
0x1800033d8  mov     r8d, 98h; Size
0x1800033de  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800033e3  call    memset_0
0x1800033e8  nop
0x1800033e9  mov     [rbp+13F0h+OutputString], r13w
0x1800033f1  mov     [rbp+13F0h+var_1430], r13b
0x1800033f5  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800033fc  mov     ecx, [rdx]; this
0x1800033fe  mov     [rsp+14F0h+var_14C8], ecx
0x180003402  mov     eax, [rdx+4]
0x180003405  mov     [rsp+14F0h+var_14C4], eax
0x180003409  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000340e  mov     ebx, eax
0x180003410  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180003415  mov     ecx, r13d
0x180003418  lea     eax, [r13+8]
0x18000341c  cmp     dword ptr [rdx+8], 1
0x180003420  cmovz   ecx, eax
0x180003423  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003427  lea     ecx, [rax-7]
0x18000342a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003432  inc     ecx
0x180003434  mov     [rsp+14F0h+var_14C0], ecx
0x180003438  mov     [rsp+14F0h+var_14B8], r13
0x18000343d  call    cs:__imp_GetCurrentThreadId
0x180003443  mov     [rsp+14F0h+var_14B0], eax
0x180003447  mov     [rsp+14F0h+var_1498], r14
0x18000344c  mov     [rsp+14F0h+var_1490], esi
0x180003450  mov     [rsp+14F0h+var_148C], ebx
0x180003454  mov     [rsp+14F0h+var_14A8], r13
0x180003459  mov     [rsp+14F0h+var_14A0], r13
0x18000345e  mov     [rbp+13F0h+var_1448], rdi
0x180003462  mov     [rbp+13F0h+var_1440], r15
0x180003466  mov     [rsp+14F0h+var_1488], r13
0x18000346b  xorps   xmm0, xmm0
0x18000346e  xor     eax, eax
0x180003470  movups  [rbp+13F0h+var_1468], xmm0
0x180003474  mov     [rbp+13F0h+var_1458], rax
0x180003478  xorps   xmm1, xmm1
0x18000347b  movups  [rsp+14F0h+var_1480], xmm1
0x180003480  mov     [rbp+13F0h+var_1470], rax
0x180003484  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000348b  test    rax, rax
0x18000348e  jz      short loc_18000349B
0x180003490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003495  mov     [rbp+13F0h+var_1450], rax
0x180003499  jmp     short loc_18000349F
0x18000349b  mov     [rbp+13F0h+var_1450], r13
0x18000349f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800034a6  test    rax, rax
0x1800034a9  jz      short loc_1800034B5
0x1800034ab  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800034bc  test    rax, rax
0x1800034bf  jz      short loc_1800034D5
0x1800034c1  mov     r8d, 400h
0x1800034c7  lea     rdx, [rbp+13F0h+var_1430]
0x1800034cb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800034dc  test    rax, rax
0x1800034df  jz      short loc_1800034EB
0x1800034e1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034eb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800034f2  test    rax, rax
0x1800034f5  jz      short loc_18000350D
0x1800034f7  test    r12b, r12b
0x1800034fa  jnz     short loc_18000350D
0x1800034fc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003501  jnz     short loc_18000350D
0x180003503  lea     rcx, [rsp+14F0h+var_14D0]
0x180003508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000350d  cmp     [rsp+14F0h+var_14C8], r13d
0x180003512  jl      short loc_18000351A
0x180003514  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000351a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003521  jnz     short loc_180003542
0x180003523  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000352a  test    rax, rax
0x18000352d  jz      short loc_180003538
0x18000352f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003534  test    al, al
0x180003536  jmp     short loc_180003540
0x180003538  call    cs:__imp_IsDebuggerPresent
0x18000353e  test    eax, eax
0x180003540  jz      short loc_18000354B
0x180003542  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003547  mov     bl, 1
0x180003549  jz      short loc_18000354E
0x18000354b  mov     bl, r13b
0x18000354e  test    r12b, r12b
0x180003551  jnz     short loc_18000357D
0x180003553  test    bl, bl
0x180003555  jnz     short loc_18000357D
0x180003557  mov     rax, cs:g_pfnResultLoggingCallback
0x18000355e  test    rax, rax
0x180003561  jz      short loc_1800035DA
0x180003563  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000356a  jnz     short loc_1800035DA
0x18000356c  xor     r8d, r8d
0x18000356f  xor     edx, edx
0x180003571  lea     rcx, [rsp+14F0h+var_14D0]
0x180003576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000357b  jmp     short loc_1800035DA
0x18000357d  mov     edi, 800h
0x180003582  mov     rax, cs:g_pfnResultLoggingCallback
0x180003589  test    rax, rax
0x18000358c  jz      short loc_1800035AB
0x18000358e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003595  jnz     short loc_1800035AB
0x180003597  mov     r8d, edi
0x18000359a  lea     rdx, [rbp+13F0h+OutputString]
0x1800035a1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ab  cmp     [rbp+13F0h+OutputString], r13w
0x1800035b3  jnz     short loc_1800035C9
0x1800035b5  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800035ba  mov     rdx, rdi; wchar_t *
0x1800035bd  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800035c4  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800035c9  test    bl, bl
0x1800035cb  jz      short loc_1800035DA
0x1800035cd  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800035d4  call    cs:__imp_OutputDebugStringW
0x1800035da  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800035df  jnz     short loc_1800035EA
0x1800035e1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800035e8  jz      short loc_1800035FC
0x1800035ea  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800035f1  test    rax, rax
0x1800035f4  jz      short loc_1800035FC
0x1800035f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035fb  nop
0x1800035fc  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003601  jz      short loc_18000360E
0x180003603  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003608  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000360e  test    r12b, r12b
0x180003611  jz      short loc_18000362B
0x180003613  lea     rdx, [rbp+13F0h+OutputString]
0x18000361a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000361f  mov     rax, cs:g_pfnThrowPlatformException
0x180003626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000362b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003630  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180003635  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000363a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
