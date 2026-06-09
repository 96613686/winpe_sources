# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004704`
- end: `0x18000497d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004668`

## callees

- `0x180003da4`
- `0x180004704`
- `0x180005414`
- `0x1800056d0`
- `0x180005960`
- `0x18000626c`
- `0x1800265e0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047bd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000494a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000494a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048c0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048c0`

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
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x180004704  mov     [rsp-8+arg_18], rbx
0x180004709  push    rbp
0x18000470a  push    rsi
0x18000470b  push    rdi
0x18000470c  push    r12
0x18000470e  push    r13
0x180004710  push    r14
0x180004712  push    r15
0x180004714  lea     rbp, [rsp-13C0h]
0x18000471c  mov     eax, 14C0h
0x180004721  call    _alloca_probe
0x180004726  sub     rsp, rax
0x180004729  mov     r14, r8
0x18000472c  mov     esi, edx
0x18000472e  mov     rdi, rcx
0x180004731  mov     r15, [rbp+13F0h+arg_28]
0x180004738  xor     edx, edx; Val
0x18000473a  mov     r8d, 98h; Size
0x180004740  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004745  call    memset_0
0x18000474a  nop
0x18000474b  xor     r13d, r13d
0x18000474e  mov     [rbp+13F0h+OutputString], r13w
0x180004756  mov     [rbp+13F0h+var_1430], r13b
0x18000475a  mov     rbx, [rbp+13F0h+arg_30]
0x180004761  mov     ecx, [rbx]; this
0x180004763  mov     [rsp+14F0h+var_14C8], ecx
0x180004767  mov     eax, [rbx+4]
0x18000476a  mov     [rsp+14F0h+var_14C4], eax
0x18000476e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004773  mov     r12d, eax
0x180004776  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000477e  mov     ecx, r13d
0x180004781  lea     eax, [r13+8]
0x180004785  cmp     dword ptr [rbx+8], 1
0x180004789  cmovz   ecx, eax
0x18000478c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004790  lea     ecx, [rax-7]
0x180004793  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000479b  inc     ecx
0x18000479d  mov     [rsp+14F0h+var_14C0], ecx
0x1800047a1  mov     rcx, [rbp+13F0h+arg_38]
0x1800047a8  test    rcx, rcx
0x1800047ab  jz      short loc_1800047B8
0x1800047ad  cmp     [rcx], r13w
0x1800047b1  mov     [rsp+14F0h+var_14B8], rcx
0x1800047b6  jnz     short loc_1800047BD
0x1800047b8  mov     [rsp+14F0h+var_14B8], r13
0x1800047bd  call    cs:__imp_GetCurrentThreadId
0x1800047c3  mov     [rsp+14F0h+var_14B0], eax
0x1800047c7  mov     [rsp+14F0h+var_1498], r14
0x1800047cc  mov     [rsp+14F0h+var_1490], esi
0x1800047d0  mov     [rsp+14F0h+var_148C], r12d
0x1800047d5  mov     [rsp+14F0h+var_14A8], r13
0x1800047da  mov     [rsp+14F0h+var_14A0], r13
0x1800047df  mov     [rbp+13F0h+var_1448], r15
0x1800047e3  mov     [rbp+13F0h+var_1440], rdi
0x1800047e7  mov     [rsp+14F0h+var_1488], r13
0x1800047ec  xorps   xmm0, xmm0
0x1800047ef  xor     eax, eax
0x1800047f1  movups  [rbp+13F0h+var_1468], xmm0
0x1800047f5  mov     [rbp+13F0h+var_1458], rax
0x1800047f9  xorps   xmm1, xmm1
0x1800047fc  movups  [rsp+14F0h+var_1480], xmm1
0x180004801  mov     [rbp+13F0h+var_1470], rax
0x180004805  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000480c  test    rax, rax
0x18000480f  jz      short loc_18000481C
0x180004811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004816  mov     [rbp+13F0h+var_1450], rax
0x18000481a  jmp     short loc_180004820
0x18000481c  mov     [rbp+13F0h+var_1450], r13
0x180004820  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004827  test    rax, rax
0x18000482a  jz      short loc_180004836
0x18000482c  lea     rcx, [rsp+14F0h+var_14D0]
0x180004831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004836  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000483d  test    rax, rax
0x180004840  jz      short loc_180004856
0x180004842  mov     r8d, 400h
0x180004848  lea     rdx, [rbp+13F0h+var_1430]
0x18000484c  lea     rcx, [rsp+14F0h+var_14D0]
0x180004851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004856  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000485d  test    rax, rax
0x180004860  jz      short loc_18000486C
0x180004862  lea     rcx, [rsp+14F0h+var_14D0]
0x180004867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000486c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004873  test    rax, rax
0x180004876  jz      short loc_180004889
0x180004878  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000487d  jnz     short loc_180004889
0x18000487f  lea     rcx, [rsp+14F0h+var_14D0]
0x180004884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004889  cmp     [rsp+14F0h+var_14C8], r13d
0x18000488e  jl      short loc_1800048A2
0x180004890  mov     ecx, 8000FFFFh; this
0x180004895  mov     [rsp+14F0h+var_14C8], ecx
0x180004899  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000489e  mov     [rsp+14F0h+var_14C4], eax
0x1800048a2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800048a9  jnz     short loc_1800048CA
0x1800048ab  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800048b2  test    rax, rax
0x1800048b5  jz      short loc_1800048C0
0x1800048b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048bc  test    al, al
0x1800048be  jmp     short loc_1800048C8
0x1800048c0  call    cs:__imp_IsDebuggerPresent
0x1800048c6  test    eax, eax
0x1800048c8  jz      short loc_1800048D1
0x1800048ca  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800048cf  jz      short loc_1800048F7
0x1800048d1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800048d8  test    rax, rax
0x1800048db  jz      short loc_180004950
0x1800048dd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800048e4  jnz     short loc_180004950
0x1800048e6  xor     r8d, r8d
0x1800048e9  xor     edx, edx
0x1800048eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800048f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048f5  jmp     short loc_180004950
0x1800048f7  mov     ebx, 800h
0x1800048fc  mov     rax, cs:g_pfnResultLoggingCallback
0x180004903  test    rax, rax
0x180004906  jz      short loc_180004925
0x180004908  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000490f  jnz     short loc_180004925
0x180004911  mov     r8d, ebx
0x180004914  lea     rdx, [rbp+13F0h+OutputString]
0x18000491b  lea     rcx, [rsp+14F0h+var_14D0]
0x180004920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004925  cmp     [rbp+13F0h+OutputString], r13w
0x18000492d  jnz     short loc_180004943
0x18000492f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004934  mov     rdx, rbx; unsigned __int16 *
0x180004937  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000493e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004943  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000494a  call    cs:__imp_OutputDebugStringW
0x180004950  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004955  jnz     short loc_180004960
0x180004957  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000495e  jz      short loc_180004972
0x180004960  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004967  test    rax, rax
0x18000496a  jz      short loc_180004972
0x18000496c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004971  nop
0x180004972  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004977  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
