# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180013720`
- end: `0x1800139c6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800131ac`

## callees

- `0x180007660`
- `0x18000856c`
- `0x180013720`
- `0x180015e04`
- `0x1800174a8`
- `0x180019bc0`
- `0x180019e38`
- `0x180068320`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137e6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800138db`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800138db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013965`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013965`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180013720  push    rbp
0x180013722  push    rbx
0x180013723  push    rsi
0x180013724  push    rdi
0x180013725  push    r12
0x180013727  push    r14
0x180013729  push    r15
0x18001372b  lea     rbp, [rsp-13D0h]
0x180013733  mov     eax, 14D0h
0x180013738  call    _alloca_probe
0x18001373d  sub     rsp, rax
0x180013740  mov     rax, cs:__security_cookie
0x180013747  xor     rax, rsp
0x18001374a  mov     [rbp+1400h+var_40], rax
0x180013751  mov     rsi, r8
0x180013754  mov     edi, edx
0x180013756  mov     rbx, rcx
0x180013759  mov     r14, [rbp+1400h+arg_28]
0x180013760  xor     edx, edx; Val
0x180013762  mov     r8d, 98h; Size
0x180013768  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18001376d  call    memset_0
0x180013772  nop
0x180013773  xor     r12d, r12d
0x180013776  mov     [rbp+1400h+OutputString], r12w
0x18001377e  mov     [rbp+1400h+var_1440], r12b
0x180013782  mov     rdx, [rbp+1400h+arg_30]; int
0x180013789  mov     ecx, [rdx]; this
0x18001378b  mov     [rsp+1500h+var_14D8], ecx
0x18001378f  mov     eax, [rdx+4]
0x180013792  mov     [rsp+1500h+var_14D4], eax
0x180013796  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001379b  mov     r15d, eax
0x18001379e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800137a6  mov     ecx, r12d
0x1800137a9  lea     eax, [r12+8]
0x1800137ae  cmp     dword ptr [rdx+8], 1
0x1800137b2  cmovz   ecx, eax
0x1800137b5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800137b9  lea     ecx, [rax-7]
0x1800137bc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800137c4  inc     ecx
0x1800137c6  mov     [rsp+1500h+var_14D0], ecx
0x1800137ca  mov     rcx, [rbp+1400h+arg_38]
0x1800137d1  test    rcx, rcx
0x1800137d4  jz      short loc_1800137E1
0x1800137d6  cmp     [rcx], r12w
0x1800137da  mov     [rsp+1500h+var_14C8], rcx
0x1800137df  jnz     short loc_1800137E6
0x1800137e1  mov     [rsp+1500h+var_14C8], r12
0x1800137e6  call    cs:__imp_GetCurrentThreadId
0x1800137ec  mov     [rsp+1500h+var_14C0], eax
0x1800137f0  mov     [rsp+1500h+var_14A8], rsi
0x1800137f5  mov     [rsp+1500h+var_14A0], edi
0x1800137f9  mov     [rsp+1500h+var_149C], r15d
0x1800137fe  mov     [rsp+1500h+var_14B8], r12
0x180013803  mov     [rsp+1500h+var_14B0], r12
0x180013808  mov     [rbp+1400h+var_1458], r14
0x18001380c  mov     [rbp+1400h+var_1450], rbx
0x180013810  mov     [rsp+1500h+var_1498], r12
0x180013815  xorps   xmm0, xmm0
0x180013818  xor     eax, eax
0x18001381a  movups  [rbp+1400h+var_1478], xmm0
0x18001381e  mov     [rbp+1400h+var_1468], rax
0x180013822  xorps   xmm1, xmm1
0x180013825  movups  [rsp+1500h+var_1490], xmm1
0x18001382a  mov     [rbp+1400h+var_1480], rax
0x18001382e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013835  test    rax, rax
0x180013838  jz      short loc_180013845
0x18001383a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001383f  mov     [rbp+1400h+var_1460], rax
0x180013843  jmp     short loc_180013849
0x180013845  mov     [rbp+1400h+var_1460], r12
0x180013849  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013850  test    rax, rax
0x180013853  jz      short loc_18001385F
0x180013855  lea     rcx, [rsp+1500h+var_14E0]
0x18001385a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001385f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013866  test    rax, rax
0x180013869  jz      short loc_18001387F
0x18001386b  mov     r8d, 400h
0x180013871  lea     rdx, [rbp+1400h+var_1440]
0x180013875  lea     rcx, [rsp+1500h+var_14E0]
0x18001387a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001387f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013886  test    rax, rax
0x180013889  jz      short loc_180013895
0x18001388b  lea     rcx, [rsp+1500h+var_14E0]
0x180013890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013895  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001389c  test    rax, rax
0x18001389f  jz      short loc_1800138B2
0x1800138a1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800138a6  jnz     short loc_1800138B2
0x1800138a8  lea     rcx, [rsp+1500h+var_14E0]
0x1800138ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138b2  cmp     [rsp+1500h+var_14D8], r12d
0x1800138b7  jge     loc_1800139C0
0x1800138bd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800138c4  jnz     short loc_1800138E5
0x1800138c6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800138cd  test    rax, rax
0x1800138d0  jz      short loc_1800138DB
0x1800138d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138d7  test    al, al
0x1800138d9  jmp     short loc_1800138E3
0x1800138db  call    cs:__imp_IsDebuggerPresent
0x1800138e1  test    eax, eax
0x1800138e3  jz      short loc_1800138EC
0x1800138e5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800138ea  jz      short loc_180013912
0x1800138ec  mov     rax, cs:g_pfnResultLoggingCallback
0x1800138f3  test    rax, rax
0x1800138f6  jz      short loc_18001396B
0x1800138f8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800138ff  jnz     short loc_18001396B
0x180013901  xor     r8d, r8d
0x180013904  xor     edx, edx
0x180013906  lea     rcx, [rsp+1500h+var_14E0]
0x18001390b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013910  jmp     short loc_18001396B
0x180013912  mov     ebx, 800h
0x180013917  mov     rax, cs:g_pfnResultLoggingCallback
0x18001391e  test    rax, rax
0x180013921  jz      short loc_180013940
0x180013923  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001392a  jnz     short loc_180013940
0x18001392c  mov     r8d, ebx
0x18001392f  lea     rdx, [rbp+1400h+OutputString]
0x180013936  lea     rcx, [rsp+1500h+var_14E0]
0x18001393b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013940  cmp     [rbp+1400h+OutputString], r12w
0x180013948  jnz     short loc_18001395E
0x18001394a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18001394f  mov     rdx, rbx; unsigned __int16 *
0x180013952  lea     rcx, [rbp+1400h+OutputString]; this
0x180013959  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001395e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180013965  call    cs:__imp_OutputDebugStringW
0x18001396b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180013970  jnz     short loc_18001397B
0x180013972  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180013979  jz      short loc_18001398D
0x18001397b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013982  test    rax, rax
0x180013985  jz      short loc_18001398D
0x180013987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001398c  nop
0x18001398d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180013992  jnz     short loc_1800139B5
0x180013994  mov     rcx, [rbp+1400h+var_40]
0x18001399b  xor     rcx, rsp; StackCookie
0x18001399e  call    __security_check_cookie
0x1800139a3  add     rsp, 14D0h
0x1800139aa  pop     r15
0x1800139ac  pop     r14
0x1800139ae  pop     r12
0x1800139b0  pop     rdi
0x1800139b1  pop     rsi
0x1800139b2  pop     rbx
0x1800139b3  pop     rbp
0x1800139b4  retn
0x1800139b5  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800139ba  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800139c0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
