# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140009354`
- end: `0x1400095fa`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140008de4`

## callees

- `0x140005530`
- `0x140006314`
- `0x140009354`
- `0x140011cc8`
- `0x140015098`
- `0x140019420`
- `0x14001b500`
- `0x14009d330`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14000950f`
- `KERNEL32!IsDebuggerPresent` at `0x14000950f`
- `KERNEL32!OutputDebugStringW` at `0x140009599`
- `KERNEL32!OutputDebugStringW` at `0x140009599`
- `KERNEL32!GetCurrentThreadId` at `0x14000941a`
- `KERNEL32!GetCurrentThreadId` at `0x14000941a`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x140009354  push    rbp
0x140009356  push    rbx
0x140009357  push    rsi
0x140009358  push    rdi
0x140009359  push    r12
0x14000935b  push    r14
0x14000935d  push    r15
0x14000935f  lea     rbp, [rsp-13D0h]
0x140009367  mov     eax, 14D0h
0x14000936c  call    _alloca_probe
0x140009371  sub     rsp, rax
0x140009374  mov     rax, cs:__security_cookie
0x14000937b  xor     rax, rsp
0x14000937e  mov     [rbp+1400h+var_40], rax
0x140009385  mov     rsi, r8
0x140009388  mov     edi, edx
0x14000938a  mov     rbx, rcx
0x14000938d  mov     r14, [rbp+1400h+arg_28]
0x140009394  xor     edx, edx; Val
0x140009396  mov     r8d, 98h; Size
0x14000939c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400093a1  call    memset_0
0x1400093a6  nop
0x1400093a7  xor     r12d, r12d
0x1400093aa  mov     [rbp+1400h+OutputString], r12w
0x1400093b2  mov     [rbp+1400h+var_1440], r12b
0x1400093b6  mov     rdx, [rbp+1400h+arg_30]; int
0x1400093bd  mov     ecx, [rdx]; this
0x1400093bf  mov     [rsp+1500h+var_14D8], ecx
0x1400093c3  mov     eax, [rdx+4]
0x1400093c6  mov     [rsp+1500h+var_14D4], eax
0x1400093ca  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400093cf  mov     r15d, eax
0x1400093d2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400093da  mov     ecx, r12d
0x1400093dd  lea     eax, [r12+8]
0x1400093e2  cmp     dword ptr [rdx+8], 1
0x1400093e6  cmovz   ecx, eax
0x1400093e9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400093ed  lea     ecx, [rax-7]
0x1400093f0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400093f8  inc     ecx
0x1400093fa  mov     [rsp+1500h+var_14D0], ecx
0x1400093fe  mov     rcx, [rbp+1400h+arg_38]
0x140009405  test    rcx, rcx
0x140009408  jz      short loc_140009415
0x14000940a  cmp     [rcx], r12w
0x14000940e  mov     [rsp+1500h+var_14C8], rcx
0x140009413  jnz     short loc_14000941A
0x140009415  mov     [rsp+1500h+var_14C8], r12
0x14000941a  call    cs:__imp_GetCurrentThreadId
0x140009420  mov     [rsp+1500h+var_14C0], eax
0x140009424  mov     [rsp+1500h+var_14A8], rsi
0x140009429  mov     [rsp+1500h+var_14A0], edi
0x14000942d  mov     [rsp+1500h+var_149C], r15d
0x140009432  mov     [rsp+1500h+var_14B8], r12
0x140009437  mov     [rsp+1500h+var_14B0], r12
0x14000943c  mov     [rbp+1400h+var_1458], r14
0x140009440  mov     [rbp+1400h+var_1450], rbx
0x140009444  mov     [rsp+1500h+var_1498], r12
0x140009449  xorps   xmm0, xmm0
0x14000944c  xor     eax, eax
0x14000944e  movups  [rbp+1400h+var_1478], xmm0
0x140009452  mov     [rbp+1400h+var_1468], rax
0x140009456  xorps   xmm1, xmm1
0x140009459  movups  [rsp+1500h+var_1490], xmm1
0x14000945e  mov     [rbp+1400h+var_1480], rax
0x140009462  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140009469  test    rax, rax
0x14000946c  jz      short loc_140009479
0x14000946e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009473  mov     [rbp+1400h+var_1460], rax
0x140009477  jmp     short loc_14000947D
0x140009479  mov     [rbp+1400h+var_1460], r12
0x14000947d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140009484  test    rax, rax
0x140009487  jz      short loc_140009493
0x140009489  lea     rcx, [rsp+1500h+var_14E0]
0x14000948e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009493  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000949a  test    rax, rax
0x14000949d  jz      short loc_1400094B3
0x14000949f  mov     r8d, 400h
0x1400094a5  lea     rdx, [rbp+1400h+var_1440]
0x1400094a9  lea     rcx, [rsp+1500h+var_14E0]
0x1400094ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094b3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400094ba  test    rax, rax
0x1400094bd  jz      short loc_1400094C9
0x1400094bf  lea     rcx, [rsp+1500h+var_14E0]
0x1400094c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094c9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400094d0  test    rax, rax
0x1400094d3  jz      short loc_1400094E6
0x1400094d5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400094da  jnz     short loc_1400094E6
0x1400094dc  lea     rcx, [rsp+1500h+var_14E0]
0x1400094e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094e6  cmp     [rsp+1500h+var_14D8], r12d
0x1400094eb  jge     loc_1400095F4
0x1400094f1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400094f8  jnz     short loc_140009519
0x1400094fa  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140009501  test    rax, rax
0x140009504  jz      short loc_14000950F
0x140009506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000950b  test    al, al
0x14000950d  jmp     short loc_140009517
0x14000950f  call    cs:__imp_IsDebuggerPresent
0x140009515  test    eax, eax
0x140009517  jz      short loc_140009520
0x140009519  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000951e  jz      short loc_140009546
0x140009520  mov     rax, cs:g_pfnResultLoggingCallback
0x140009527  test    rax, rax
0x14000952a  jz      short loc_14000959F
0x14000952c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140009533  jnz     short loc_14000959F
0x140009535  xor     r8d, r8d
0x140009538  xor     edx, edx
0x14000953a  lea     rcx, [rsp+1500h+var_14E0]
0x14000953f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009544  jmp     short loc_14000959F
0x140009546  mov     ebx, 800h
0x14000954b  mov     rax, cs:g_pfnResultLoggingCallback
0x140009552  test    rax, rax
0x140009555  jz      short loc_140009574
0x140009557  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000955e  jnz     short loc_140009574
0x140009560  mov     r8d, ebx
0x140009563  lea     rdx, [rbp+1400h+OutputString]
0x14000956a  lea     rcx, [rsp+1500h+var_14E0]
0x14000956f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009574  cmp     [rbp+1400h+OutputString], r12w
0x14000957c  jnz     short loc_140009592
0x14000957e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140009583  mov     rdx, rbx; unsigned __int16 *
0x140009586  lea     rcx, [rbp+1400h+OutputString]; this
0x14000958d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140009592  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140009599  call    cs:__imp_OutputDebugStringW
0x14000959f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400095a4  jnz     short loc_1400095AF
0x1400095a6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400095ad  jz      short loc_1400095C1
0x1400095af  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400095b6  test    rax, rax
0x1400095b9  jz      short loc_1400095C1
0x1400095bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095c0  nop
0x1400095c1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400095c6  jnz     short loc_1400095E9
0x1400095c8  mov     rcx, [rbp+1400h+var_40]
0x1400095cf  xor     rcx, rsp; StackCookie
0x1400095d2  call    __security_check_cookie
0x1400095d7  add     rsp, 14D0h
0x1400095de  pop     r15
0x1400095e0  pop     r14
0x1400095e2  pop     r12
0x1400095e4  pop     rdi
0x1400095e5  pop     rsi
0x1400095e6  pop     rbx
0x1400095e7  pop     rbp
0x1400095e8  retn
0x1400095e9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400095ee  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400095f4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
