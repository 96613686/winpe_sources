# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400028dc`
- end: `0x140002b45`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002688`

## callees

- `0x1400028dc`
- `0x140004324`
- `0x1400054a4`
- `0x140006630`
- `0x140007b80`
- `0x14002e3e2`
- `0x14002e4e0`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000297e`
- `KERNEL32!GetCurrentThreadId` at `0x14000297e`
- `KERNEL32!OutputDebugStringW` at `0x140002b12`
- `KERNEL32!OutputDebugStringW` at `0x140002b12`
- `KERNEL32!IsDebuggerPresent` at `0x140002a88`
- `KERNEL32!IsDebuggerPresent` at `0x140002a88`

## string_xrefs

- `0x140002988`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
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
0x1400028dc  mov     [rsp-8+arg_10], rbx
0x1400028e1  mov     [rsp-8+arg_18], rsi
0x1400028e6  push    rbp
0x1400028e7  push    rdi
0x1400028e8  push    r12
0x1400028ea  push    r14
0x1400028ec  push    r15
0x1400028ee  lea     rbp, [rsp-13C0h]
0x1400028f6  mov     eax, 14C0h
0x1400028fb  call    _alloca_probe
0x140002900  sub     rsp, rax
0x140002903  mov     r14d, edx
0x140002906  mov     r15, rcx
0x140002909  mov     rsi, [rbp+13E0h+arg_28]
0x140002910  xor     edx, edx; Val
0x140002912  mov     r8d, 98h; Size
0x140002918  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x14000291d  call    memset_0
0x140002922  nop
0x140002923  xor     r12d, r12d
0x140002926  mov     [rbp+13E0h+OutputString], r12w
0x14000292e  mov     [rbp+13E0h+var_1420], r12b
0x140002932  mov     rbx, [rbp+13E0h+arg_30]
0x140002939  mov     ecx, [rbx]; this
0x14000293b  mov     [rsp+14E0h+var_14B8], ecx
0x14000293f  mov     eax, [rbx+4]
0x140002942  mov     [rsp+14E0h+var_14B4], eax
0x140002946  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000294b  mov     edi, eax
0x14000294d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x140002955  mov     ecx, r12d
0x140002958  lea     eax, [r12+8]
0x14000295d  cmp     dword ptr [rbx+8], 1
0x140002961  cmovz   ecx, eax
0x140002964  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x140002968  lea     ecx, [rax-7]
0x14000296b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002973  inc     ecx
0x140002975  mov     [rsp+14E0h+var_14B0], ecx
0x140002979  mov     [rsp+14E0h+var_14A8], r12
0x14000297e  call    cs:__imp_GetCurrentThreadId
0x140002984  mov     [rsp+14E0h+var_14A0], eax
0x140002988  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000298f  mov     [rsp+14E0h+var_1488], rax
0x140002994  mov     [rsp+14E0h+var_1480], r14d
0x140002999  mov     [rsp+14E0h+var_147C], edi
0x14000299d  mov     [rsp+14E0h+var_1498], r12
0x1400029a2  mov     [rsp+14E0h+var_1490], r12
0x1400029a7  mov     [rbp+13E0h+var_1438], rsi
0x1400029ab  mov     [rbp+13E0h+var_1430], r15
0x1400029af  mov     [rsp+14E0h+var_1478], r12
0x1400029b4  xorps   xmm0, xmm0
0x1400029b7  xor     eax, eax
0x1400029b9  movups  [rbp+13E0h+var_1458], xmm0
0x1400029bd  mov     [rbp+13E0h+var_1448], rax
0x1400029c1  xorps   xmm1, xmm1
0x1400029c4  movups  [rsp+14E0h+var_1470], xmm1
0x1400029c9  mov     [rbp+13E0h+var_1460], rax
0x1400029cd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400029d4  test    rax, rax
0x1400029d7  jz      short loc_1400029E4
0x1400029d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029de  mov     [rbp+13E0h+var_1440], rax
0x1400029e2  jmp     short loc_1400029E8
0x1400029e4  mov     [rbp+13E0h+var_1440], r12
0x1400029e8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400029ef  test    rax, rax
0x1400029f2  jz      short loc_1400029FE
0x1400029f4  lea     rcx, [rsp+14E0h+var_14C0]
0x1400029f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029fe  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002a05  test    rax, rax
0x140002a08  jz      short loc_140002A1E
0x140002a0a  mov     r8d, 400h
0x140002a10  lea     rdx, [rbp+13E0h+var_1420]
0x140002a14  lea     rcx, [rsp+14E0h+var_14C0]
0x140002a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a1e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002a25  test    rax, rax
0x140002a28  jz      short loc_140002A34
0x140002a2a  lea     rcx, [rsp+14E0h+var_14C0]
0x140002a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a34  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002a3b  test    rax, rax
0x140002a3e  jz      short loc_140002A51
0x140002a40  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140002a45  jnz     short loc_140002A51
0x140002a47  lea     rcx, [rsp+14E0h+var_14C0]
0x140002a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a51  cmp     [rsp+14E0h+var_14B8], r12d
0x140002a56  jl      short loc_140002A6A
0x140002a58  mov     ecx, 8000FFFFh; this
0x140002a5d  mov     [rsp+14E0h+var_14B8], ecx
0x140002a61  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002a66  mov     [rsp+14E0h+var_14B4], eax
0x140002a6a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002a71  jnz     short loc_140002A92
0x140002a73  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002a7a  test    rax, rax
0x140002a7d  jz      short loc_140002A88
0x140002a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a84  test    al, al
0x140002a86  jmp     short loc_140002A90
0x140002a88  call    cs:__imp_IsDebuggerPresent
0x140002a8e  test    eax, eax
0x140002a90  jz      short loc_140002A99
0x140002a92  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140002a97  jz      short loc_140002ABF
0x140002a99  mov     rax, cs:g_pfnResultLoggingCallback
0x140002aa0  test    rax, rax
0x140002aa3  jz      short loc_140002B18
0x140002aa5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002aac  jnz     short loc_140002B18
0x140002aae  xor     r8d, r8d
0x140002ab1  xor     edx, edx
0x140002ab3  lea     rcx, [rsp+14E0h+var_14C0]
0x140002ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002abd  jmp     short loc_140002B18
0x140002abf  mov     ebx, 800h
0x140002ac4  mov     rax, cs:g_pfnResultLoggingCallback
0x140002acb  test    rax, rax
0x140002ace  jz      short loc_140002AED
0x140002ad0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002ad7  jnz     short loc_140002AED
0x140002ad9  mov     r8d, ebx
0x140002adc  lea     rdx, [rbp+13E0h+OutputString]
0x140002ae3  lea     rcx, [rsp+14E0h+var_14C0]
0x140002ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002aed  cmp     [rbp+13E0h+OutputString], r12w
0x140002af5  jnz     short loc_140002B0B
0x140002af7  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140002afc  mov     rdx, rbx; unsigned __int16 *
0x140002aff  lea     rcx, [rbp+13E0h+OutputString]; this
0x140002b06  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002b0b  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x140002b12  call    cs:__imp_OutputDebugStringW
0x140002b18  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x140002b1d  jnz     short loc_140002B28
0x140002b1f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002b26  jz      short loc_140002B3A
0x140002b28  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002b2f  test    rax, rax
0x140002b32  jz      short loc_140002B3A
0x140002b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b39  nop
0x140002b3a  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140002b3f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
