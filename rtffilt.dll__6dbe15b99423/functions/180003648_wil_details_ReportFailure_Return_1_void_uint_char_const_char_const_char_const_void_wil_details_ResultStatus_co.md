# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003648`
- end: `0x1800038ee`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002dfc`

## callees

- `0x180001e40`
- `0x1800028b4`
- `0x180003648`
- `0x180006b04`
- `0x180008748`
- `0x18000c2e0`
- `0x18000c558`
- `0x180019850`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000370e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000370e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003803`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003803`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000388d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000388d`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v18, v16);
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
0x180003648  push    rbp
0x18000364a  push    rbx
0x18000364b  push    rsi
0x18000364c  push    rdi
0x18000364d  push    r12
0x18000364f  push    r14
0x180003651  push    r15
0x180003653  lea     rbp, [rsp-13D0h]
0x18000365b  mov     eax, 14D0h
0x180003660  call    _alloca_probe
0x180003665  sub     rsp, rax
0x180003668  mov     rax, cs:__security_cookie
0x18000366f  xor     rax, rsp
0x180003672  mov     [rbp+1400h+var_40], rax
0x180003679  mov     rsi, r8
0x18000367c  mov     edi, edx
0x18000367e  mov     rbx, rcx
0x180003681  mov     r14, [rbp+1400h+arg_28]
0x180003688  xor     edx, edx; Val
0x18000368a  mov     r8d, 98h; Size
0x180003690  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003695  call    memset_0
0x18000369a  nop
0x18000369b  xor     r12d, r12d
0x18000369e  mov     [rbp+1400h+OutputString], r12w
0x1800036a6  mov     [rbp+1400h+var_1440], r12b
0x1800036aa  mov     rdx, [rbp+1400h+arg_30]; int
0x1800036b1  mov     ecx, [rdx]; this
0x1800036b3  mov     [rsp+1500h+var_14D8], ecx
0x1800036b7  mov     eax, [rdx+4]
0x1800036ba  mov     [rsp+1500h+var_14D4], eax
0x1800036be  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800036c3  mov     r15d, eax
0x1800036c6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800036ce  mov     ecx, r12d
0x1800036d1  lea     eax, [r12+8]
0x1800036d6  cmp     dword ptr [rdx+8], 1
0x1800036da  cmovz   ecx, eax
0x1800036dd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800036e1  lea     ecx, [rax-7]
0x1800036e4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800036ec  inc     ecx
0x1800036ee  mov     [rsp+1500h+var_14D0], ecx
0x1800036f2  mov     rcx, [rbp+1400h+arg_38]
0x1800036f9  test    rcx, rcx
0x1800036fc  jz      short loc_180003709
0x1800036fe  cmp     [rcx], r12w
0x180003702  mov     [rsp+1500h+var_14C8], rcx
0x180003707  jnz     short loc_18000370E
0x180003709  mov     [rsp+1500h+var_14C8], r12
0x18000370e  call    cs:__imp_GetCurrentThreadId
0x180003714  mov     [rsp+1500h+var_14C0], eax
0x180003718  mov     [rsp+1500h+var_14A8], rsi
0x18000371d  mov     [rsp+1500h+var_14A0], edi
0x180003721  mov     [rsp+1500h+var_149C], r15d
0x180003726  mov     [rsp+1500h+var_14B8], r12
0x18000372b  mov     [rsp+1500h+var_14B0], r12
0x180003730  mov     [rbp+1400h+var_1458], r14
0x180003734  mov     [rbp+1400h+var_1450], rbx
0x180003738  mov     [rsp+1500h+var_1498], r12
0x18000373d  xorps   xmm0, xmm0
0x180003740  xor     eax, eax
0x180003742  movups  [rbp+1400h+var_1478], xmm0
0x180003746  mov     [rbp+1400h+var_1468], rax
0x18000374a  xorps   xmm1, xmm1
0x18000374d  movups  [rsp+1500h+var_1490], xmm1
0x180003752  mov     [rbp+1400h+var_1480], rax
0x180003756  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000375d  test    rax, rax
0x180003760  jz      short loc_18000376D
0x180003762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003767  mov     [rbp+1400h+var_1460], rax
0x18000376b  jmp     short loc_180003771
0x18000376d  mov     [rbp+1400h+var_1460], r12
0x180003771  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003778  test    rax, rax
0x18000377b  jz      short loc_180003787
0x18000377d  lea     rcx, [rsp+1500h+var_14E0]
0x180003782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003787  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000378e  test    rax, rax
0x180003791  jz      short loc_1800037A7
0x180003793  mov     r8d, 400h
0x180003799  lea     rdx, [rbp+1400h+var_1440]
0x18000379d  lea     rcx, [rsp+1500h+var_14E0]
0x1800037a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037a7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800037ae  test    rax, rax
0x1800037b1  jz      short loc_1800037BD
0x1800037b3  lea     rcx, [rsp+1500h+var_14E0]
0x1800037b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037bd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800037c4  test    rax, rax
0x1800037c7  jz      short loc_1800037DA
0x1800037c9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800037ce  jnz     short loc_1800037DA
0x1800037d0  lea     rcx, [rsp+1500h+var_14E0]
0x1800037d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037da  cmp     [rsp+1500h+var_14D8], r12d
0x1800037df  jge     loc_1800038E8
0x1800037e5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800037ec  jnz     short loc_18000380D
0x1800037ee  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800037f5  test    rax, rax
0x1800037f8  jz      short loc_180003803
0x1800037fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ff  test    al, al
0x180003801  jmp     short loc_18000380B
0x180003803  call    cs:__imp_IsDebuggerPresent
0x180003809  test    eax, eax
0x18000380b  jz      short loc_180003814
0x18000380d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003812  jz      short loc_18000383A
0x180003814  mov     rax, cs:g_pfnResultLoggingCallback
0x18000381b  test    rax, rax
0x18000381e  jz      short loc_180003893
0x180003820  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003827  jnz     short loc_180003893
0x180003829  xor     r8d, r8d
0x18000382c  xor     edx, edx
0x18000382e  lea     rcx, [rsp+1500h+var_14E0]
0x180003833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003838  jmp     short loc_180003893
0x18000383a  mov     ebx, 800h
0x18000383f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003846  test    rax, rax
0x180003849  jz      short loc_180003868
0x18000384b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003852  jnz     short loc_180003868
0x180003854  mov     r8d, ebx
0x180003857  lea     rdx, [rbp+1400h+OutputString]
0x18000385e  lea     rcx, [rsp+1500h+var_14E0]
0x180003863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003868  cmp     [rbp+1400h+OutputString], r12w
0x180003870  jnz     short loc_180003886
0x180003872  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003877  mov     rdx, rbx; wchar_t *
0x18000387a  lea     rcx, [rbp+1400h+OutputString]; this
0x180003881  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003886  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000388d  call    cs:__imp_OutputDebugStringW
0x180003893  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003898  jnz     short loc_1800038A3
0x18000389a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800038a1  jz      short loc_1800038B5
0x1800038a3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800038aa  test    rax, rax
0x1800038ad  jz      short loc_1800038B5
0x1800038af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b4  nop
0x1800038b5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800038ba  jnz     short loc_1800038DD
0x1800038bc  mov     rcx, [rbp+1400h+var_40]
0x1800038c3  xor     rcx, rsp; StackCookie
0x1800038c6  call    __security_check_cookie
0x1800038cb  add     rsp, 14D0h
0x1800038d2  pop     r15
0x1800038d4  pop     r14
0x1800038d6  pop     r12
0x1800038d8  pop     rdi
0x1800038d9  pop     rsi
0x1800038da  pop     rbx
0x1800038db  pop     rbp
0x1800038dc  retn
0x1800038dd  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800038e2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800038e8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
