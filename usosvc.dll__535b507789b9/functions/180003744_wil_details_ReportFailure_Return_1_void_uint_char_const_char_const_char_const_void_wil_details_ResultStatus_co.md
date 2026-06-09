# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003744`
- end: `0x1800039d1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000321c`

## callees

- `0x1800026d0`
- `0x180003198`
- `0x180003744`
- `0x180004964`
- `0x180005860`
- `0x180006790`
- `0x18000686c`
- `0x18000e400`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800038e6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800038e6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003970`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003970`

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
0x180003744  push    rbp
0x180003746  push    rbx
0x180003747  push    rsi
0x180003748  push    rdi
0x180003749  push    r12
0x18000374b  push    r14
0x18000374d  push    r15
0x18000374f  lea     rbp, [rsp-13D0h]
0x180003757  mov     eax, 14D0h
0x18000375c  call    _alloca_probe
0x180003761  sub     rsp, rax
0x180003764  mov     rax, cs:__security_cookie
0x18000376b  xor     rax, rsp
0x18000376e  mov     [rbp+1400h+var_40], rax
0x180003775  mov     r14, r8
0x180003778  mov     esi, edx
0x18000377a  mov     r15, rcx
0x18000377d  mov     rdi, [rbp+1400h+arg_28]
0x180003784  xor     edx, edx; Val
0x180003786  mov     r8d, 98h; Size
0x18000378c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003791  call    memset_0
0x180003796  nop
0x180003797  xor     r12d, r12d
0x18000379a  mov     [rbp+1400h+OutputString], r12w
0x1800037a2  mov     [rbp+1400h+var_1440], r12b
0x1800037a6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800037ad  mov     ecx, [rdx]; this
0x1800037af  mov     [rsp+1500h+var_14D8], ecx
0x1800037b3  mov     eax, [rdx+4]
0x1800037b6  mov     [rsp+1500h+var_14D4], eax
0x1800037ba  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800037bf  mov     ebx, eax
0x1800037c1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800037c9  mov     ecx, r12d
0x1800037cc  lea     eax, [r12+8]
0x1800037d1  cmp     dword ptr [rdx+8], 1
0x1800037d5  cmovz   ecx, eax
0x1800037d8  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800037dc  lea     ecx, [rax-7]
0x1800037df  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800037e7  inc     ecx
0x1800037e9  mov     [rsp+1500h+var_14D0], ecx
0x1800037ed  mov     [rsp+1500h+var_14C8], r12
0x1800037f2  call    cs:__imp_GetCurrentThreadId
0x1800037f8  mov     [rsp+1500h+var_14C0], eax
0x1800037fc  mov     [rsp+1500h+var_14A8], r14
0x180003801  mov     [rsp+1500h+var_14A0], esi
0x180003805  mov     [rsp+1500h+var_149C], ebx
0x180003809  mov     [rsp+1500h+var_14B8], r12
0x18000380e  mov     [rsp+1500h+var_14B0], r12
0x180003813  mov     [rbp+1400h+var_1458], rdi
0x180003817  mov     [rbp+1400h+var_1450], r15
0x18000381b  mov     [rsp+1500h+var_1498], r12
0x180003820  xorps   xmm0, xmm0
0x180003823  xor     eax, eax
0x180003825  movups  [rbp+1400h+var_1478], xmm0
0x180003829  mov     [rbp+1400h+var_1468], rax
0x18000382d  xorps   xmm1, xmm1
0x180003830  movups  [rsp+1500h+var_1490], xmm1
0x180003835  mov     [rbp+1400h+var_1480], rax
0x180003839  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003840  test    rax, rax
0x180003843  jz      short loc_180003850
0x180003845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000384a  mov     [rbp+1400h+var_1460], rax
0x18000384e  jmp     short loc_180003854
0x180003850  mov     [rbp+1400h+var_1460], r12
0x180003854  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000385b  test    rax, rax
0x18000385e  jz      short loc_18000386A
0x180003860  lea     rcx, [rsp+1500h+var_14E0]
0x180003865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000386a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003871  test    rax, rax
0x180003874  jz      short loc_18000388A
0x180003876  mov     r8d, 400h
0x18000387c  lea     rdx, [rbp+1400h+var_1440]
0x180003880  lea     rcx, [rsp+1500h+var_14E0]
0x180003885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003891  test    rax, rax
0x180003894  jz      short loc_1800038A0
0x180003896  lea     rcx, [rsp+1500h+var_14E0]
0x18000389b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038a0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800038a7  test    rax, rax
0x1800038aa  jz      short loc_1800038BD
0x1800038ac  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800038b1  jnz     short loc_1800038BD
0x1800038b3  lea     rcx, [rsp+1500h+var_14E0]
0x1800038b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038bd  cmp     [rsp+1500h+var_14D8], r12d
0x1800038c2  jge     loc_1800039CB
0x1800038c8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800038cf  jnz     short loc_1800038F0
0x1800038d1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800038d8  test    rax, rax
0x1800038db  jz      short loc_1800038E6
0x1800038dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e2  test    al, al
0x1800038e4  jmp     short loc_1800038EE
0x1800038e6  call    cs:__imp_IsDebuggerPresent
0x1800038ec  test    eax, eax
0x1800038ee  jz      short loc_1800038F7
0x1800038f0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800038f5  jz      short loc_18000391D
0x1800038f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800038fe  test    rax, rax
0x180003901  jz      short loc_180003976
0x180003903  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000390a  jnz     short loc_180003976
0x18000390c  xor     r8d, r8d
0x18000390f  xor     edx, edx
0x180003911  lea     rcx, [rsp+1500h+var_14E0]
0x180003916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000391b  jmp     short loc_180003976
0x18000391d  mov     ebx, 800h
0x180003922  mov     rax, cs:g_pfnResultLoggingCallback
0x180003929  test    rax, rax
0x18000392c  jz      short loc_18000394B
0x18000392e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003935  jnz     short loc_18000394B
0x180003937  mov     r8d, ebx
0x18000393a  lea     rdx, [rbp+1400h+OutputString]
0x180003941  lea     rcx, [rsp+1500h+var_14E0]
0x180003946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000394b  cmp     [rbp+1400h+OutputString], r12w
0x180003953  jnz     short loc_180003969
0x180003955  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000395a  mov     rdx, rbx; unsigned __int16 *
0x18000395d  lea     rcx, [rbp+1400h+OutputString]; this
0x180003964  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003969  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003970  call    cs:__imp_OutputDebugStringW
0x180003976  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000397b  jnz     short loc_180003986
0x18000397d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003984  jz      short loc_180003998
0x180003986  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000398d  test    rax, rax
0x180003990  jz      short loc_180003998
0x180003992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003997  nop
0x180003998  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000399d  jnz     short loc_1800039C0
0x18000399f  mov     rcx, [rbp+1400h+var_40]
0x1800039a6  xor     rcx, rsp; StackCookie
0x1800039a9  call    __security_check_cookie
0x1800039ae  add     rsp, 14D0h
0x1800039b5  pop     r15
0x1800039b7  pop     r14
0x1800039b9  pop     r12
0x1800039bb  pop     rdi
0x1800039bc  pop     rsi
0x1800039bd  pop     rbx
0x1800039be  pop     rbp
0x1800039bf  retn
0x1800039c0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800039c5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800039cb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
