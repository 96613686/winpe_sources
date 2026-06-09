# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180019460`
- end: `0x1800196f4`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180018f48`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180019460`
- `0x18001a8c4`
- `0x18001bb10`
- `0x18001c950`
- `0x18001cb88`
- `0x18001d290`
- `0x18001e010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18001968f`
- `KERNEL32!OutputDebugStringW` at `0x18001968f`
- `KERNEL32!IsDebuggerPresent` at `0x180019605`
- `KERNEL32!IsDebuggerPresent` at `0x180019605`
- `KERNEL32!GetCurrentThreadId` at `0x18001950a`
- `KERNEL32!GetCurrentThreadId` at `0x18001950a`

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
0x180019460  mov     [rsp-8+arg_10], rbx
0x180019465  push    rbp
0x180019466  push    rsi
0x180019467  push    rdi
0x180019468  push    r14
0x18001946a  push    r15
0x18001946c  lea     rbp, [rsp-13D0h]
0x180019474  mov     eax, 14D0h
0x180019479  call    _alloca_probe
0x18001947e  sub     rsp, rax
0x180019481  mov     rax, cs:__security_cookie
0x180019488  xor     rax, rsp
0x18001948b  mov     [rbp+13F0h+var_30], rax
0x180019492  mov     rdi, [rbp+13F0h+arg_28]
0x180019499  mov     esi, edx
0x18001949b  mov     r14, rcx
0x18001949e  xor     edx, edx; Val
0x1800194a0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800194a5  mov     r8d, 98h; Size
0x1800194ab  call    memset_0
0x1800194b0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800194b7  xor     r15d, r15d
0x1800194ba  mov     [rbp+13F0h+OutputString], r15w
0x1800194c2  mov     [rbp+13F0h+var_1430], r15b
0x1800194c6  mov     ecx, [rdx]; this
0x1800194c8  mov     eax, [rdx+4]
0x1800194cb  mov     [rsp+14F0h+var_14C8], ecx
0x1800194cf  mov     [rsp+14F0h+var_14C4], eax
0x1800194d3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800194d8  cmp     dword ptr [rdx+8], 1
0x1800194dc  mov     ebx, eax
0x1800194de  lea     eax, [r15+8]
0x1800194e2  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800194ea  mov     ecx, r15d
0x1800194ed  cmovz   ecx, eax
0x1800194f0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800194f4  lea     ecx, [rax-7]
0x1800194f7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800194ff  inc     ecx
0x180019501  mov     [rsp+14F0h+var_14B8], r15
0x180019506  mov     [rsp+14F0h+var_14C0], ecx
0x18001950a  call    cs:__imp_GetCurrentThreadId
0x180019510  xorps   xmm0, xmm0
0x180019513  mov     [rsp+14F0h+var_1490], esi
0x180019517  mov     [rsp+14F0h+var_14B0], eax
0x18001951b  xorps   xmm1, xmm1
0x18001951e  lea     rax, aWil; "wil"
0x180019525  mov     [rsp+14F0h+var_148C], ebx
0x180019529  mov     [rsp+14F0h+var_1498], rax
0x18001952e  xor     eax, eax
0x180019530  mov     [rbp+13F0h+var_1458], rax
0x180019534  mov     [rbp+13F0h+var_1470], rax
0x180019538  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001953f  mov     [rsp+14F0h+var_14A8], r15
0x180019544  mov     [rsp+14F0h+var_14A0], r15
0x180019549  mov     [rbp+13F0h+var_1448], rdi
0x18001954d  mov     [rbp+13F0h+var_1440], r14
0x180019551  mov     [rsp+14F0h+var_1488], r15
0x180019556  movups  [rbp+13F0h+var_1468], xmm0
0x18001955a  movups  [rsp+14F0h+var_1480], xmm1
0x18001955f  test    rax, rax
0x180019562  jz      short loc_18001956F
0x180019564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019569  mov     [rbp+13F0h+var_1450], rax
0x18001956d  jmp     short loc_180019573
0x18001956f  mov     [rbp+13F0h+var_1450], r15
0x180019573  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001957a  test    rax, rax
0x18001957d  jz      short loc_180019589
0x18001957f  lea     rcx, [rsp+14F0h+var_14D0]
0x180019584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019589  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180019590  test    rax, rax
0x180019593  jz      short loc_1800195A9
0x180019595  mov     r8d, 400h
0x18001959b  lea     rdx, [rbp+13F0h+var_1430]
0x18001959f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800195a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195a9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800195b0  test    rax, rax
0x1800195b3  jz      short loc_1800195BF
0x1800195b5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800195ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195bf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800195c6  test    rax, rax
0x1800195c9  jz      short loc_1800195DC
0x1800195cb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800195d0  jnz     short loc_1800195DC
0x1800195d2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800195d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195dc  cmp     [rsp+14F0h+var_14C8], r15d
0x1800195e1  jge     loc_1800196E3
0x1800195e7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800195ee  jnz     short loc_18001960F
0x1800195f0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800195f7  test    rax, rax
0x1800195fa  jz      short loc_180019605
0x1800195fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019601  test    al, al
0x180019603  jmp     short loc_18001960D
0x180019605  call    cs:__imp_IsDebuggerPresent
0x18001960b  test    eax, eax
0x18001960d  jz      short loc_180019616
0x18001960f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180019614  jz      short loc_18001963C
0x180019616  mov     rax, cs:g_pfnResultLoggingCallback
0x18001961d  test    rax, rax
0x180019620  jz      short loc_180019695
0x180019622  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180019629  jnz     short loc_180019695
0x18001962b  xor     r8d, r8d
0x18001962e  lea     rcx, [rsp+14F0h+var_14D0]
0x180019633  xor     edx, edx
0x180019635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001963a  jmp     short loc_180019695
0x18001963c  mov     rax, cs:g_pfnResultLoggingCallback
0x180019643  mov     ebx, 800h
0x180019648  test    rax, rax
0x18001964b  jz      short loc_18001966A
0x18001964d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180019654  jnz     short loc_18001966A
0x180019656  mov     r8d, ebx
0x180019659  lea     rdx, [rbp+13F0h+OutputString]
0x180019660  lea     rcx, [rsp+14F0h+var_14D0]
0x180019665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001966a  cmp     [rbp+13F0h+OutputString], r15w
0x180019672  jnz     short loc_180019688
0x180019674  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180019679  mov     rdx, rbx; unsigned __int16 *
0x18001967c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180019683  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180019688  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001968f  call    cs:__imp_OutputDebugStringW
0x180019695  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001969a  jnz     short loc_1800196A5
0x18001969c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800196a3  jz      short loc_1800196B6
0x1800196a5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800196ac  test    rax, rax
0x1800196af  jz      short loc_1800196B6
0x1800196b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196b6  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800196bb  jnz     short loc_1800196E9
0x1800196bd  mov     rcx, [rbp+13F0h+var_30]
0x1800196c4  xor     rcx, rsp; StackCookie
0x1800196c7  call    __security_check_cookie
0x1800196cc  mov     rbx, [rsp+14F0h+arg_10]
0x1800196d4  add     rsp, 14D0h
0x1800196db  pop     r15
0x1800196dd  pop     r14
0x1800196df  pop     rdi
0x1800196e0  pop     rsi
0x1800196e1  pop     rbp
0x1800196e2  retn
0x1800196e3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800196e9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800196ee  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
