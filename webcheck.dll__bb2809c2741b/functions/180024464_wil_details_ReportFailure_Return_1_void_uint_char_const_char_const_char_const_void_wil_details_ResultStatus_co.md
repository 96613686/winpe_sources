# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180024464`
- end: `0x1800246f8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180024138`

## callees

- `0x180024464`
- `0x1800250c4`
- `0x180026850`
- `0x180027068`
- `0x180027144`
- `0x18002924e`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002450e`
- `KERNEL32!GetCurrentThreadId` at `0x18002450e`
- `KERNEL32!OutputDebugStringW` at `0x180024693`
- `KERNEL32!OutputDebugStringW` at `0x180024693`
- `KERNEL32!IsDebuggerPresent` at `0x180024609`
- `KERNEL32!IsDebuggerPresent` at `0x180024609`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180024464  mov     [rsp-8+arg_10], rbx
0x180024469  push    rbp
0x18002446a  push    rsi
0x18002446b  push    rdi
0x18002446c  push    r14
0x18002446e  push    r15
0x180024470  lea     rbp, [rsp-13D0h]
0x180024478  mov     eax, 14D0h
0x18002447d  call    _alloca_probe
0x180024482  sub     rsp, rax
0x180024485  mov     rax, cs:__security_cookie
0x18002448c  xor     rax, rsp
0x18002448f  mov     [rbp+13F0h+var_30], rax
0x180024496  mov     rdi, [rbp+13F0h+arg_28]
0x18002449d  mov     esi, edx
0x18002449f  mov     r14, rcx
0x1800244a2  xor     edx, edx; Val
0x1800244a4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800244a9  mov     r8d, 98h; Size
0x1800244af  call    memset_0
0x1800244b4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800244bb  xor     r15d, r15d
0x1800244be  mov     [rbp+13F0h+OutputString], r15w
0x1800244c6  mov     [rbp+13F0h+var_1430], r15b
0x1800244ca  mov     ecx, [rdx]; this
0x1800244cc  mov     eax, [rdx+4]
0x1800244cf  mov     [rsp+14F0h+var_14C8], ecx
0x1800244d3  mov     [rsp+14F0h+var_14C4], eax
0x1800244d7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800244dc  cmp     dword ptr [rdx+8], 1
0x1800244e0  mov     ebx, eax
0x1800244e2  lea     eax, [r15+8]
0x1800244e6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800244ee  mov     ecx, r15d
0x1800244f1  cmovz   ecx, eax
0x1800244f4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800244f8  lea     ecx, [rax-7]
0x1800244fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180024503  inc     ecx
0x180024505  mov     [rsp+14F0h+var_14B8], r15
0x18002450a  mov     [rsp+14F0h+var_14C0], ecx
0x18002450e  call    cs:__imp_GetCurrentThreadId
0x180024514  xorps   xmm0, xmm0
0x180024517  mov     [rsp+14F0h+var_1490], esi
0x18002451b  mov     [rsp+14F0h+var_14B0], eax
0x18002451f  xorps   xmm1, xmm1
0x180024522  lea     rax, aWil; "wil"
0x180024529  mov     [rsp+14F0h+var_148C], ebx
0x18002452d  mov     [rsp+14F0h+var_1498], rax
0x180024532  xor     eax, eax
0x180024534  mov     [rbp+13F0h+var_1458], rax
0x180024538  mov     [rbp+13F0h+var_1470], rax
0x18002453c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180024543  mov     [rsp+14F0h+var_14A8], r15
0x180024548  mov     [rsp+14F0h+var_14A0], r15
0x18002454d  mov     [rbp+13F0h+var_1448], rdi
0x180024551  mov     [rbp+13F0h+var_1440], r14
0x180024555  mov     [rsp+14F0h+var_1488], r15
0x18002455a  movups  [rbp+13F0h+var_1468], xmm0
0x18002455e  movups  [rsp+14F0h+var_1480], xmm1
0x180024563  test    rax, rax
0x180024566  jz      short loc_180024573
0x180024568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002456d  mov     [rbp+13F0h+var_1450], rax
0x180024571  jmp     short loc_180024577
0x180024573  mov     [rbp+13F0h+var_1450], r15
0x180024577  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002457e  test    rax, rax
0x180024581  jz      short loc_18002458D
0x180024583  lea     rcx, [rsp+14F0h+var_14D0]
0x180024588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002458d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180024594  test    rax, rax
0x180024597  jz      short loc_1800245AD
0x180024599  mov     r8d, 400h
0x18002459f  lea     rdx, [rbp+13F0h+var_1430]
0x1800245a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800245a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245ad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800245b4  test    rax, rax
0x1800245b7  jz      short loc_1800245C3
0x1800245b9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800245be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245c3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800245ca  test    rax, rax
0x1800245cd  jz      short loc_1800245E0
0x1800245cf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800245d4  jnz     short loc_1800245E0
0x1800245d6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800245db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245e0  cmp     [rsp+14F0h+var_14C8], r15d
0x1800245e5  jge     loc_1800246E7
0x1800245eb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800245f2  jnz     short loc_180024613
0x1800245f4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800245fb  test    rax, rax
0x1800245fe  jz      short loc_180024609
0x180024600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024605  test    al, al
0x180024607  jmp     short loc_180024611
0x180024609  call    cs:__imp_IsDebuggerPresent
0x18002460f  test    eax, eax
0x180024611  jz      short loc_18002461A
0x180024613  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180024618  jz      short loc_180024640
0x18002461a  mov     rax, cs:g_pfnResultLoggingCallback
0x180024621  test    rax, rax
0x180024624  jz      short loc_180024699
0x180024626  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002462d  jnz     short loc_180024699
0x18002462f  xor     r8d, r8d
0x180024632  lea     rcx, [rsp+14F0h+var_14D0]
0x180024637  xor     edx, edx
0x180024639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002463e  jmp     short loc_180024699
0x180024640  mov     rax, cs:g_pfnResultLoggingCallback
0x180024647  mov     ebx, 800h
0x18002464c  test    rax, rax
0x18002464f  jz      short loc_18002466E
0x180024651  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180024658  jnz     short loc_18002466E
0x18002465a  mov     r8d, ebx
0x18002465d  lea     rdx, [rbp+13F0h+OutputString]
0x180024664  lea     rcx, [rsp+14F0h+var_14D0]
0x180024669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002466e  cmp     [rbp+13F0h+OutputString], r15w
0x180024676  jnz     short loc_18002468C
0x180024678  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002467d  mov     rdx, rbx; unsigned __int16 *
0x180024680  lea     rcx, [rbp+13F0h+OutputString]; this
0x180024687  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002468c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180024693  call    cs:__imp_OutputDebugStringW
0x180024699  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002469e  jnz     short loc_1800246A9
0x1800246a0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800246a7  jz      short loc_1800246BA
0x1800246a9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800246b0  test    rax, rax
0x1800246b3  jz      short loc_1800246BA
0x1800246b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246ba  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800246bf  jnz     short loc_1800246ED
0x1800246c1  mov     rcx, [rbp+13F0h+var_30]
0x1800246c8  xor     rcx, rsp; StackCookie
0x1800246cb  call    __security_check_cookie
0x1800246d0  mov     rbx, [rsp+14F0h+arg_10]
0x1800246d8  add     rsp, 14D0h
0x1800246df  pop     r15
0x1800246e1  pop     r14
0x1800246e3  pop     rdi
0x1800246e4  pop     rsi
0x1800246e5  pop     rbp
0x1800246e6  retn
0x1800246e7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800246ed  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800246f2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
