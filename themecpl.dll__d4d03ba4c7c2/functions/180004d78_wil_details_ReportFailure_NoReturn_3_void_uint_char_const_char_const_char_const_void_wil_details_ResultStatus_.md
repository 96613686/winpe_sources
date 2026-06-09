# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004d78`
- end: `0x180005003`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000499c`

## callees

- `0x180002f34`
- `0x180004d78`
- `0x180006374`
- `0x180006c2c`
- `0x180007470`
- `0x18000852c`
- `0x1800556e0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e31`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004fca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004fca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004f3a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004f3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
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
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180004d78  mov     [rsp-8+arg_18], rbx
0x180004d7d  push    rbp
0x180004d7e  push    rsi
0x180004d7f  push    rdi
0x180004d80  push    r12
0x180004d82  push    r13
0x180004d84  push    r14
0x180004d86  push    r15
0x180004d88  lea     rbp, [rsp-13C0h]
0x180004d90  mov     eax, 14C0h
0x180004d95  call    _alloca_probe
0x180004d9a  sub     rsp, rax
0x180004d9d  mov     r14, r8
0x180004da0  mov     esi, edx
0x180004da2  mov     rdi, rcx
0x180004da5  mov     r15, [rbp+13F0h+arg_28]
0x180004dac  xor     edx, edx; Val
0x180004dae  mov     r8d, 98h; Size
0x180004db4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004db9  call    memset_0
0x180004dbe  nop
0x180004dbf  xor     r13d, r13d
0x180004dc2  mov     [rbp+13F0h+OutputString], r13w
0x180004dca  mov     [rbp+13F0h+var_1430], r13b
0x180004dce  mov     rbx, [rbp+13F0h+arg_30]
0x180004dd5  mov     ecx, [rbx]; this
0x180004dd7  mov     [rsp+14F0h+var_14C8], ecx
0x180004ddb  mov     eax, [rbx+4]
0x180004dde  mov     [rsp+14F0h+var_14C4], eax
0x180004de2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004de7  mov     r12d, eax
0x180004dea  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180004df2  mov     ecx, r13d
0x180004df5  lea     eax, [r13+8]
0x180004df9  cmp     dword ptr [rbx+8], 1
0x180004dfd  cmovz   ecx, eax
0x180004e00  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004e04  lea     ecx, [rax-7]
0x180004e07  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004e0f  inc     ecx
0x180004e11  mov     [rsp+14F0h+var_14C0], ecx
0x180004e15  mov     rcx, [rbp+13F0h+arg_38]
0x180004e1c  test    rcx, rcx
0x180004e1f  jz      short loc_180004E2C
0x180004e21  cmp     [rcx], r13w
0x180004e25  mov     [rsp+14F0h+var_14B8], rcx
0x180004e2a  jnz     short loc_180004E31
0x180004e2c  mov     [rsp+14F0h+var_14B8], r13
0x180004e31  call    cs:__imp_GetCurrentThreadId
0x180004e38  nop     dword ptr [rax+rax+00h]
0x180004e3d  mov     [rsp+14F0h+var_14B0], eax
0x180004e41  mov     [rsp+14F0h+var_1498], r14
0x180004e46  mov     [rsp+14F0h+var_1490], esi
0x180004e4a  mov     [rsp+14F0h+var_148C], r12d
0x180004e4f  mov     [rsp+14F0h+var_14A8], r13
0x180004e54  mov     [rsp+14F0h+var_14A0], r13
0x180004e59  mov     [rbp+13F0h+var_1448], r15
0x180004e5d  mov     [rbp+13F0h+var_1440], rdi
0x180004e61  mov     [rsp+14F0h+var_1488], r13
0x180004e66  xorps   xmm0, xmm0
0x180004e69  xor     eax, eax
0x180004e6b  movups  [rbp+13F0h+var_1468], xmm0
0x180004e6f  mov     [rbp+13F0h+var_1458], rax
0x180004e73  xorps   xmm1, xmm1
0x180004e76  movups  [rsp+14F0h+var_1480], xmm1
0x180004e7b  mov     [rbp+13F0h+var_1470], rax
0x180004e7f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004e86  test    rax, rax
0x180004e89  jz      short loc_180004E96
0x180004e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e90  mov     [rbp+13F0h+var_1450], rax
0x180004e94  jmp     short loc_180004E9A
0x180004e96  mov     [rbp+13F0h+var_1450], r13
0x180004e9a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004ea1  test    rax, rax
0x180004ea4  jz      short loc_180004EB0
0x180004ea6  lea     rcx, [rsp+14F0h+var_14D0]
0x180004eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004eb7  test    rax, rax
0x180004eba  jz      short loc_180004ED0
0x180004ebc  mov     r8d, 400h
0x180004ec2  lea     rdx, [rbp+13F0h+var_1430]
0x180004ec6  lea     rcx, [rsp+14F0h+var_14D0]
0x180004ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ed7  test    rax, rax
0x180004eda  jz      short loc_180004EE6
0x180004edc  lea     rcx, [rsp+14F0h+var_14D0]
0x180004ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004eed  test    rax, rax
0x180004ef0  jz      short loc_180004F03
0x180004ef2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004ef7  jnz     short loc_180004F03
0x180004ef9  lea     rcx, [rsp+14F0h+var_14D0]
0x180004efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f03  cmp     [rsp+14F0h+var_14C8], r13d
0x180004f08  jl      short loc_180004F1C
0x180004f0a  mov     ecx, 8000FFFFh; this
0x180004f0f  mov     [rsp+14F0h+var_14C8], ecx
0x180004f13  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004f18  mov     [rsp+14F0h+var_14C4], eax
0x180004f1c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004f23  jnz     short loc_180004F4A
0x180004f25  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004f2c  test    rax, rax
0x180004f2f  jz      short loc_180004F3A
0x180004f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f36  test    al, al
0x180004f38  jmp     short loc_180004F48
0x180004f3a  call    cs:__imp_IsDebuggerPresent
0x180004f41  nop     dword ptr [rax+rax+00h]
0x180004f46  test    eax, eax
0x180004f48  jz      short loc_180004F51
0x180004f4a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004f4f  jz      short loc_180004F77
0x180004f51  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f58  test    rax, rax
0x180004f5b  jz      short loc_180004FD6
0x180004f5d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004f64  jnz     short loc_180004FD6
0x180004f66  xor     r8d, r8d
0x180004f69  xor     edx, edx
0x180004f6b  lea     rcx, [rsp+14F0h+var_14D0]
0x180004f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f75  jmp     short loc_180004FD6
0x180004f77  mov     ebx, 800h
0x180004f7c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f83  test    rax, rax
0x180004f86  jz      short loc_180004FA5
0x180004f88  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004f8f  jnz     short loc_180004FA5
0x180004f91  mov     r8d, ebx
0x180004f94  lea     rdx, [rbp+13F0h+OutputString]
0x180004f9b  lea     rcx, [rsp+14F0h+var_14D0]
0x180004fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa5  cmp     [rbp+13F0h+OutputString], r13w
0x180004fad  jnz     short loc_180004FC3
0x180004faf  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004fb4  mov     rdx, rbx; unsigned __int16 *
0x180004fb7  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004fbe  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004fc3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004fca  call    cs:__imp_OutputDebugStringW
0x180004fd1  nop     dword ptr [rax+rax+00h]
0x180004fd6  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004fdb  jnz     short loc_180004FE6
0x180004fdd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180004fe4  jz      short loc_180004FF8
0x180004fe6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004fed  test    rax, rax
0x180004ff0  jz      short loc_180004FF8
0x180004ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff7  nop
0x180004ff8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004ffd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
