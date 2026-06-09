# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800035e0`
- end: `0x18000388c`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003080`

## callees

- `0x180002b38`
- `0x1800035e0`
- `0x180007e34`
- `0x18000a128`
- `0x18000c798`
- `0x18000d030`
- `0x18000d1fc`
- `0x180014400`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003689`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003689`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003820`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003820`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003784`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003784`

## pseudocode

```c
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
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
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
0x1800035e0  mov     [rsp-8+arg_18], rbx
0x1800035e5  push    rbp
0x1800035e6  push    rsi
0x1800035e7  push    rdi
0x1800035e8  push    r12
0x1800035ea  push    r13
0x1800035ec  push    r14
0x1800035ee  push    r15
0x1800035f0  lea     rbp, [rsp-13C0h]
0x1800035f8  mov     eax, 14C0h
0x1800035fd  call    _alloca_probe
0x180003602  sub     rsp, rax
0x180003605  mov     r14, r8
0x180003608  mov     esi, edx
0x18000360a  mov     r15, rcx
0x18000360d  mov     rdi, [rbp+13F0h+arg_28]
0x180003614  xor     r13d, r13d
0x180003617  cmp     cs:g_pfnThrowPlatformException, r13
0x18000361e  setnz   r12b
0x180003622  xor     edx, edx; Val
0x180003624  mov     r8d, 98h; Size
0x18000362a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000362f  call    memset_0
0x180003634  nop
0x180003635  mov     [rbp+13F0h+OutputString], r13w
0x18000363d  mov     [rbp+13F0h+var_1430], r13b
0x180003641  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003648  mov     ecx, [rdx]; this
0x18000364a  mov     [rsp+14F0h+var_14C8], ecx
0x18000364e  mov     eax, [rdx+4]
0x180003651  mov     [rsp+14F0h+var_14C4], eax
0x180003655  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000365a  mov     ebx, eax
0x18000365c  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180003661  mov     ecx, r13d
0x180003664  lea     eax, [r13+8]
0x180003668  cmp     dword ptr [rdx+8], 1
0x18000366c  cmovz   ecx, eax
0x18000366f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003673  lea     ecx, [rax-7]
0x180003676  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000367e  inc     ecx
0x180003680  mov     [rsp+14F0h+var_14C0], ecx
0x180003684  mov     [rsp+14F0h+var_14B8], r13
0x180003689  call    cs:__imp_GetCurrentThreadId
0x18000368f  mov     [rsp+14F0h+var_14B0], eax
0x180003693  mov     [rsp+14F0h+var_1498], r14
0x180003698  mov     [rsp+14F0h+var_1490], esi
0x18000369c  mov     [rsp+14F0h+var_148C], ebx
0x1800036a0  mov     [rsp+14F0h+var_14A8], r13
0x1800036a5  mov     [rsp+14F0h+var_14A0], r13
0x1800036aa  mov     [rbp+13F0h+var_1448], rdi
0x1800036ae  mov     [rbp+13F0h+var_1440], r15
0x1800036b2  mov     [rsp+14F0h+var_1488], r13
0x1800036b7  xorps   xmm0, xmm0
0x1800036ba  xor     eax, eax
0x1800036bc  movups  [rbp+13F0h+var_1468], xmm0
0x1800036c0  mov     [rbp+13F0h+var_1458], rax
0x1800036c4  xorps   xmm1, xmm1
0x1800036c7  movups  [rsp+14F0h+var_1480], xmm1
0x1800036cc  mov     [rbp+13F0h+var_1470], rax
0x1800036d0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800036d7  test    rax, rax
0x1800036da  jz      short loc_1800036E7
0x1800036dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036e1  mov     [rbp+13F0h+var_1450], rax
0x1800036e5  jmp     short loc_1800036EB
0x1800036e7  mov     [rbp+13F0h+var_1450], r13
0x1800036eb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800036f2  test    rax, rax
0x1800036f5  jz      short loc_180003701
0x1800036f7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800036fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003701  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003708  test    rax, rax
0x18000370b  jz      short loc_180003721
0x18000370d  mov     r8d, 400h
0x180003713  lea     rdx, [rbp+13F0h+var_1430]
0x180003717  lea     rcx, [rsp+14F0h+var_14D0]
0x18000371c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003721  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003728  test    rax, rax
0x18000372b  jz      short loc_180003737
0x18000372d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003737  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000373e  test    rax, rax
0x180003741  jz      short loc_180003759
0x180003743  test    r12b, r12b
0x180003746  jnz     short loc_180003759
0x180003748  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000374d  jnz     short loc_180003759
0x18000374f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003759  cmp     [rsp+14F0h+var_14C8], r13d
0x18000375e  jl      short loc_180003766
0x180003760  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003766  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000376d  jnz     short loc_18000378E
0x18000376f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003776  test    rax, rax
0x180003779  jz      short loc_180003784
0x18000377b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003780  test    al, al
0x180003782  jmp     short loc_18000378C
0x180003784  call    cs:__imp_IsDebuggerPresent
0x18000378a  test    eax, eax
0x18000378c  jz      short loc_180003797
0x18000378e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003793  mov     bl, 1
0x180003795  jz      short loc_18000379A
0x180003797  mov     bl, r13b
0x18000379a  test    r12b, r12b
0x18000379d  jnz     short loc_1800037C9
0x18000379f  test    bl, bl
0x1800037a1  jnz     short loc_1800037C9
0x1800037a3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037aa  test    rax, rax
0x1800037ad  jz      short loc_180003826
0x1800037af  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800037b6  jnz     short loc_180003826
0x1800037b8  xor     r8d, r8d
0x1800037bb  xor     edx, edx
0x1800037bd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c7  jmp     short loc_180003826
0x1800037c9  mov     edi, 800h
0x1800037ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037d5  test    rax, rax
0x1800037d8  jz      short loc_1800037F7
0x1800037da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800037e1  jnz     short loc_1800037F7
0x1800037e3  mov     r8d, edi
0x1800037e6  lea     rdx, [rbp+13F0h+OutputString]
0x1800037ed  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f7  cmp     [rbp+13F0h+OutputString], r13w
0x1800037ff  jnz     short loc_180003815
0x180003801  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003806  mov     rdx, rdi; wchar_t *
0x180003809  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003810  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003815  test    bl, bl
0x180003817  jz      short loc_180003826
0x180003819  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003820  call    cs:__imp_OutputDebugStringW
0x180003826  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000382b  jnz     short loc_180003836
0x18000382d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003834  jz      short loc_180003848
0x180003836  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000383d  test    rax, rax
0x180003840  jz      short loc_180003848
0x180003842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003847  nop
0x180003848  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000384d  jz      short loc_18000385A
0x18000384f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003854  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000385a  test    r12b, r12b
0x18000385d  jz      short loc_180003877
0x18000385f  lea     rdx, [rbp+13F0h+OutputString]
0x180003866  lea     rcx, [rsp+14F0h+var_14D0]
0x18000386b  mov     rax, cs:g_pfnThrowPlatformException
0x180003872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003877  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000387c  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180003881  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003886  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
