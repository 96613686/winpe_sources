# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400031fc`
- end: `0x14000345c`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002fa0`

## callees

- `0x1400031fc`
- `0x140003fdc`
- `0x1400044a0`
- `0x140004b68`
- `0x140005354`
- `0x14001755a`
- `0x1400175d0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000329d`
- `KERNEL32!GetCurrentThreadId` at `0x14000329d`
- `KERNEL32!OutputDebugStringW` at `0x14000342a`
- `KERNEL32!OutputDebugStringW` at `0x14000342a`
- `KERNEL32!IsDebuggerPresent` at `0x1400033a0`
- `KERNEL32!IsDebuggerPresent` at `0x1400033a0`

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
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
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

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x1400031fc  mov     [rsp-8+arg_18], rbx
0x140003201  push    rbp
0x140003202  push    rsi
0x140003203  push    rdi
0x140003204  push    r12
0x140003206  push    r13
0x140003208  push    r14
0x14000320a  push    r15
0x14000320c  lea     rbp, [rsp-13C0h]
0x140003214  mov     eax, 14C0h
0x140003219  call    _alloca_probe
0x14000321e  sub     rsp, rax
0x140003221  mov     rsi, [rbp+13F0h+arg_28]
0x140003228  mov     r15, r8
0x14000322b  mov     r14d, edx
0x14000322e  mov     r12, rcx
0x140003231  xor     edx, edx; Val
0x140003233  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003238  mov     r8d, 98h; Size
0x14000323e  call    memset_0
0x140003243  mov     rbx, [rbp+13F0h+arg_30]
0x14000324a  xor     r13d, r13d
0x14000324d  mov     [rbp+13F0h+OutputString], r13w
0x140003255  mov     [rbp+13F0h+var_1430], r13b
0x140003259  mov     ecx, [rbx]; this
0x14000325b  mov     eax, [rbx+4]
0x14000325e  mov     [rsp+14F0h+var_14C8], ecx
0x140003262  mov     [rsp+14F0h+var_14C4], eax
0x140003266  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000326b  cmp     dword ptr [rbx+8], 1
0x14000326f  mov     edi, eax
0x140003271  lea     eax, [r13+8]
0x140003275  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14000327d  mov     ecx, r13d
0x140003280  cmovz   ecx, eax
0x140003283  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003287  lea     ecx, [rax-7]
0x14000328a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003292  inc     ecx
0x140003294  mov     [rsp+14F0h+var_14B8], r13
0x140003299  mov     [rsp+14F0h+var_14C0], ecx
0x14000329d  call    cs:__imp_GetCurrentThreadId
0x1400032a3  xorps   xmm0, xmm0
0x1400032a6  mov     [rsp+14F0h+var_1498], r15
0x1400032ab  mov     [rsp+14F0h+var_14B0], eax
0x1400032af  xorps   xmm1, xmm1
0x1400032b2  xor     eax, eax
0x1400032b4  mov     [rsp+14F0h+var_1490], r14d
0x1400032b9  mov     [rbp+13F0h+var_1458], rax
0x1400032bd  mov     [rbp+13F0h+var_1470], rax
0x1400032c1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400032c8  mov     [rsp+14F0h+var_148C], edi
0x1400032cc  mov     [rsp+14F0h+var_14A8], r13
0x1400032d1  mov     [rsp+14F0h+var_14A0], r13
0x1400032d6  mov     [rbp+13F0h+var_1448], rsi
0x1400032da  mov     [rbp+13F0h+var_1440], r12
0x1400032de  mov     [rsp+14F0h+var_1488], r13
0x1400032e3  movups  [rbp+13F0h+var_1468], xmm0
0x1400032e7  movups  [rsp+14F0h+var_1480], xmm1
0x1400032ec  test    rax, rax
0x1400032ef  jz      short loc_1400032FC
0x1400032f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032f6  mov     [rbp+13F0h+var_1450], rax
0x1400032fa  jmp     short loc_140003300
0x1400032fc  mov     [rbp+13F0h+var_1450], r13
0x140003300  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003307  test    rax, rax
0x14000330a  jz      short loc_140003316
0x14000330c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003316  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000331d  test    rax, rax
0x140003320  jz      short loc_140003336
0x140003322  mov     r8d, 400h
0x140003328  lea     rdx, [rbp+13F0h+var_1430]
0x14000332c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003336  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000333d  test    rax, rax
0x140003340  jz      short loc_14000334C
0x140003342  lea     rcx, [rsp+14F0h+var_14D0]
0x140003347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000334c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003353  test    rax, rax
0x140003356  jz      short loc_140003369
0x140003358  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000335d  jnz     short loc_140003369
0x14000335f  lea     rcx, [rsp+14F0h+var_14D0]
0x140003364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003369  cmp     [rsp+14F0h+var_14C8], r13d
0x14000336e  jl      short loc_140003382
0x140003370  mov     ecx, 8000FFFFh; this
0x140003375  mov     [rsp+14F0h+var_14C8], ecx
0x140003379  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000337e  mov     [rsp+14F0h+var_14C4], eax
0x140003382  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140003389  jnz     short loc_1400033AA
0x14000338b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003392  test    rax, rax
0x140003395  jz      short loc_1400033A0
0x140003397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000339c  test    al, al
0x14000339e  jmp     short loc_1400033A8
0x1400033a0  call    cs:__imp_IsDebuggerPresent
0x1400033a6  test    eax, eax
0x1400033a8  jz      short loc_1400033B1
0x1400033aa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400033af  jz      short loc_1400033D7
0x1400033b1  mov     rax, cs:g_pfnResultLoggingCallback
0x1400033b8  test    rax, rax
0x1400033bb  jz      short loc_140003430
0x1400033bd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400033c4  jnz     short loc_140003430
0x1400033c6  xor     r8d, r8d
0x1400033c9  lea     rcx, [rsp+14F0h+var_14D0]
0x1400033ce  xor     edx, edx
0x1400033d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033d5  jmp     short loc_140003430
0x1400033d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400033de  mov     ebx, 800h
0x1400033e3  test    rax, rax
0x1400033e6  jz      short loc_140003405
0x1400033e8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400033ef  jnz     short loc_140003405
0x1400033f1  mov     r8d, ebx
0x1400033f4  lea     rdx, [rbp+13F0h+OutputString]
0x1400033fb  lea     rcx, [rsp+14F0h+var_14D0]
0x140003400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003405  cmp     [rbp+13F0h+OutputString], r13w
0x14000340d  jnz     short loc_140003423
0x14000340f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003414  mov     rdx, rbx; unsigned __int16 *
0x140003417  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000341e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003423  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000342a  call    cs:__imp_OutputDebugStringW
0x140003430  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003435  jnz     short loc_140003440
0x140003437  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000343e  jz      short loc_140003451
0x140003440  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003447  test    rax, rax
0x14000344a  jz      short loc_140003451
0x14000344c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003451  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003456  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
