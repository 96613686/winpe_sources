# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800022e8`
- end: `0x180002561`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002094`

## callees

- `0x1800022e8`
- `0x180005798`
- `0x180007fbc`
- `0x18000b1b0`
- `0x18000d6bc`
- `0x180012d6e`
- `0x180012e40`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002389`
- `KERNEL32!GetCurrentThreadId` at `0x180002389`
- `KERNEL32!IsDebuggerPresent` at `0x180002499`
- `KERNEL32!IsDebuggerPresent` at `0x180002499`
- `KERNEL32!OutputDebugStringW` at `0x180002529`
- `KERNEL32!OutputDebugStringW` at `0x180002529`

## string_xrefs

- `0x1800023a4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
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
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
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
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
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
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x1800022e8  mov     [rsp-8+arg_10], rbx
0x1800022ed  mov     [rsp-8+arg_18], rsi
0x1800022f2  push    rbp
0x1800022f3  push    rdi
0x1800022f4  push    r12
0x1800022f6  push    r14
0x1800022f8  push    r15
0x1800022fa  lea     rbp, [rsp-13C0h]
0x180002302  mov     eax, 14C0h
0x180002307  call    _alloca_probe
0x18000230c  sub     rsp, rax
0x18000230f  mov     rsi, [rbp+13E0h+arg_28]
0x180002316  mov     r14d, edx
0x180002319  mov     r15, rcx
0x18000231c  xor     edx, edx; Val
0x18000231e  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002323  mov     r8d, 98h; Size
0x180002329  call    memset_0
0x18000232e  mov     rbx, [rbp+13E0h+arg_30]
0x180002335  xor     r12d, r12d
0x180002338  mov     [rbp+13E0h+OutputString], r12w
0x180002340  mov     [rbp+13E0h+var_1420], r12b
0x180002344  mov     ecx, [rbx]; this
0x180002346  mov     eax, [rbx+4]
0x180002349  mov     [rsp+14E0h+var_14B8], ecx
0x18000234d  mov     [rsp+14E0h+var_14B4], eax
0x180002351  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002356  cmp     dword ptr [rbx+8], 1
0x18000235a  mov     edi, eax
0x18000235c  lea     eax, [r12+8]
0x180002361  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002369  mov     ecx, r12d
0x18000236c  cmovz   ecx, eax
0x18000236f  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002373  lea     ecx, [rax-7]
0x180002376  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000237e  inc     ecx
0x180002380  mov     [rsp+14E0h+var_14A8], r12
0x180002385  mov     [rsp+14E0h+var_14B0], ecx
0x180002389  call    cs:__imp_GetCurrentThreadId
0x180002390  nop     dword ptr [rax+rax+00h]
0x180002395  xorps   xmm0, xmm0
0x180002398  mov     [rsp+14E0h+var_1480], r14d
0x18000239d  mov     [rsp+14E0h+var_14A0], eax
0x1800023a1  xorps   xmm1, xmm1
0x1800023a4  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800023ab  mov     [rsp+14E0h+var_147C], edi
0x1800023af  mov     [rsp+14E0h+var_1488], rax
0x1800023b4  xor     eax, eax
0x1800023b6  mov     [rbp+13E0h+var_1448], rax
0x1800023ba  mov     [rbp+13E0h+var_1460], rax
0x1800023be  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800023c5  mov     [rsp+14E0h+var_1498], r12
0x1800023ca  mov     [rsp+14E0h+var_1490], r12
0x1800023cf  mov     [rbp+13E0h+var_1438], rsi
0x1800023d3  mov     [rbp+13E0h+var_1430], r15
0x1800023d7  mov     [rsp+14E0h+var_1478], r12
0x1800023dc  movups  [rbp+13E0h+var_1458], xmm0
0x1800023e0  movups  [rsp+14E0h+var_1470], xmm1
0x1800023e5  test    rax, rax
0x1800023e8  jz      short loc_1800023F5
0x1800023ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ef  mov     [rbp+13E0h+var_1440], rax
0x1800023f3  jmp     short loc_1800023F9
0x1800023f5  mov     [rbp+13E0h+var_1440], r12
0x1800023f9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002400  test    rax, rax
0x180002403  jz      short loc_18000240F
0x180002405  lea     rcx, [rsp+14E0h+var_14C0]
0x18000240a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002416  test    rax, rax
0x180002419  jz      short loc_18000242F
0x18000241b  mov     r8d, 400h
0x180002421  lea     rdx, [rbp+13E0h+var_1420]
0x180002425  lea     rcx, [rsp+14E0h+var_14C0]
0x18000242a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000242f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002436  test    rax, rax
0x180002439  jz      short loc_180002445
0x18000243b  lea     rcx, [rsp+14E0h+var_14C0]
0x180002440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002445  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000244c  test    rax, rax
0x18000244f  jz      short loc_180002462
0x180002451  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002456  jnz     short loc_180002462
0x180002458  lea     rcx, [rsp+14E0h+var_14C0]
0x18000245d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002462  cmp     [rsp+14E0h+var_14B8], r12d
0x180002467  jl      short loc_18000247B
0x180002469  mov     ecx, 8000FFFFh; this
0x18000246e  mov     [rsp+14E0h+var_14B8], ecx
0x180002472  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002477  mov     [rsp+14E0h+var_14B4], eax
0x18000247b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002482  jnz     short loc_1800024A9
0x180002484  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000248b  test    rax, rax
0x18000248e  jz      short loc_180002499
0x180002490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002495  test    al, al
0x180002497  jmp     short loc_1800024A7
0x180002499  call    cs:__imp_IsDebuggerPresent
0x1800024a0  nop     dword ptr [rax+rax+00h]
0x1800024a5  test    eax, eax
0x1800024a7  jz      short loc_1800024B0
0x1800024a9  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800024ae  jz      short loc_1800024D6
0x1800024b0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800024b7  test    rax, rax
0x1800024ba  jz      short loc_180002535
0x1800024bc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800024c3  jnz     short loc_180002535
0x1800024c5  xor     r8d, r8d
0x1800024c8  lea     rcx, [rsp+14E0h+var_14C0]
0x1800024cd  xor     edx, edx
0x1800024cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024d4  jmp     short loc_180002535
0x1800024d6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800024dd  mov     ebx, 800h
0x1800024e2  test    rax, rax
0x1800024e5  jz      short loc_180002504
0x1800024e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800024ee  jnz     short loc_180002504
0x1800024f0  mov     r8d, ebx
0x1800024f3  lea     rdx, [rbp+13E0h+OutputString]
0x1800024fa  lea     rcx, [rsp+14E0h+var_14C0]
0x1800024ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002504  cmp     [rbp+13E0h+OutputString], r12w
0x18000250c  jnz     short loc_180002522
0x18000250e  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002513  mov     rdx, rbx; unsigned __int16 *
0x180002516  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000251d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002522  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002529  call    cs:__imp_OutputDebugStringW
0x180002530  nop     dword ptr [rax+rax+00h]
0x180002535  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x18000253a  jnz     short loc_180002545
0x18000253c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002543  jz      short loc_180002556
0x180002545  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000254c  test    rax, rax
0x18000254f  jz      short loc_180002556
0x180002551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002556  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000255b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
