# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003868`
- end: `0x180003af5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000352c`

## callees

- `0x180003868`
- `0x180005de4`
- `0x180007c40`
- `0x180009cb8`
- `0x18000ad50`
- `0x18001b0f6`
- `0x18001b150`
- `0x18001b210`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003916`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003916`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003a94`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003a94`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a0a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a0a`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180003868  push    rbp
0x18000386a  push    rbx
0x18000386b  push    rsi
0x18000386c  push    rdi
0x18000386d  push    r12
0x18000386f  push    r14
0x180003871  push    r15
0x180003873  lea     rbp, [rsp-13D0h]
0x18000387b  mov     eax, 14D0h
0x180003880  call    _alloca_probe
0x180003885  sub     rsp, rax
0x180003888  mov     rax, cs:__security_cookie
0x18000388f  xor     rax, rsp
0x180003892  mov     [rbp+1400h+var_40], rax
0x180003899  mov     r14, r8
0x18000389c  mov     esi, edx
0x18000389e  mov     r15, rcx
0x1800038a1  mov     rdi, [rbp+1400h+arg_28]
0x1800038a8  xor     edx, edx; Val
0x1800038aa  mov     r8d, 98h; Size
0x1800038b0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800038b5  call    memset_0
0x1800038ba  nop
0x1800038bb  xor     r12d, r12d
0x1800038be  mov     [rbp+1400h+OutputString], r12w
0x1800038c6  mov     [rbp+1400h+var_1440], r12b
0x1800038ca  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800038d1  mov     ecx, [rdx]; this
0x1800038d3  mov     [rsp+1500h+var_14D8], ecx
0x1800038d7  mov     eax, [rdx+4]
0x1800038da  mov     [rsp+1500h+var_14D4], eax
0x1800038de  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800038e3  mov     ebx, eax
0x1800038e5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800038ed  mov     ecx, r12d
0x1800038f0  lea     eax, [r12+8]
0x1800038f5  cmp     dword ptr [rdx+8], 1
0x1800038f9  cmovz   ecx, eax
0x1800038fc  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003900  lea     ecx, [rax-7]
0x180003903  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000390b  inc     ecx
0x18000390d  mov     [rsp+1500h+var_14D0], ecx
0x180003911  mov     [rsp+1500h+var_14C8], r12
0x180003916  call    cs:__imp_GetCurrentThreadId
0x18000391c  mov     [rsp+1500h+var_14C0], eax
0x180003920  mov     [rsp+1500h+var_14A8], r14
0x180003925  mov     [rsp+1500h+var_14A0], esi
0x180003929  mov     [rsp+1500h+var_149C], ebx
0x18000392d  mov     [rsp+1500h+var_14B8], r12
0x180003932  mov     [rsp+1500h+var_14B0], r12
0x180003937  mov     [rbp+1400h+var_1458], rdi
0x18000393b  mov     [rbp+1400h+var_1450], r15
0x18000393f  mov     [rsp+1500h+var_1498], r12
0x180003944  xorps   xmm0, xmm0
0x180003947  xor     eax, eax
0x180003949  movups  [rbp+1400h+var_1478], xmm0
0x18000394d  mov     [rbp+1400h+var_1468], rax
0x180003951  xorps   xmm1, xmm1
0x180003954  movups  [rsp+1500h+var_1490], xmm1
0x180003959  mov     [rbp+1400h+var_1480], rax
0x18000395d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003964  test    rax, rax
0x180003967  jz      short loc_180003974
0x180003969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000396e  mov     [rbp+1400h+var_1460], rax
0x180003972  jmp     short loc_180003978
0x180003974  mov     [rbp+1400h+var_1460], r12
0x180003978  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000397f  test    rax, rax
0x180003982  jz      short loc_18000398E
0x180003984  lea     rcx, [rsp+1500h+var_14E0]
0x180003989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000398e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003995  test    rax, rax
0x180003998  jz      short loc_1800039AE
0x18000399a  mov     r8d, 400h
0x1800039a0  lea     rdx, [rbp+1400h+var_1440]
0x1800039a4  lea     rcx, [rsp+1500h+var_14E0]
0x1800039a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ae  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039b5  test    rax, rax
0x1800039b8  jz      short loc_1800039C4
0x1800039ba  lea     rcx, [rsp+1500h+var_14E0]
0x1800039bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039cb  test    rax, rax
0x1800039ce  jz      short loc_1800039E1
0x1800039d0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800039d5  jnz     short loc_1800039E1
0x1800039d7  lea     rcx, [rsp+1500h+var_14E0]
0x1800039dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039e1  cmp     [rsp+1500h+var_14D8], r12d
0x1800039e6  jge     loc_180003AEF
0x1800039ec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800039f3  jnz     short loc_180003A14
0x1800039f5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800039fc  test    rax, rax
0x1800039ff  jz      short loc_180003A0A
0x180003a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a06  test    al, al
0x180003a08  jmp     short loc_180003A12
0x180003a0a  call    cs:__imp_IsDebuggerPresent
0x180003a10  test    eax, eax
0x180003a12  jz      short loc_180003A1B
0x180003a14  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003a19  jz      short loc_180003A41
0x180003a1b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a22  test    rax, rax
0x180003a25  jz      short loc_180003A9A
0x180003a27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003a2e  jnz     short loc_180003A9A
0x180003a30  xor     r8d, r8d
0x180003a33  xor     edx, edx
0x180003a35  lea     rcx, [rsp+1500h+var_14E0]
0x180003a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a3f  jmp     short loc_180003A9A
0x180003a41  mov     ebx, 800h
0x180003a46  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a4d  test    rax, rax
0x180003a50  jz      short loc_180003A6F
0x180003a52  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003a59  jnz     short loc_180003A6F
0x180003a5b  mov     r8d, ebx
0x180003a5e  lea     rdx, [rbp+1400h+OutputString]
0x180003a65  lea     rcx, [rsp+1500h+var_14E0]
0x180003a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a6f  cmp     [rbp+1400h+OutputString], r12w
0x180003a77  jnz     short loc_180003A8D
0x180003a79  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003a7e  mov     rdx, rbx; unsigned __int16 *
0x180003a81  lea     rcx, [rbp+1400h+OutputString]; this
0x180003a88  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003a8d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003a94  call    cs:__imp_OutputDebugStringW
0x180003a9a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003a9f  jnz     short loc_180003AAA
0x180003aa1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003aa8  jz      short loc_180003ABC
0x180003aaa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003ab1  test    rax, rax
0x180003ab4  jz      short loc_180003ABC
0x180003ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003abb  nop
0x180003abc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003ac1  jnz     short loc_180003AE4
0x180003ac3  mov     rcx, [rbp+1400h+var_40]
0x180003aca  xor     rcx, rsp; StackCookie
0x180003acd  call    __security_check_cookie
0x180003ad2  add     rsp, 14D0h
0x180003ad9  pop     r15
0x180003adb  pop     r14
0x180003add  pop     r12
0x180003adf  pop     rdi
0x180003ae0  pop     rsi
0x180003ae1  pop     rbx
0x180003ae2  pop     rbp
0x180003ae3  retn
0x180003ae4  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003ae9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003aef  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
