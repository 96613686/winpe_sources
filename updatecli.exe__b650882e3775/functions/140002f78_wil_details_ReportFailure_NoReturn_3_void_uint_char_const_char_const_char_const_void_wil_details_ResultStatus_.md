# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140002f78`
- end: `0x1400031e1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002d24`

## callees

- `0x140002c38`
- `0x140002f78`
- `0x140004354`
- `0x140004afc`
- `0x140005220`
- `0x1400061a0`
- `0x14000ac20`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000301a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000301a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400031ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400031ae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003124`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003124`

## string_xrefs

- `0x140003024`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140002f78  mov     [rsp-8+arg_10], rbx
0x140002f7d  mov     [rsp-8+arg_18], rsi
0x140002f82  push    rbp
0x140002f83  push    rdi
0x140002f84  push    r12
0x140002f86  push    r14
0x140002f88  push    r15
0x140002f8a  lea     rbp, [rsp-13C0h]
0x140002f92  mov     eax, 14C0h
0x140002f97  call    _alloca_probe
0x140002f9c  sub     rsp, rax
0x140002f9f  mov     r14d, edx
0x140002fa2  mov     r15, rcx
0x140002fa5  mov     rsi, [rbp+13E0h+arg_28]
0x140002fac  xor     edx, edx; Val
0x140002fae  mov     r8d, 98h; Size
0x140002fb4  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x140002fb9  call    memset_0
0x140002fbe  nop
0x140002fbf  xor     r12d, r12d
0x140002fc2  mov     [rbp+13E0h+OutputString], r12w
0x140002fca  mov     [rbp+13E0h+var_1420], r12b
0x140002fce  mov     rbx, [rbp+13E0h+arg_30]
0x140002fd5  mov     ecx, [rbx]; this
0x140002fd7  mov     [rsp+14E0h+var_14B8], ecx
0x140002fdb  mov     eax, [rbx+4]
0x140002fde  mov     [rsp+14E0h+var_14B4], eax
0x140002fe2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140002fe7  mov     edi, eax
0x140002fe9  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x140002ff1  mov     ecx, r12d
0x140002ff4  lea     eax, [r12+8]
0x140002ff9  cmp     dword ptr [rbx+8], 1
0x140002ffd  cmovz   ecx, eax
0x140003000  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x140003004  lea     ecx, [rax-7]
0x140003007  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000300f  inc     ecx
0x140003011  mov     [rsp+14E0h+var_14B0], ecx
0x140003015  mov     [rsp+14E0h+var_14A8], r12
0x14000301a  call    cs:__imp_GetCurrentThreadId
0x140003020  mov     [rsp+14E0h+var_14A0], eax
0x140003024  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000302b  mov     [rsp+14E0h+var_1488], rax
0x140003030  mov     [rsp+14E0h+var_1480], r14d
0x140003035  mov     [rsp+14E0h+var_147C], edi
0x140003039  mov     [rsp+14E0h+var_1498], r12
0x14000303e  mov     [rsp+14E0h+var_1490], r12
0x140003043  mov     [rbp+13E0h+var_1438], rsi
0x140003047  mov     [rbp+13E0h+var_1430], r15
0x14000304b  mov     [rsp+14E0h+var_1478], r12
0x140003050  xorps   xmm0, xmm0
0x140003053  xor     eax, eax
0x140003055  movups  [rbp+13E0h+var_1458], xmm0
0x140003059  mov     [rbp+13E0h+var_1448], rax
0x14000305d  xorps   xmm1, xmm1
0x140003060  movups  [rsp+14E0h+var_1470], xmm1
0x140003065  mov     [rbp+13E0h+var_1460], rax
0x140003069  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003070  test    rax, rax
0x140003073  jz      short loc_140003080
0x140003075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000307a  mov     [rbp+13E0h+var_1440], rax
0x14000307e  jmp     short loc_140003084
0x140003080  mov     [rbp+13E0h+var_1440], r12
0x140003084  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000308b  test    rax, rax
0x14000308e  jz      short loc_14000309A
0x140003090  lea     rcx, [rsp+14E0h+var_14C0]
0x140003095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000309a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400030a1  test    rax, rax
0x1400030a4  jz      short loc_1400030BA
0x1400030a6  mov     r8d, 400h
0x1400030ac  lea     rdx, [rbp+13E0h+var_1420]
0x1400030b0  lea     rcx, [rsp+14E0h+var_14C0]
0x1400030b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030ba  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400030c1  test    rax, rax
0x1400030c4  jz      short loc_1400030D0
0x1400030c6  lea     rcx, [rsp+14E0h+var_14C0]
0x1400030cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030d0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400030d7  test    rax, rax
0x1400030da  jz      short loc_1400030ED
0x1400030dc  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1400030e1  jnz     short loc_1400030ED
0x1400030e3  lea     rcx, [rsp+14E0h+var_14C0]
0x1400030e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030ed  cmp     [rsp+14E0h+var_14B8], r12d
0x1400030f2  jl      short loc_140003106
0x1400030f4  mov     ecx, 8000FFFFh; this
0x1400030f9  mov     [rsp+14E0h+var_14B8], ecx
0x1400030fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003102  mov     [rsp+14E0h+var_14B4], eax
0x140003106  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000310d  jnz     short loc_14000312E
0x14000310f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003116  test    rax, rax
0x140003119  jz      short loc_140003124
0x14000311b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003120  test    al, al
0x140003122  jmp     short loc_14000312C
0x140003124  call    cs:__imp_IsDebuggerPresent
0x14000312a  test    eax, eax
0x14000312c  jz      short loc_140003135
0x14000312e  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140003133  jz      short loc_14000315B
0x140003135  mov     rax, cs:g_pfnResultLoggingCallback
0x14000313c  test    rax, rax
0x14000313f  jz      short loc_1400031B4
0x140003141  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003148  jnz     short loc_1400031B4
0x14000314a  xor     r8d, r8d
0x14000314d  xor     edx, edx
0x14000314f  lea     rcx, [rsp+14E0h+var_14C0]
0x140003154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003159  jmp     short loc_1400031B4
0x14000315b  mov     ebx, 800h
0x140003160  mov     rax, cs:g_pfnResultLoggingCallback
0x140003167  test    rax, rax
0x14000316a  jz      short loc_140003189
0x14000316c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003173  jnz     short loc_140003189
0x140003175  mov     r8d, ebx
0x140003178  lea     rdx, [rbp+13E0h+OutputString]
0x14000317f  lea     rcx, [rsp+14E0h+var_14C0]
0x140003184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003189  cmp     [rbp+13E0h+OutputString], r12w
0x140003191  jnz     short loc_1400031A7
0x140003193  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140003198  mov     rdx, rbx; unsigned __int16 *
0x14000319b  lea     rcx, [rbp+13E0h+OutputString]; this
0x1400031a2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400031a7  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1400031ae  call    cs:__imp_OutputDebugStringW
0x1400031b4  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1400031b9  jnz     short loc_1400031C4
0x1400031bb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400031c2  jz      short loc_1400031D6
0x1400031c4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400031cb  test    rax, rax
0x1400031ce  jz      short loc_1400031D6
0x1400031d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031d5  nop
0x1400031d6  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1400031db  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
