# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400030e8`
- end: `0x140003360`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `632`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002e94`

## callees

- `0x140001c8f`
- `0x1400030e8`
- `0x140004424`
- `0x140004be0`
- `0x140005320`
- `0x140006c50`
- `0x140007830`
- `0x140008010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400032a3`
- `KERNEL32!IsDebuggerPresent` at `0x1400032a3`
- `KERNEL32!OutputDebugStringW` at `0x14000332d`
- `KERNEL32!OutputDebugStringW` at `0x14000332d`
- `KERNEL32!GetCurrentThreadId` at `0x140003199`
- `KERNEL32!GetCurrentThreadId` at `0x140003199`

## string_xrefs

- `0x1400031a3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7)
{
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
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
  WCHAR OutputString[2064]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v36 = -2;
  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = a2;
  v27 = v10;
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
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
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
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x1400030e8  push    rbp
0x1400030ea  push    rdi
0x1400030eb  push    r12
0x1400030ed  push    r14
0x1400030ef  push    r15
0x1400030f1  lea     rbp, [rsp-13D0h]
0x1400030f9  mov     eax, 14D0h
0x1400030fe  call    _alloca_probe
0x140003103  sub     rsp, rax
0x140003106  mov     [rbp+13F0h+var_1430], 0FFFFFFFFFFFFFFFEh
0x14000310e  mov     [rsp+14F0h+arg_10], rbx
0x140003116  mov     [rsp+14F0h+arg_18], rsi
0x14000311e  mov     r14d, edx
0x140003121  mov     r15, rcx
0x140003124  mov     rsi, [rbp+13F0h+arg_28]
0x14000312b  xor     edx, edx; Val
0x14000312d  mov     r8d, 98h; Size
0x140003133  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003138  call    memset_0
0x14000313d  nop
0x14000313e  xor     r12d, r12d
0x140003141  mov     [rbp+13F0h+OutputString], r12w
0x140003149  mov     [rbp+13F0h+var_1420], r12b
0x14000314d  mov     rbx, [rbp+13F0h+arg_30]
0x140003154  mov     ecx, [rbx]; this
0x140003156  mov     [rsp+14F0h+var_14C8], ecx
0x14000315a  mov     eax, [rbx+4]
0x14000315d  mov     [rsp+14F0h+var_14C4], eax
0x140003161  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003166  mov     edi, eax
0x140003168  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140003170  mov     ecx, r12d
0x140003173  lea     eax, [r12+8]
0x140003178  cmp     dword ptr [rbx+8], 1
0x14000317c  cmovz   ecx, eax
0x14000317f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003183  lea     ecx, [rax-7]
0x140003186  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000318e  inc     ecx
0x140003190  mov     [rsp+14F0h+var_14C0], ecx
0x140003194  mov     [rsp+14F0h+var_14B8], r12
0x140003199  call    cs:__imp_GetCurrentThreadId
0x14000319f  mov     [rsp+14F0h+var_14B0], eax
0x1400031a3  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400031aa  mov     [rsp+14F0h+var_1498], rax
0x1400031af  mov     [rsp+14F0h+var_1490], r14d
0x1400031b4  mov     [rsp+14F0h+var_148C], edi
0x1400031b8  mov     [rsp+14F0h+var_14A8], r12
0x1400031bd  mov     [rsp+14F0h+var_14A0], r12
0x1400031c2  mov     [rbp+13F0h+var_1448], rsi
0x1400031c6  mov     [rbp+13F0h+var_1440], r15
0x1400031ca  mov     [rsp+14F0h+var_1488], r12
0x1400031cf  xorps   xmm0, xmm0
0x1400031d2  xor     eax, eax
0x1400031d4  movups  [rbp+13F0h+var_1468], xmm0
0x1400031d8  mov     [rbp+13F0h+var_1458], rax
0x1400031dc  xorps   xmm1, xmm1
0x1400031df  movups  [rsp+14F0h+var_1480], xmm1
0x1400031e4  mov     [rbp+13F0h+var_1470], rax
0x1400031e8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400031ef  test    rax, rax
0x1400031f2  jz      short loc_1400031FF
0x1400031f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031f9  mov     [rbp+13F0h+var_1450], rax
0x1400031fd  jmp     short loc_140003203
0x1400031ff  mov     [rbp+13F0h+var_1450], r12
0x140003203  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000320a  test    rax, rax
0x14000320d  jz      short loc_140003219
0x14000320f  lea     rcx, [rsp+14F0h+var_14D0]
0x140003214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003219  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003220  test    rax, rax
0x140003223  jz      short loc_140003239
0x140003225  mov     r8d, 400h
0x14000322b  lea     rdx, [rbp+13F0h+var_1420]
0x14000322f  lea     rcx, [rsp+14F0h+var_14D0]
0x140003234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003239  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003240  test    rax, rax
0x140003243  jz      short loc_14000324F
0x140003245  lea     rcx, [rsp+14F0h+var_14D0]
0x14000324a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000324f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003256  test    rax, rax
0x140003259  jz      short loc_14000326C
0x14000325b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003260  jnz     short loc_14000326C
0x140003262  lea     rcx, [rsp+14F0h+var_14D0]
0x140003267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000326c  cmp     [rsp+14F0h+var_14C8], r12d
0x140003271  jl      short loc_140003285
0x140003273  mov     ecx, 8000FFFFh; this
0x140003278  mov     [rsp+14F0h+var_14C8], ecx
0x14000327c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003281  mov     [rsp+14F0h+var_14C4], eax
0x140003285  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000328c  jnz     short loc_1400032AD
0x14000328e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003295  test    rax, rax
0x140003298  jz      short loc_1400032A3
0x14000329a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000329f  test    al, al
0x1400032a1  jmp     short loc_1400032AB
0x1400032a3  call    cs:__imp_IsDebuggerPresent
0x1400032a9  test    eax, eax
0x1400032ab  jz      short loc_1400032B4
0x1400032ad  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400032b2  jz      short loc_1400032DA
0x1400032b4  mov     rax, cs:g_pfnResultLoggingCallback
0x1400032bb  test    rax, rax
0x1400032be  jz      short loc_140003333
0x1400032c0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400032c7  jnz     short loc_140003333
0x1400032c9  xor     r8d, r8d
0x1400032cc  xor     edx, edx
0x1400032ce  lea     rcx, [rsp+14F0h+var_14D0]
0x1400032d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032d8  jmp     short loc_140003333
0x1400032da  mov     ebx, 800h
0x1400032df  mov     rax, cs:g_pfnResultLoggingCallback
0x1400032e6  test    rax, rax
0x1400032e9  jz      short loc_140003308
0x1400032eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400032f2  jnz     short loc_140003308
0x1400032f4  mov     r8d, ebx
0x1400032f7  lea     rdx, [rbp+13F0h+OutputString]
0x1400032fe  lea     rcx, [rsp+14F0h+var_14D0]
0x140003303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003308  cmp     [rbp+13F0h+OutputString], r12w
0x140003310  jnz     short loc_140003326
0x140003312  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003317  mov     rdx, rbx; unsigned __int16 *
0x14000331a  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003321  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003326  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000332d  call    cs:__imp_OutputDebugStringW
0x140003333  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003338  jnz     short loc_140003343
0x14000333a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140003341  jz      short loc_140003355
0x140003343  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000334a  test    rax, rax
0x14000334d  jz      short loc_140003355
0x14000334f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003354  nop
0x140003355  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000335a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
