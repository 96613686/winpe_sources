# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18002201c`
- end: `0x1800222c8`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180021f70`

## callees

- `0x180003088`
- `0x1800064a4`
- `0x1800078b0`
- `0x1800098f0`
- `0x18000a040`
- `0x18000a20c`
- `0x18002201c`
- `0x180031580`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800220c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800220c5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800221c0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800221c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002225c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002225c`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x18002201c  mov     [rsp-8+arg_18], rbx
0x180022021  push    rbp
0x180022022  push    rsi
0x180022023  push    rdi
0x180022024  push    r12
0x180022026  push    r13
0x180022028  push    r14
0x18002202a  push    r15
0x18002202c  lea     rbp, [rsp-13C0h]
0x180022034  mov     eax, 14C0h
0x180022039  call    _alloca_probe
0x18002203e  sub     rsp, rax
0x180022041  mov     r14, r8
0x180022044  mov     esi, edx
0x180022046  mov     r15, rcx
0x180022049  mov     rdi, [rbp+13F0h+arg_28]
0x180022050  xor     r13d, r13d
0x180022053  cmp     cs:g_pfnThrowPlatformException, r13
0x18002205a  setnz   r12b
0x18002205e  xor     edx, edx; Val
0x180022060  mov     r8d, 98h; Size
0x180022066  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18002206b  call    memset_0
0x180022070  nop
0x180022071  mov     [rbp+13F0h+OutputString], r13w
0x180022079  mov     [rbp+13F0h+var_1430], r13b
0x18002207d  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180022084  mov     ecx, [rdx]; this
0x180022086  mov     [rsp+14F0h+var_14C8], ecx
0x18002208a  mov     eax, [rdx+4]
0x18002208d  mov     [rsp+14F0h+var_14C4], eax
0x180022091  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180022096  mov     ebx, eax
0x180022098  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18002209d  mov     ecx, r13d
0x1800220a0  lea     eax, [r13+8]
0x1800220a4  cmp     dword ptr [rdx+8], 1
0x1800220a8  cmovz   ecx, eax
0x1800220ab  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800220af  lea     ecx, [rax-7]
0x1800220b2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800220ba  inc     ecx
0x1800220bc  mov     [rsp+14F0h+var_14C0], ecx
0x1800220c0  mov     [rsp+14F0h+var_14B8], r13
0x1800220c5  call    cs:__imp_GetCurrentThreadId
0x1800220cb  mov     [rsp+14F0h+var_14B0], eax
0x1800220cf  mov     [rsp+14F0h+var_1498], r14
0x1800220d4  mov     [rsp+14F0h+var_1490], esi
0x1800220d8  mov     [rsp+14F0h+var_148C], ebx
0x1800220dc  mov     [rsp+14F0h+var_14A8], r13
0x1800220e1  mov     [rsp+14F0h+var_14A0], r13
0x1800220e6  mov     [rbp+13F0h+var_1448], rdi
0x1800220ea  mov     [rbp+13F0h+var_1440], r15
0x1800220ee  mov     [rsp+14F0h+var_1488], r13
0x1800220f3  xorps   xmm0, xmm0
0x1800220f6  xor     eax, eax
0x1800220f8  movups  [rbp+13F0h+var_1468], xmm0
0x1800220fc  mov     [rbp+13F0h+var_1458], rax
0x180022100  xorps   xmm1, xmm1
0x180022103  movups  [rsp+14F0h+var_1480], xmm1
0x180022108  mov     [rbp+13F0h+var_1470], rax
0x18002210c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180022113  test    rax, rax
0x180022116  jz      short loc_180022123
0x180022118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002211d  mov     [rbp+13F0h+var_1450], rax
0x180022121  jmp     short loc_180022127
0x180022123  mov     [rbp+13F0h+var_1450], r13
0x180022127  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002212e  test    rax, rax
0x180022131  jz      short loc_18002213D
0x180022133  lea     rcx, [rsp+14F0h+var_14D0]
0x180022138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002213d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180022144  test    rax, rax
0x180022147  jz      short loc_18002215D
0x180022149  mov     r8d, 400h
0x18002214f  lea     rdx, [rbp+13F0h+var_1430]
0x180022153  lea     rcx, [rsp+14F0h+var_14D0]
0x180022158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002215d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180022164  test    rax, rax
0x180022167  jz      short loc_180022173
0x180022169  lea     rcx, [rsp+14F0h+var_14D0]
0x18002216e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022173  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002217a  test    rax, rax
0x18002217d  jz      short loc_180022195
0x18002217f  test    r12b, r12b
0x180022182  jnz     short loc_180022195
0x180022184  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180022189  jnz     short loc_180022195
0x18002218b  lea     rcx, [rsp+14F0h+var_14D0]
0x180022190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022195  cmp     [rsp+14F0h+var_14C8], r13d
0x18002219a  jl      short loc_1800221A2
0x18002219c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800221a2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800221a9  jnz     short loc_1800221CA
0x1800221ab  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800221b2  test    rax, rax
0x1800221b5  jz      short loc_1800221C0
0x1800221b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221bc  test    al, al
0x1800221be  jmp     short loc_1800221C8
0x1800221c0  call    cs:__imp_IsDebuggerPresent
0x1800221c6  test    eax, eax
0x1800221c8  jz      short loc_1800221D3
0x1800221ca  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800221cf  mov     bl, 1
0x1800221d1  jz      short loc_1800221D6
0x1800221d3  mov     bl, r13b
0x1800221d6  test    r12b, r12b
0x1800221d9  jnz     short loc_180022205
0x1800221db  test    bl, bl
0x1800221dd  jnz     short loc_180022205
0x1800221df  mov     rax, cs:g_pfnResultLoggingCallback
0x1800221e6  test    rax, rax
0x1800221e9  jz      short loc_180022262
0x1800221eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800221f2  jnz     short loc_180022262
0x1800221f4  xor     r8d, r8d
0x1800221f7  xor     edx, edx
0x1800221f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800221fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022203  jmp     short loc_180022262
0x180022205  mov     edi, 800h
0x18002220a  mov     rax, cs:g_pfnResultLoggingCallback
0x180022211  test    rax, rax
0x180022214  jz      short loc_180022233
0x180022216  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002221d  jnz     short loc_180022233
0x18002221f  mov     r8d, edi
0x180022222  lea     rdx, [rbp+13F0h+OutputString]
0x180022229  lea     rcx, [rsp+14F0h+var_14D0]
0x18002222e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022233  cmp     [rbp+13F0h+OutputString], r13w
0x18002223b  jnz     short loc_180022251
0x18002223d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180022242  mov     rdx, rdi; unsigned __int16 *
0x180022245  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002224c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180022251  test    bl, bl
0x180022253  jz      short loc_180022262
0x180022255  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18002225c  call    cs:__imp_OutputDebugStringW
0x180022262  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180022267  jnz     short loc_180022272
0x180022269  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180022270  jz      short loc_180022284
0x180022272  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180022279  test    rax, rax
0x18002227c  jz      short loc_180022284
0x18002227e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022283  nop
0x180022284  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180022289  jz      short loc_180022296
0x18002228b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180022290  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180022296  test    r12b, r12b
0x180022299  jz      short loc_1800222B3
0x18002229b  lea     rdx, [rbp+13F0h+OutputString]
0x1800222a2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800222a7  mov     rax, cs:g_pfnThrowPlatformException
0x1800222ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222b3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800222b8  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800222bd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800222c2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
