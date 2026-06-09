# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180007078`
- end: `0x18000733d`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006e68`

## callees

- `0x180003198`
- `0x180004964`
- `0x18000580c`
- `0x180006440`
- `0x180006790`
- `0x18000686c`
- `0x180007078`
- `0x18000e400`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007139`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007139`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007235`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007235`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800072d1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800072d1`

## pseudocode

```c
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
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0);
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
0x180007078  mov     [rsp-8+arg_18], rbx
0x18000707d  push    rbp
0x18000707e  push    rsi
0x18000707f  push    rdi
0x180007080  push    r12
0x180007082  push    r13
0x180007084  push    r14
0x180007086  push    r15
0x180007088  lea     rbp, [rsp-13C0h]
0x180007090  mov     eax, 14C0h
0x180007095  call    _alloca_probe
0x18000709a  sub     rsp, rax
0x18000709d  mov     r14, r8
0x1800070a0  mov     esi, edx
0x1800070a2  mov     rbx, rcx
0x1800070a5  mov     r15, [rbp+13F0h+arg_28]
0x1800070ac  xor     r13d, r13d
0x1800070af  cmp     cs:g_pfnThrowPlatformException, r13
0x1800070b6  setnz   dil
0x1800070ba  xor     edx, edx; Val
0x1800070bc  mov     r8d, 98h; Size
0x1800070c2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800070c7  call    memset_0
0x1800070cc  nop
0x1800070cd  mov     [rbp+13F0h+OutputString], r13w
0x1800070d5  mov     [rbp+13F0h+var_1430], r13b
0x1800070d9  mov     rdx, [rbp+13F0h+arg_30]; int
0x1800070e0  mov     ecx, [rdx]; this
0x1800070e2  mov     [rsp+14F0h+var_14C8], ecx
0x1800070e6  mov     eax, [rdx+4]
0x1800070e9  mov     [rsp+14F0h+var_14C4], eax
0x1800070ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800070f2  mov     r12d, eax
0x1800070f5  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x1800070fa  mov     ecx, r13d
0x1800070fd  lea     eax, [r13+8]
0x180007101  cmp     dword ptr [rdx+8], 1
0x180007105  cmovz   ecx, eax
0x180007108  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000710c  lea     ecx, [rax-7]
0x18000710f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007117  inc     ecx
0x180007119  mov     [rsp+14F0h+var_14C0], ecx
0x18000711d  mov     rcx, [rbp+13F0h+arg_38]
0x180007124  test    rcx, rcx
0x180007127  jz      short loc_180007134
0x180007129  cmp     [rcx], r13w
0x18000712d  mov     [rsp+14F0h+var_14B8], rcx
0x180007132  jnz     short loc_180007139
0x180007134  mov     [rsp+14F0h+var_14B8], r13
0x180007139  call    cs:__imp_GetCurrentThreadId
0x18000713f  mov     [rsp+14F0h+var_14B0], eax
0x180007143  mov     [rsp+14F0h+var_1498], r14
0x180007148  mov     [rsp+14F0h+var_1490], esi
0x18000714c  mov     [rsp+14F0h+var_148C], r12d
0x180007151  mov     [rsp+14F0h+var_14A8], r13
0x180007156  mov     [rsp+14F0h+var_14A0], r13
0x18000715b  mov     [rbp+13F0h+var_1448], r15
0x18000715f  mov     [rbp+13F0h+var_1440], rbx
0x180007163  mov     [rsp+14F0h+var_1488], r13
0x180007168  xorps   xmm0, xmm0
0x18000716b  xor     eax, eax
0x18000716d  movups  [rbp+13F0h+var_1468], xmm0
0x180007171  mov     [rbp+13F0h+var_1458], rax
0x180007175  xorps   xmm1, xmm1
0x180007178  movups  [rsp+14F0h+var_1480], xmm1
0x18000717d  mov     [rbp+13F0h+var_1470], rax
0x180007181  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007188  test    rax, rax
0x18000718b  jz      short loc_180007198
0x18000718d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007192  mov     [rbp+13F0h+var_1450], rax
0x180007196  jmp     short loc_18000719C
0x180007198  mov     [rbp+13F0h+var_1450], r13
0x18000719c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800071a3  test    rax, rax
0x1800071a6  jz      short loc_1800071B2
0x1800071a8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800071ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071b2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800071b9  test    rax, rax
0x1800071bc  jz      short loc_1800071D2
0x1800071be  mov     r8d, 400h
0x1800071c4  lea     rdx, [rbp+13F0h+var_1430]
0x1800071c8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800071cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071d2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800071d9  test    rax, rax
0x1800071dc  jz      short loc_1800071E8
0x1800071de  lea     rcx, [rsp+14F0h+var_14D0]
0x1800071e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071e8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800071ef  test    rax, rax
0x1800071f2  jz      short loc_18000720A
0x1800071f4  test    dil, dil
0x1800071f7  jnz     short loc_18000720A
0x1800071f9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800071fe  jnz     short loc_18000720A
0x180007200  lea     rcx, [rsp+14F0h+var_14D0]
0x180007205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000720a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000720f  jl      short loc_180007217
0x180007211  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007217  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000721e  jnz     short loc_18000723F
0x180007220  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007227  test    rax, rax
0x18000722a  jz      short loc_180007235
0x18000722c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007231  test    al, al
0x180007233  jmp     short loc_18000723D
0x180007235  call    cs:__imp_IsDebuggerPresent
0x18000723b  test    eax, eax
0x18000723d  jz      short loc_180007248
0x18000723f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007244  mov     bl, 1
0x180007246  jz      short loc_18000724B
0x180007248  mov     bl, r13b
0x18000724b  test    dil, dil
0x18000724e  jnz     short loc_18000727A
0x180007250  test    bl, bl
0x180007252  jnz     short loc_18000727A
0x180007254  mov     rax, cs:g_pfnResultLoggingCallback
0x18000725b  test    rax, rax
0x18000725e  jz      short loc_1800072D7
0x180007260  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007267  jnz     short loc_1800072D7
0x180007269  xor     r8d, r8d
0x18000726c  xor     edx, edx
0x18000726e  lea     rcx, [rsp+14F0h+var_14D0]
0x180007273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007278  jmp     short loc_1800072D7
0x18000727a  mov     esi, 800h
0x18000727f  mov     rax, cs:g_pfnResultLoggingCallback
0x180007286  test    rax, rax
0x180007289  jz      short loc_1800072A8
0x18000728b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007292  jnz     short loc_1800072A8
0x180007294  mov     r8d, esi
0x180007297  lea     rdx, [rbp+13F0h+OutputString]
0x18000729e  lea     rcx, [rsp+14F0h+var_14D0]
0x1800072a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072a8  cmp     [rbp+13F0h+OutputString], r13w
0x1800072b0  jnz     short loc_1800072C6
0x1800072b2  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800072b7  mov     rdx, rsi; unsigned __int16 *
0x1800072ba  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800072c1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800072c6  test    bl, bl
0x1800072c8  jz      short loc_1800072D7
0x1800072ca  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800072d1  call    cs:__imp_OutputDebugStringW
0x1800072d7  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800072dc  jnz     short loc_1800072E7
0x1800072de  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800072e5  jz      short loc_1800072F9
0x1800072e7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800072ee  test    rax, rax
0x1800072f1  jz      short loc_1800072F9
0x1800072f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072f8  nop
0x1800072f9  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800072fe  jz      short loc_18000730B
0x180007300  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007305  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000730b  test    dil, dil
0x18000730e  jz      short loc_180007328
0x180007310  lea     rdx, [rbp+13F0h+OutputString]
0x180007317  lea     rcx, [rsp+14F0h+var_14D0]
0x18000731c  mov     rax, cs:g_pfnThrowPlatformException
0x180007323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007328  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000732d  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180007332  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007337  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
