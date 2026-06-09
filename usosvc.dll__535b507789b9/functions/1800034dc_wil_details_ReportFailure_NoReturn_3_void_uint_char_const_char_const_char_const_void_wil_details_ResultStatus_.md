# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800034dc`
- end: `0x18000373e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003278`

## callees

- `0x180003198`
- `0x1800034dc`
- `0x180004964`
- `0x18000510c`
- `0x180005830`
- `0x180006790`
- `0x18000e400`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000357e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000357e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003681`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003681`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000370b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000370b`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x1800034dc  mov     [rsp-8+arg_18], rbx
0x1800034e1  push    rbp
0x1800034e2  push    rsi
0x1800034e3  push    rdi
0x1800034e4  push    r12
0x1800034e6  push    r13
0x1800034e8  push    r14
0x1800034ea  push    r15
0x1800034ec  lea     rbp, [rsp-13C0h]
0x1800034f4  mov     eax, 14C0h
0x1800034f9  call    _alloca_probe
0x1800034fe  sub     rsp, rax
0x180003501  mov     r15, r8
0x180003504  mov     r14d, edx
0x180003507  mov     r12, rcx
0x18000350a  mov     rsi, [rbp+13F0h+arg_28]
0x180003511  xor     edx, edx; Val
0x180003513  mov     r8d, 98h; Size
0x180003519  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000351e  call    memset_0
0x180003523  nop
0x180003524  xor     r13d, r13d
0x180003527  mov     [rbp+13F0h+OutputString], r13w
0x18000352f  mov     [rbp+13F0h+var_1430], r13b
0x180003533  mov     rbx, [rbp+13F0h+arg_30]
0x18000353a  mov     ecx, [rbx]; this
0x18000353c  mov     [rsp+14F0h+var_14C8], ecx
0x180003540  mov     eax, [rbx+4]
0x180003543  mov     [rsp+14F0h+var_14C4], eax
0x180003547  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000354c  mov     edi, eax
0x18000354e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003556  mov     ecx, r13d
0x180003559  lea     eax, [r13+8]
0x18000355d  cmp     dword ptr [rbx+8], 1
0x180003561  cmovz   ecx, eax
0x180003564  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003568  lea     ecx, [rax-7]
0x18000356b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003573  inc     ecx
0x180003575  mov     [rsp+14F0h+var_14C0], ecx
0x180003579  mov     [rsp+14F0h+var_14B8], r13
0x18000357e  call    cs:__imp_GetCurrentThreadId
0x180003584  mov     [rsp+14F0h+var_14B0], eax
0x180003588  mov     [rsp+14F0h+var_1498], r15
0x18000358d  mov     [rsp+14F0h+var_1490], r14d
0x180003592  mov     [rsp+14F0h+var_148C], edi
0x180003596  mov     [rsp+14F0h+var_14A8], r13
0x18000359b  mov     [rsp+14F0h+var_14A0], r13
0x1800035a0  mov     [rbp+13F0h+var_1448], rsi
0x1800035a4  mov     [rbp+13F0h+var_1440], r12
0x1800035a8  mov     [rsp+14F0h+var_1488], r13
0x1800035ad  xorps   xmm0, xmm0
0x1800035b0  xor     eax, eax
0x1800035b2  movups  [rbp+13F0h+var_1468], xmm0
0x1800035b6  mov     [rbp+13F0h+var_1458], rax
0x1800035ba  xorps   xmm1, xmm1
0x1800035bd  movups  [rsp+14F0h+var_1480], xmm1
0x1800035c2  mov     [rbp+13F0h+var_1470], rax
0x1800035c6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800035cd  test    rax, rax
0x1800035d0  jz      short loc_1800035DD
0x1800035d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d7  mov     [rbp+13F0h+var_1450], rax
0x1800035db  jmp     short loc_1800035E1
0x1800035dd  mov     [rbp+13F0h+var_1450], r13
0x1800035e1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800035e8  test    rax, rax
0x1800035eb  jz      short loc_1800035F7
0x1800035ed  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800035fe  test    rax, rax
0x180003601  jz      short loc_180003617
0x180003603  mov     r8d, 400h
0x180003609  lea     rdx, [rbp+13F0h+var_1430]
0x18000360d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003617  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000361e  test    rax, rax
0x180003621  jz      short loc_18000362D
0x180003623  lea     rcx, [rsp+14F0h+var_14D0]
0x180003628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000362d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003634  test    rax, rax
0x180003637  jz      short loc_18000364A
0x180003639  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000363e  jnz     short loc_18000364A
0x180003640  lea     rcx, [rsp+14F0h+var_14D0]
0x180003645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000364a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000364f  jl      short loc_180003663
0x180003651  mov     ecx, 8000FFFFh; this
0x180003656  mov     [rsp+14F0h+var_14C8], ecx
0x18000365a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000365f  mov     [rsp+14F0h+var_14C4], eax
0x180003663  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000366a  jnz     short loc_18000368B
0x18000366c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003673  test    rax, rax
0x180003676  jz      short loc_180003681
0x180003678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000367d  test    al, al
0x18000367f  jmp     short loc_180003689
0x180003681  call    cs:__imp_IsDebuggerPresent
0x180003687  test    eax, eax
0x180003689  jz      short loc_180003692
0x18000368b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003690  jz      short loc_1800036B8
0x180003692  mov     rax, cs:g_pfnResultLoggingCallback
0x180003699  test    rax, rax
0x18000369c  jz      short loc_180003711
0x18000369e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800036a5  jnz     short loc_180003711
0x1800036a7  xor     r8d, r8d
0x1800036aa  xor     edx, edx
0x1800036ac  lea     rcx, [rsp+14F0h+var_14D0]
0x1800036b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b6  jmp     short loc_180003711
0x1800036b8  mov     ebx, 800h
0x1800036bd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036c4  test    rax, rax
0x1800036c7  jz      short loc_1800036E6
0x1800036c9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800036d0  jnz     short loc_1800036E6
0x1800036d2  mov     r8d, ebx
0x1800036d5  lea     rdx, [rbp+13F0h+OutputString]
0x1800036dc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800036e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036e6  cmp     [rbp+13F0h+OutputString], r13w
0x1800036ee  jnz     short loc_180003704
0x1800036f0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800036f5  mov     rdx, rbx; unsigned __int16 *
0x1800036f8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800036ff  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003704  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000370b  call    cs:__imp_OutputDebugStringW
0x180003711  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003716  jnz     short loc_180003721
0x180003718  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000371f  jz      short loc_180003733
0x180003721  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003728  test    rax, rax
0x18000372b  jz      short loc_180003733
0x18000372d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003732  nop
0x180003733  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003738  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
