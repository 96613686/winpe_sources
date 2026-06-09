# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400031dc`
- end: `0x14000343c`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002f80`

## callees

- `0x140002254`
- `0x1400031dc`
- `0x140004944`
- `0x140005144`
- `0x140005a70`
- `0x1400069a0`
- `0x14000b180`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000327d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000327d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003380`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003380`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000340a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000340a`

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
0x1400031dc  mov     [rsp-8+arg_18], rbx
0x1400031e1  push    rbp
0x1400031e2  push    rsi
0x1400031e3  push    rdi
0x1400031e4  push    r12
0x1400031e6  push    r13
0x1400031e8  push    r14
0x1400031ea  push    r15
0x1400031ec  lea     rbp, [rsp-13C0h]
0x1400031f4  mov     eax, 14C0h
0x1400031f9  call    _alloca_probe
0x1400031fe  sub     rsp, rax
0x140003201  mov     rsi, [rbp+13F0h+arg_28]
0x140003208  mov     r15, r8
0x14000320b  mov     r14d, edx
0x14000320e  mov     r12, rcx
0x140003211  xor     edx, edx; Val
0x140003213  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003218  mov     r8d, 98h; Size
0x14000321e  call    memset_0
0x140003223  mov     rbx, [rbp+13F0h+arg_30]
0x14000322a  xor     r13d, r13d
0x14000322d  mov     [rbp+13F0h+OutputString], r13w
0x140003235  mov     [rbp+13F0h+var_1430], r13b
0x140003239  mov     ecx, [rbx]; this
0x14000323b  mov     eax, [rbx+4]
0x14000323e  mov     [rsp+14F0h+var_14C8], ecx
0x140003242  mov     [rsp+14F0h+var_14C4], eax
0x140003246  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000324b  cmp     dword ptr [rbx+8], 1
0x14000324f  mov     edi, eax
0x140003251  lea     eax, [r13+8]
0x140003255  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14000325d  mov     ecx, r13d
0x140003260  cmovz   ecx, eax
0x140003263  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003267  lea     ecx, [rax-7]
0x14000326a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003272  inc     ecx
0x140003274  mov     [rsp+14F0h+var_14B8], r13
0x140003279  mov     [rsp+14F0h+var_14C0], ecx
0x14000327d  call    cs:__imp_GetCurrentThreadId
0x140003283  xorps   xmm0, xmm0
0x140003286  mov     [rsp+14F0h+var_1498], r15
0x14000328b  mov     [rsp+14F0h+var_14B0], eax
0x14000328f  xorps   xmm1, xmm1
0x140003292  xor     eax, eax
0x140003294  mov     [rsp+14F0h+var_1490], r14d
0x140003299  mov     [rbp+13F0h+var_1458], rax
0x14000329d  mov     [rbp+13F0h+var_1470], rax
0x1400032a1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400032a8  mov     [rsp+14F0h+var_148C], edi
0x1400032ac  mov     [rsp+14F0h+var_14A8], r13
0x1400032b1  mov     [rsp+14F0h+var_14A0], r13
0x1400032b6  mov     [rbp+13F0h+var_1448], rsi
0x1400032ba  mov     [rbp+13F0h+var_1440], r12
0x1400032be  mov     [rsp+14F0h+var_1488], r13
0x1400032c3  movups  [rbp+13F0h+var_1468], xmm0
0x1400032c7  movups  [rsp+14F0h+var_1480], xmm1
0x1400032cc  test    rax, rax
0x1400032cf  jz      short loc_1400032DC
0x1400032d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032d6  mov     [rbp+13F0h+var_1450], rax
0x1400032da  jmp     short loc_1400032E0
0x1400032dc  mov     [rbp+13F0h+var_1450], r13
0x1400032e0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400032e7  test    rax, rax
0x1400032ea  jz      short loc_1400032F6
0x1400032ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1400032f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032f6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400032fd  test    rax, rax
0x140003300  jz      short loc_140003316
0x140003302  mov     r8d, 400h
0x140003308  lea     rdx, [rbp+13F0h+var_1430]
0x14000330c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003316  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000331d  test    rax, rax
0x140003320  jz      short loc_14000332C
0x140003322  lea     rcx, [rsp+14F0h+var_14D0]
0x140003327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000332c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003333  test    rax, rax
0x140003336  jz      short loc_140003349
0x140003338  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000333d  jnz     short loc_140003349
0x14000333f  lea     rcx, [rsp+14F0h+var_14D0]
0x140003344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003349  cmp     [rsp+14F0h+var_14C8], r13d
0x14000334e  jl      short loc_140003362
0x140003350  mov     ecx, 8000FFFFh; this
0x140003355  mov     [rsp+14F0h+var_14C8], ecx
0x140003359  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000335e  mov     [rsp+14F0h+var_14C4], eax
0x140003362  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140003369  jnz     short loc_14000338A
0x14000336b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003372  test    rax, rax
0x140003375  jz      short loc_140003380
0x140003377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000337c  test    al, al
0x14000337e  jmp     short loc_140003388
0x140003380  call    cs:__imp_IsDebuggerPresent
0x140003386  test    eax, eax
0x140003388  jz      short loc_140003391
0x14000338a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000338f  jz      short loc_1400033B7
0x140003391  mov     rax, cs:g_pfnResultLoggingCallback
0x140003398  test    rax, rax
0x14000339b  jz      short loc_140003410
0x14000339d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400033a4  jnz     short loc_140003410
0x1400033a6  xor     r8d, r8d
0x1400033a9  lea     rcx, [rsp+14F0h+var_14D0]
0x1400033ae  xor     edx, edx
0x1400033b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033b5  jmp     short loc_140003410
0x1400033b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400033be  mov     ebx, 800h
0x1400033c3  test    rax, rax
0x1400033c6  jz      short loc_1400033E5
0x1400033c8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400033cf  jnz     short loc_1400033E5
0x1400033d1  mov     r8d, ebx
0x1400033d4  lea     rdx, [rbp+13F0h+OutputString]
0x1400033db  lea     rcx, [rsp+14F0h+var_14D0]
0x1400033e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033e5  cmp     [rbp+13F0h+OutputString], r13w
0x1400033ed  jnz     short loc_140003403
0x1400033ef  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400033f4  mov     rdx, rbx; unsigned __int16 *
0x1400033f7  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400033fe  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003403  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000340a  call    cs:__imp_OutputDebugStringW
0x140003410  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003415  jnz     short loc_140003420
0x140003417  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000341e  jz      short loc_140003431
0x140003420  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003427  test    rax, rax
0x14000342a  jz      short loc_140003431
0x14000342c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003431  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003436  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
