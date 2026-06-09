# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180009408`
- end: `0x18000967a`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009194`

## callees

- `0x180009408`
- `0x18000b8f0`
- `0x18000c2c4`
- `0x18000d500`
- `0x18001084c`
- `0x180011a62`
- `0x180011b50`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800094a9`
- `KERNEL32!GetCurrentThreadId` at `0x1800094a9`
- `KERNEL32!IsDebuggerPresent` at `0x1800095b2`
- `KERNEL32!IsDebuggerPresent` at `0x1800095b2`
- `KERNEL32!OutputDebugStringW` at `0x180009642`
- `KERNEL32!OutputDebugStringW` at `0x180009642`

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
0x180009408  mov     [rsp-8+arg_18], rbx
0x18000940d  push    rbp
0x18000940e  push    rsi
0x18000940f  push    rdi
0x180009410  push    r12
0x180009412  push    r13
0x180009414  push    r14
0x180009416  push    r15
0x180009418  lea     rbp, [rsp-13C0h]
0x180009420  mov     eax, 14C0h
0x180009425  call    _alloca_probe
0x18000942a  sub     rsp, rax
0x18000942d  mov     rsi, [rbp+13F0h+arg_28]
0x180009434  mov     r15, r8
0x180009437  mov     r14d, edx
0x18000943a  mov     r12, rcx
0x18000943d  xor     edx, edx; Val
0x18000943f  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009444  mov     r8d, 98h; Size
0x18000944a  call    memset_0
0x18000944f  mov     rbx, [rbp+13F0h+arg_30]
0x180009456  xor     r13d, r13d
0x180009459  mov     [rbp+13F0h+OutputString], r13w
0x180009461  mov     [rbp+13F0h+var_1430], r13b
0x180009465  mov     ecx, [rbx]; this
0x180009467  mov     eax, [rbx+4]
0x18000946a  mov     [rsp+14F0h+var_14C8], ecx
0x18000946e  mov     [rsp+14F0h+var_14C4], eax
0x180009472  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009477  cmp     dword ptr [rbx+8], 1
0x18000947b  mov     edi, eax
0x18000947d  lea     eax, [r13+8]
0x180009481  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180009489  mov     ecx, r13d
0x18000948c  cmovz   ecx, eax
0x18000948f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180009493  lea     ecx, [rax-7]
0x180009496  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000949e  inc     ecx
0x1800094a0  mov     [rsp+14F0h+var_14B8], r13
0x1800094a5  mov     [rsp+14F0h+var_14C0], ecx
0x1800094a9  call    cs:__imp_GetCurrentThreadId
0x1800094b0  nop     dword ptr [rax+rax+00h]
0x1800094b5  xorps   xmm0, xmm0
0x1800094b8  mov     [rsp+14F0h+var_1498], r15
0x1800094bd  mov     [rsp+14F0h+var_14B0], eax
0x1800094c1  xorps   xmm1, xmm1
0x1800094c4  xor     eax, eax
0x1800094c6  mov     [rsp+14F0h+var_1490], r14d
0x1800094cb  mov     [rbp+13F0h+var_1458], rax
0x1800094cf  mov     [rbp+13F0h+var_1470], rax
0x1800094d3  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800094da  mov     [rsp+14F0h+var_148C], edi
0x1800094de  mov     [rsp+14F0h+var_14A8], r13
0x1800094e3  mov     [rsp+14F0h+var_14A0], r13
0x1800094e8  mov     [rbp+13F0h+var_1448], rsi
0x1800094ec  mov     [rbp+13F0h+var_1440], r12
0x1800094f0  mov     [rsp+14F0h+var_1488], r13
0x1800094f5  movups  [rbp+13F0h+var_1468], xmm0
0x1800094f9  movups  [rsp+14F0h+var_1480], xmm1
0x1800094fe  test    rax, rax
0x180009501  jz      short loc_18000950E
0x180009503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009508  mov     [rbp+13F0h+var_1450], rax
0x18000950c  jmp     short loc_180009512
0x18000950e  mov     [rbp+13F0h+var_1450], r13
0x180009512  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009519  test    rax, rax
0x18000951c  jz      short loc_180009528
0x18000951e  lea     rcx, [rsp+14F0h+var_14D0]
0x180009523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009528  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000952f  test    rax, rax
0x180009532  jz      short loc_180009548
0x180009534  mov     r8d, 400h
0x18000953a  lea     rdx, [rbp+13F0h+var_1430]
0x18000953e  lea     rcx, [rsp+14F0h+var_14D0]
0x180009543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009548  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000954f  test    rax, rax
0x180009552  jz      short loc_18000955E
0x180009554  lea     rcx, [rsp+14F0h+var_14D0]
0x180009559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000955e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009565  test    rax, rax
0x180009568  jz      short loc_18000957B
0x18000956a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000956f  jnz     short loc_18000957B
0x180009571  lea     rcx, [rsp+14F0h+var_14D0]
0x180009576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000957b  cmp     [rsp+14F0h+var_14C8], r13d
0x180009580  jl      short loc_180009594
0x180009582  mov     ecx, 8000FFFFh; this
0x180009587  mov     [rsp+14F0h+var_14C8], ecx
0x18000958b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009590  mov     [rsp+14F0h+var_14C4], eax
0x180009594  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000959b  jnz     short loc_1800095C2
0x18000959d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800095a4  test    rax, rax
0x1800095a7  jz      short loc_1800095B2
0x1800095a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ae  test    al, al
0x1800095b0  jmp     short loc_1800095C0
0x1800095b2  call    cs:__imp_IsDebuggerPresent
0x1800095b9  nop     dword ptr [rax+rax+00h]
0x1800095be  test    eax, eax
0x1800095c0  jz      short loc_1800095C9
0x1800095c2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800095c7  jz      short loc_1800095EF
0x1800095c9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800095d0  test    rax, rax
0x1800095d3  jz      short loc_18000964E
0x1800095d5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800095dc  jnz     short loc_18000964E
0x1800095de  xor     r8d, r8d
0x1800095e1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800095e6  xor     edx, edx
0x1800095e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ed  jmp     short loc_18000964E
0x1800095ef  mov     rax, cs:g_pfnResultLoggingCallback
0x1800095f6  mov     ebx, 800h
0x1800095fb  test    rax, rax
0x1800095fe  jz      short loc_18000961D
0x180009600  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009607  jnz     short loc_18000961D
0x180009609  mov     r8d, ebx
0x18000960c  lea     rdx, [rbp+13F0h+OutputString]
0x180009613  lea     rcx, [rsp+14F0h+var_14D0]
0x180009618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000961d  cmp     [rbp+13F0h+OutputString], r13w
0x180009625  jnz     short loc_18000963B
0x180009627  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000962c  mov     rdx, rbx; unsigned __int16 *
0x18000962f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180009636  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000963b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180009642  call    cs:__imp_OutputDebugStringW
0x180009649  nop     dword ptr [rax+rax+00h]
0x18000964e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180009653  jnz     short loc_18000965E
0x180009655  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000965c  jz      short loc_18000966F
0x18000965e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009665  test    rax, rax
0x180009668  jz      short loc_18000966F
0x18000966a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000966f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009674  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
