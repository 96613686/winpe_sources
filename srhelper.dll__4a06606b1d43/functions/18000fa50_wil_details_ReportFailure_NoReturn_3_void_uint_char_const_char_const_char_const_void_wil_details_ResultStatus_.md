# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000fa50`
- end: `0x18000fcb0`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000f7f4`

## callees

- `0x18000fa50`
- `0x180011964`
- `0x1800120fc`
- `0x180012cd0`
- `0x1800147d0`
- `0x1800157be`
- `0x180015880`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000faf1`
- `KERNEL32!GetCurrentThreadId` at `0x18000faf1`
- `KERNEL32!OutputDebugStringW` at `0x18000fc7e`
- `KERNEL32!OutputDebugStringW` at `0x18000fc7e`
- `KERNEL32!IsDebuggerPresent` at `0x18000fbf4`
- `KERNEL32!IsDebuggerPresent` at `0x18000fbf4`

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
0x18000fa50  mov     [rsp-8+arg_18], rbx
0x18000fa55  push    rbp
0x18000fa56  push    rsi
0x18000fa57  push    rdi
0x18000fa58  push    r12
0x18000fa5a  push    r13
0x18000fa5c  push    r14
0x18000fa5e  push    r15
0x18000fa60  lea     rbp, [rsp-13C0h]
0x18000fa68  mov     eax, 14C0h
0x18000fa6d  call    _alloca_probe
0x18000fa72  sub     rsp, rax
0x18000fa75  mov     rsi, [rbp+13F0h+arg_28]
0x18000fa7c  mov     r15, r8
0x18000fa7f  mov     r14d, edx
0x18000fa82  mov     r12, rcx
0x18000fa85  xor     edx, edx; Val
0x18000fa87  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000fa8c  mov     r8d, 98h; Size
0x18000fa92  call    memset_0
0x18000fa97  mov     rbx, [rbp+13F0h+arg_30]
0x18000fa9e  xor     r13d, r13d
0x18000faa1  mov     [rbp+13F0h+OutputString], r13w
0x18000faa9  mov     [rbp+13F0h+var_1430], r13b
0x18000faad  mov     ecx, [rbx]; this
0x18000faaf  mov     eax, [rbx+4]
0x18000fab2  mov     [rsp+14F0h+var_14C8], ecx
0x18000fab6  mov     [rsp+14F0h+var_14C4], eax
0x18000faba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000fabf  cmp     dword ptr [rbx+8], 1
0x18000fac3  mov     edi, eax
0x18000fac5  lea     eax, [r13+8]
0x18000fac9  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000fad1  mov     ecx, r13d
0x18000fad4  cmovz   ecx, eax
0x18000fad7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000fadb  lea     ecx, [rax-7]
0x18000fade  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000fae6  inc     ecx
0x18000fae8  mov     [rsp+14F0h+var_14B8], r13
0x18000faed  mov     [rsp+14F0h+var_14C0], ecx
0x18000faf1  call    cs:__imp_GetCurrentThreadId
0x18000faf7  xorps   xmm0, xmm0
0x18000fafa  mov     [rsp+14F0h+var_1498], r15
0x18000faff  mov     [rsp+14F0h+var_14B0], eax
0x18000fb03  xorps   xmm1, xmm1
0x18000fb06  xor     eax, eax
0x18000fb08  mov     [rsp+14F0h+var_1490], r14d
0x18000fb0d  mov     [rbp+13F0h+var_1458], rax
0x18000fb11  mov     [rbp+13F0h+var_1470], rax
0x18000fb15  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000fb1c  mov     [rsp+14F0h+var_148C], edi
0x18000fb20  mov     [rsp+14F0h+var_14A8], r13
0x18000fb25  mov     [rsp+14F0h+var_14A0], r13
0x18000fb2a  mov     [rbp+13F0h+var_1448], rsi
0x18000fb2e  mov     [rbp+13F0h+var_1440], r12
0x18000fb32  mov     [rsp+14F0h+var_1488], r13
0x18000fb37  movups  [rbp+13F0h+var_1468], xmm0
0x18000fb3b  movups  [rsp+14F0h+var_1480], xmm1
0x18000fb40  test    rax, rax
0x18000fb43  jz      short loc_18000FB50
0x18000fb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb4a  mov     [rbp+13F0h+var_1450], rax
0x18000fb4e  jmp     short loc_18000FB54
0x18000fb50  mov     [rbp+13F0h+var_1450], r13
0x18000fb54  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000fb5b  test    rax, rax
0x18000fb5e  jz      short loc_18000FB6A
0x18000fb60  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb6a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000fb71  test    rax, rax
0x18000fb74  jz      short loc_18000FB8A
0x18000fb76  mov     r8d, 400h
0x18000fb7c  lea     rdx, [rbp+13F0h+var_1430]
0x18000fb80  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fb85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb8a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000fb91  test    rax, rax
0x18000fb94  jz      short loc_18000FBA0
0x18000fb96  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fba0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000fba7  test    rax, rax
0x18000fbaa  jz      short loc_18000FBBD
0x18000fbac  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000fbb1  jnz     short loc_18000FBBD
0x18000fbb3  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fbb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbbd  cmp     [rsp+14F0h+var_14C8], r13d
0x18000fbc2  jl      short loc_18000FBD6
0x18000fbc4  mov     ecx, 8000FFFFh; this
0x18000fbc9  mov     [rsp+14F0h+var_14C8], ecx
0x18000fbcd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fbd2  mov     [rsp+14F0h+var_14C4], eax
0x18000fbd6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000fbdd  jnz     short loc_18000FBFE
0x18000fbdf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000fbe6  test    rax, rax
0x18000fbe9  jz      short loc_18000FBF4
0x18000fbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbf0  test    al, al
0x18000fbf2  jmp     short loc_18000FBFC
0x18000fbf4  call    cs:__imp_IsDebuggerPresent
0x18000fbfa  test    eax, eax
0x18000fbfc  jz      short loc_18000FC05
0x18000fbfe  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000fc03  jz      short loc_18000FC2B
0x18000fc05  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fc0c  test    rax, rax
0x18000fc0f  jz      short loc_18000FC84
0x18000fc11  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000fc18  jnz     short loc_18000FC84
0x18000fc1a  xor     r8d, r8d
0x18000fc1d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fc22  xor     edx, edx
0x18000fc24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc29  jmp     short loc_18000FC84
0x18000fc2b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fc32  mov     ebx, 800h
0x18000fc37  test    rax, rax
0x18000fc3a  jz      short loc_18000FC59
0x18000fc3c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000fc43  jnz     short loc_18000FC59
0x18000fc45  mov     r8d, ebx
0x18000fc48  lea     rdx, [rbp+13F0h+OutputString]
0x18000fc4f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc59  cmp     [rbp+13F0h+OutputString], r13w
0x18000fc61  jnz     short loc_18000FC77
0x18000fc63  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000fc68  mov     rdx, rbx; unsigned __int16 *
0x18000fc6b  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000fc72  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000fc77  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000fc7e  call    cs:__imp_OutputDebugStringW
0x18000fc84  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000fc89  jnz     short loc_18000FC94
0x18000fc8b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000fc92  jz      short loc_18000FCA5
0x18000fc94  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000fc9b  test    rax, rax
0x18000fc9e  jz      short loc_18000FCA5
0x18000fca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fca5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000fcaa  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
