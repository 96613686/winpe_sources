# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005410`
- end: `0x1800056d5`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004f00`

## callees

- `0x180004c80`
- `0x180005410`
- `0x180007af4`
- `0x180008f90`
- `0x18000ae38`
- `0x18000b590`
- `0x18000b75c`
- `0x18002ef20`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054d1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005669`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005669`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800055cd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800055cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x180005410  mov     [rsp-8+arg_18], rbx
0x180005415  push    rbp
0x180005416  push    rsi
0x180005417  push    rdi
0x180005418  push    r12
0x18000541a  push    r13
0x18000541c  push    r14
0x18000541e  push    r15
0x180005420  lea     rbp, [rsp-13C0h]
0x180005428  mov     eax, 14C0h
0x18000542d  call    _alloca_probe
0x180005432  sub     rsp, rax
0x180005435  mov     r14, r8
0x180005438  mov     esi, edx
0x18000543a  mov     rbx, rcx
0x18000543d  mov     r15, [rbp+13F0h+arg_28]
0x180005444  xor     r13d, r13d
0x180005447  cmp     cs:g_pfnThrowPlatformException, r13
0x18000544e  setnz   dil
0x180005452  xor     edx, edx; Val
0x180005454  mov     r8d, 98h; Size
0x18000545a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000545f  call    memset_0
0x180005464  nop
0x180005465  mov     [rbp+13F0h+OutputString], r13w
0x18000546d  mov     [rbp+13F0h+var_1430], r13b
0x180005471  mov     rdx, [rbp+13F0h+arg_30]; int
0x180005478  mov     ecx, [rdx]; this
0x18000547a  mov     [rsp+14F0h+var_14C8], ecx
0x18000547e  mov     eax, [rdx+4]
0x180005481  mov     [rsp+14F0h+var_14C4], eax
0x180005485  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000548a  mov     r12d, eax
0x18000548d  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180005492  mov     ecx, r13d
0x180005495  lea     eax, [r13+8]
0x180005499  cmp     dword ptr [rdx+8], 1
0x18000549d  cmovz   ecx, eax
0x1800054a0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800054a4  lea     ecx, [rax-7]
0x1800054a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800054af  inc     ecx
0x1800054b1  mov     [rsp+14F0h+var_14C0], ecx
0x1800054b5  mov     rcx, [rbp+13F0h+arg_38]
0x1800054bc  test    rcx, rcx
0x1800054bf  jz      short loc_1800054CC
0x1800054c1  cmp     [rcx], r13w
0x1800054c5  mov     [rsp+14F0h+var_14B8], rcx
0x1800054ca  jnz     short loc_1800054D1
0x1800054cc  mov     [rsp+14F0h+var_14B8], r13
0x1800054d1  call    cs:__imp_GetCurrentThreadId
0x1800054d7  mov     [rsp+14F0h+var_14B0], eax
0x1800054db  mov     [rsp+14F0h+var_1498], r14
0x1800054e0  mov     [rsp+14F0h+var_1490], esi
0x1800054e4  mov     [rsp+14F0h+var_148C], r12d
0x1800054e9  mov     [rsp+14F0h+var_14A8], r13
0x1800054ee  mov     [rsp+14F0h+var_14A0], r13
0x1800054f3  mov     [rbp+13F0h+var_1448], r15
0x1800054f7  mov     [rbp+13F0h+var_1440], rbx
0x1800054fb  mov     [rsp+14F0h+var_1488], r13
0x180005500  xorps   xmm0, xmm0
0x180005503  xor     eax, eax
0x180005505  movups  [rbp+13F0h+var_1468], xmm0
0x180005509  mov     [rbp+13F0h+var_1458], rax
0x18000550d  xorps   xmm1, xmm1
0x180005510  movups  [rsp+14F0h+var_1480], xmm1
0x180005515  mov     [rbp+13F0h+var_1470], rax
0x180005519  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005520  test    rax, rax
0x180005523  jz      short loc_180005530
0x180005525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000552a  mov     [rbp+13F0h+var_1450], rax
0x18000552e  jmp     short loc_180005534
0x180005530  mov     [rbp+13F0h+var_1450], r13
0x180005534  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000553b  test    rax, rax
0x18000553e  jz      short loc_18000554A
0x180005540  lea     rcx, [rsp+14F0h+var_14D0]
0x180005545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000554a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005551  test    rax, rax
0x180005554  jz      short loc_18000556A
0x180005556  mov     r8d, 400h
0x18000555c  lea     rdx, [rbp+13F0h+var_1430]
0x180005560  lea     rcx, [rsp+14F0h+var_14D0]
0x180005565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000556a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005571  test    rax, rax
0x180005574  jz      short loc_180005580
0x180005576  lea     rcx, [rsp+14F0h+var_14D0]
0x18000557b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005580  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005587  test    rax, rax
0x18000558a  jz      short loc_1800055A2
0x18000558c  test    dil, dil
0x18000558f  jnz     short loc_1800055A2
0x180005591  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005596  jnz     short loc_1800055A2
0x180005598  lea     rcx, [rsp+14F0h+var_14D0]
0x18000559d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a2  cmp     [rsp+14F0h+var_14C8], r13d
0x1800055a7  jl      short loc_1800055AF
0x1800055a9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800055af  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800055b6  jnz     short loc_1800055D7
0x1800055b8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800055bf  test    rax, rax
0x1800055c2  jz      short loc_1800055CD
0x1800055c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055c9  test    al, al
0x1800055cb  jmp     short loc_1800055D5
0x1800055cd  call    cs:__imp_IsDebuggerPresent
0x1800055d3  test    eax, eax
0x1800055d5  jz      short loc_1800055E0
0x1800055d7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800055dc  mov     bl, 1
0x1800055de  jz      short loc_1800055E3
0x1800055e0  mov     bl, r13b
0x1800055e3  test    dil, dil
0x1800055e6  jnz     short loc_180005612
0x1800055e8  test    bl, bl
0x1800055ea  jnz     short loc_180005612
0x1800055ec  mov     rax, cs:g_pfnResultLoggingCallback
0x1800055f3  test    rax, rax
0x1800055f6  jz      short loc_18000566F
0x1800055f8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800055ff  jnz     short loc_18000566F
0x180005601  xor     r8d, r8d
0x180005604  xor     edx, edx
0x180005606  lea     rcx, [rsp+14F0h+var_14D0]
0x18000560b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005610  jmp     short loc_18000566F
0x180005612  mov     esi, 800h
0x180005617  mov     rax, cs:g_pfnResultLoggingCallback
0x18000561e  test    rax, rax
0x180005621  jz      short loc_180005640
0x180005623  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000562a  jnz     short loc_180005640
0x18000562c  mov     r8d, esi
0x18000562f  lea     rdx, [rbp+13F0h+OutputString]
0x180005636  lea     rcx, [rsp+14F0h+var_14D0]
0x18000563b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005640  cmp     [rbp+13F0h+OutputString], r13w
0x180005648  jnz     short loc_18000565E
0x18000564a  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000564f  mov     rdx, rsi; unsigned __int16 *
0x180005652  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005659  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000565e  test    bl, bl
0x180005660  jz      short loc_18000566F
0x180005662  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005669  call    cs:__imp_OutputDebugStringW
0x18000566f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005674  jnz     short loc_18000567F
0x180005676  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000567d  jz      short loc_180005691
0x18000567f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005686  test    rax, rax
0x180005689  jz      short loc_180005691
0x18000568b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005690  nop
0x180005691  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005696  jz      short loc_1800056A3
0x180005698  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000569d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800056a3  test    dil, dil
0x1800056a6  jz      short loc_1800056C0
0x1800056a8  lea     rdx, [rbp+13F0h+OutputString]
0x1800056af  lea     rcx, [rsp+14F0h+var_14D0]
0x1800056b4  mov     rax, cs:g_pfnThrowPlatformException
0x1800056bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800056c5  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800056ca  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800056cf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
