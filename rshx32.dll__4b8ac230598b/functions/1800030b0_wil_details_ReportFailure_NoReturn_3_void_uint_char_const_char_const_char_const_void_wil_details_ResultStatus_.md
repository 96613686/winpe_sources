# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800030b0`
- end: `0x180003310`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002e54`

## callees

- `0x1800030b0`
- `0x1800041f4`
- `0x18000498c`
- `0x1800050b0`
- `0x1800059f0`
- `0x18001d33a`
- `0x18001d400`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003151`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003151`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800032de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800032de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003254`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003254`

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
0x1800030b0  mov     [rsp-8+arg_18], rbx
0x1800030b5  push    rbp
0x1800030b6  push    rsi
0x1800030b7  push    rdi
0x1800030b8  push    r12
0x1800030ba  push    r13
0x1800030bc  push    r14
0x1800030be  push    r15
0x1800030c0  lea     rbp, [rsp-13C0h]
0x1800030c8  mov     eax, 14C0h
0x1800030cd  call    _alloca_probe
0x1800030d2  sub     rsp, rax
0x1800030d5  mov     rsi, [rbp+13F0h+arg_28]
0x1800030dc  mov     r15, r8
0x1800030df  mov     r14d, edx
0x1800030e2  mov     r12, rcx
0x1800030e5  xor     edx, edx; Val
0x1800030e7  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800030ec  mov     r8d, 98h; Size
0x1800030f2  call    memset_0
0x1800030f7  mov     rbx, [rbp+13F0h+arg_30]
0x1800030fe  xor     r13d, r13d
0x180003101  mov     [rbp+13F0h+OutputString], r13w
0x180003109  mov     [rbp+13F0h+var_1430], r13b
0x18000310d  mov     ecx, [rbx]; this
0x18000310f  mov     eax, [rbx+4]
0x180003112  mov     [rsp+14F0h+var_14C8], ecx
0x180003116  mov     [rsp+14F0h+var_14C4], eax
0x18000311a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000311f  cmp     dword ptr [rbx+8], 1
0x180003123  mov     edi, eax
0x180003125  lea     eax, [r13+8]
0x180003129  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003131  mov     ecx, r13d
0x180003134  cmovz   ecx, eax
0x180003137  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000313b  lea     ecx, [rax-7]
0x18000313e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003146  inc     ecx
0x180003148  mov     [rsp+14F0h+var_14B8], r13
0x18000314d  mov     [rsp+14F0h+var_14C0], ecx
0x180003151  call    cs:__imp_GetCurrentThreadId
0x180003157  xorps   xmm0, xmm0
0x18000315a  mov     [rsp+14F0h+var_1498], r15
0x18000315f  mov     [rsp+14F0h+var_14B0], eax
0x180003163  xorps   xmm1, xmm1
0x180003166  xor     eax, eax
0x180003168  mov     [rsp+14F0h+var_1490], r14d
0x18000316d  mov     [rbp+13F0h+var_1458], rax
0x180003171  mov     [rbp+13F0h+var_1470], rax
0x180003175  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000317c  mov     [rsp+14F0h+var_148C], edi
0x180003180  mov     [rsp+14F0h+var_14A8], r13
0x180003185  mov     [rsp+14F0h+var_14A0], r13
0x18000318a  mov     [rbp+13F0h+var_1448], rsi
0x18000318e  mov     [rbp+13F0h+var_1440], r12
0x180003192  mov     [rsp+14F0h+var_1488], r13
0x180003197  movups  [rbp+13F0h+var_1468], xmm0
0x18000319b  movups  [rsp+14F0h+var_1480], xmm1
0x1800031a0  test    rax, rax
0x1800031a3  jz      short loc_1800031B0
0x1800031a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031aa  mov     [rbp+13F0h+var_1450], rax
0x1800031ae  jmp     short loc_1800031B4
0x1800031b0  mov     [rbp+13F0h+var_1450], r13
0x1800031b4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800031bb  test    rax, rax
0x1800031be  jz      short loc_1800031CA
0x1800031c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800031d1  test    rax, rax
0x1800031d4  jz      short loc_1800031EA
0x1800031d6  mov     r8d, 400h
0x1800031dc  lea     rdx, [rbp+13F0h+var_1430]
0x1800031e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800031f1  test    rax, rax
0x1800031f4  jz      short loc_180003200
0x1800031f6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003200  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003207  test    rax, rax
0x18000320a  jz      short loc_18000321D
0x18000320c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003211  jnz     short loc_18000321D
0x180003213  lea     rcx, [rsp+14F0h+var_14D0]
0x180003218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000321d  cmp     [rsp+14F0h+var_14C8], r13d
0x180003222  jl      short loc_180003236
0x180003224  mov     ecx, 8000FFFFh; this
0x180003229  mov     [rsp+14F0h+var_14C8], ecx
0x18000322d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003232  mov     [rsp+14F0h+var_14C4], eax
0x180003236  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000323d  jnz     short loc_18000325E
0x18000323f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003246  test    rax, rax
0x180003249  jz      short loc_180003254
0x18000324b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003250  test    al, al
0x180003252  jmp     short loc_18000325C
0x180003254  call    cs:__imp_IsDebuggerPresent
0x18000325a  test    eax, eax
0x18000325c  jz      short loc_180003265
0x18000325e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003263  jz      short loc_18000328B
0x180003265  mov     rax, cs:g_pfnResultLoggingCallback
0x18000326c  test    rax, rax
0x18000326f  jz      short loc_1800032E4
0x180003271  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003278  jnz     short loc_1800032E4
0x18000327a  xor     r8d, r8d
0x18000327d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003282  xor     edx, edx
0x180003284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003289  jmp     short loc_1800032E4
0x18000328b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003292  mov     ebx, 800h
0x180003297  test    rax, rax
0x18000329a  jz      short loc_1800032B9
0x18000329c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800032a3  jnz     short loc_1800032B9
0x1800032a5  mov     r8d, ebx
0x1800032a8  lea     rdx, [rbp+13F0h+OutputString]
0x1800032af  lea     rcx, [rsp+14F0h+var_14D0]
0x1800032b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b9  cmp     [rbp+13F0h+OutputString], r13w
0x1800032c1  jnz     short loc_1800032D7
0x1800032c3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800032c8  mov     rdx, rbx; unsigned __int16 *
0x1800032cb  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800032d2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800032d7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800032de  call    cs:__imp_OutputDebugStringW
0x1800032e4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800032e9  jnz     short loc_1800032F4
0x1800032eb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800032f2  jz      short loc_180003305
0x1800032f4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800032fb  test    rax, rax
0x1800032fe  jz      short loc_180003305
0x180003300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003305  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000330a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
