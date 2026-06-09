# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003368`
- end: `0x14000360a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `674`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002e38`

## callees

- `0x140001c8f`
- `0x140003368`
- `0x140004424`
- `0x140005350`
- `0x140006c50`
- `0x140006e2c`
- `0x140007770`
- `0x140007830`
- `0x140008010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14000351a`
- `KERNEL32!IsDebuggerPresent` at `0x14000351a`
- `KERNEL32!OutputDebugStringW` at `0x1400035a4`
- `KERNEL32!OutputDebugStringW` at `0x1400035a4`
- `KERNEL32!GetCurrentThreadId` at `0x14000341f`
- `KERNEL32!GetCurrentThreadId` at `0x14000341f`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  char v37[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v36 = -2;
  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x140003368  push    rbp
0x14000336a  push    rsi
0x14000336b  push    rdi
0x14000336c  push    r14
0x14000336e  push    r15
0x140003370  lea     rbp, [rsp-13E0h]
0x140003378  mov     eax, 14E0h
0x14000337d  call    _alloca_probe
0x140003382  sub     rsp, rax
0x140003385  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x14000338d  mov     [rsp+1500h+arg_10], rbx
0x140003395  mov     rax, cs:__security_cookie
0x14000339c  xor     rax, rsp
0x14000339f  mov     [rbp+1400h+var_30], rax
0x1400033a6  mov     esi, edx
0x1400033a8  mov     r14, rcx
0x1400033ab  mov     rdi, [rbp+1400h+arg_28]
0x1400033b2  xor     edx, edx; Val
0x1400033b4  mov     r8d, 98h; Size
0x1400033ba  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400033bf  call    memset_0
0x1400033c4  nop
0x1400033c5  xor     r15d, r15d
0x1400033c8  mov     [rbp+1400h+OutputString], r15w
0x1400033d0  mov     [rbp+1400h+var_1430], r15b
0x1400033d4  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1400033db  mov     ecx, [rdx]; this
0x1400033dd  mov     [rsp+1500h+var_14D8], ecx
0x1400033e1  mov     eax, [rdx+4]
0x1400033e4  mov     [rsp+1500h+var_14D4], eax
0x1400033e8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400033ed  mov     ebx, eax
0x1400033ef  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400033f7  mov     ecx, r15d
0x1400033fa  lea     eax, [r15+8]
0x1400033fe  cmp     dword ptr [rdx+8], 1
0x140003402  cmovz   ecx, eax
0x140003405  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003409  lea     ecx, [rax-7]
0x14000340c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003414  inc     ecx
0x140003416  mov     [rsp+1500h+var_14D0], ecx
0x14000341a  mov     [rsp+1500h+var_14C8], r15
0x14000341f  call    cs:__imp_GetCurrentThreadId
0x140003425  mov     [rsp+1500h+var_14C0], eax
0x140003429  lea     rax, aWil; "wil"
0x140003430  mov     [rsp+1500h+var_14A8], rax
0x140003435  mov     [rsp+1500h+var_14A0], esi
0x140003439  mov     [rsp+1500h+var_149C], ebx
0x14000343d  mov     [rsp+1500h+var_14B8], r15
0x140003442  mov     [rsp+1500h+var_14B0], r15
0x140003447  mov     [rbp+1400h+var_1458], rdi
0x14000344b  mov     [rbp+1400h+var_1450], r14
0x14000344f  mov     [rsp+1500h+var_1498], r15
0x140003454  xorps   xmm0, xmm0
0x140003457  xor     eax, eax
0x140003459  movups  [rbp+1400h+var_1478], xmm0
0x14000345d  mov     [rbp+1400h+var_1468], rax
0x140003461  xorps   xmm1, xmm1
0x140003464  movups  [rsp+1500h+var_1490], xmm1
0x140003469  mov     [rbp+1400h+var_1480], rax
0x14000346d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003474  test    rax, rax
0x140003477  jz      short loc_140003484
0x140003479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000347e  mov     [rbp+1400h+var_1460], rax
0x140003482  jmp     short loc_140003488
0x140003484  mov     [rbp+1400h+var_1460], r15
0x140003488  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000348f  test    rax, rax
0x140003492  jz      short loc_14000349E
0x140003494  lea     rcx, [rsp+1500h+var_14E0]
0x140003499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000349e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400034a5  test    rax, rax
0x1400034a8  jz      short loc_1400034BE
0x1400034aa  mov     r8d, 400h
0x1400034b0  lea     rdx, [rbp+1400h+var_1430]
0x1400034b4  lea     rcx, [rsp+1500h+var_14E0]
0x1400034b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034be  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400034c5  test    rax, rax
0x1400034c8  jz      short loc_1400034D4
0x1400034ca  lea     rcx, [rsp+1500h+var_14E0]
0x1400034cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034d4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400034db  test    rax, rax
0x1400034de  jz      short loc_1400034F1
0x1400034e0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400034e5  jnz     short loc_1400034F1
0x1400034e7  lea     rcx, [rsp+1500h+var_14E0]
0x1400034ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034f1  cmp     [rsp+1500h+var_14D8], r15d
0x1400034f6  jge     loc_140003604
0x1400034fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140003503  jnz     short loc_140003524
0x140003505  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000350c  test    rax, rax
0x14000350f  jz      short loc_14000351A
0x140003511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003516  test    al, al
0x140003518  jmp     short loc_140003522
0x14000351a  call    cs:__imp_IsDebuggerPresent
0x140003520  test    eax, eax
0x140003522  jz      short loc_14000352B
0x140003524  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003529  jz      short loc_140003551
0x14000352b  mov     rax, cs:g_pfnResultLoggingCallback
0x140003532  test    rax, rax
0x140003535  jz      short loc_1400035AA
0x140003537  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000353e  jnz     short loc_1400035AA
0x140003540  xor     r8d, r8d
0x140003543  xor     edx, edx
0x140003545  lea     rcx, [rsp+1500h+var_14E0]
0x14000354a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000354f  jmp     short loc_1400035AA
0x140003551  mov     ebx, 800h
0x140003556  mov     rax, cs:g_pfnResultLoggingCallback
0x14000355d  test    rax, rax
0x140003560  jz      short loc_14000357F
0x140003562  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003569  jnz     short loc_14000357F
0x14000356b  mov     r8d, ebx
0x14000356e  lea     rdx, [rbp+1400h+OutputString]
0x140003575  lea     rcx, [rsp+1500h+var_14E0]
0x14000357a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000357f  cmp     [rbp+1400h+OutputString], r15w
0x140003587  jnz     short loc_14000359D
0x140003589  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000358e  mov     rdx, rbx; unsigned __int16 *
0x140003591  lea     rcx, [rbp+1400h+OutputString]; this
0x140003598  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000359d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400035a4  call    cs:__imp_OutputDebugStringW
0x1400035aa  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400035af  jnz     short loc_1400035BA
0x1400035b1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400035b8  jz      short loc_1400035CC
0x1400035ba  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400035c1  test    rax, rax
0x1400035c4  jz      short loc_1400035CC
0x1400035c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035cb  nop
0x1400035cc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400035d1  jnz     short loc_1400035F9
0x1400035d3  mov     rcx, [rbp+1400h+var_30]
0x1400035da  xor     rcx, rsp; StackCookie
0x1400035dd  call    __security_check_cookie
0x1400035e2  mov     rbx, [rsp+1500h+arg_10]
0x1400035ea  add     rsp, 14E0h
0x1400035f1  pop     r15
0x1400035f3  pop     r14
0x1400035f5  pop     rdi
0x1400035f6  pop     rsi
0x1400035f7  pop     rbp
0x1400035f8  retn
0x1400035f9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400035fe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140003604  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
