# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800044e4`
- end: `0x18000475d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004060`

## callees

- `0x180003384`
- `0x1800044e4`
- `0x180009274`
- `0x180009b28`
- `0x18000aca0`
- `0x18000e140`
- `0x180070720`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000459d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000459d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000472a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000472a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800046a0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800046a0`

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
0x1800044e4  mov     [rsp-8+arg_18], rbx
0x1800044e9  push    rbp
0x1800044ea  push    rsi
0x1800044eb  push    rdi
0x1800044ec  push    r12
0x1800044ee  push    r13
0x1800044f0  push    r14
0x1800044f2  push    r15
0x1800044f4  lea     rbp, [rsp-13C0h]
0x1800044fc  mov     eax, 14C0h
0x180004501  call    _alloca_probe
0x180004506  sub     rsp, rax
0x180004509  mov     r14, r8
0x18000450c  mov     esi, edx
0x18000450e  mov     rdi, rcx
0x180004511  mov     r15, [rbp+13F0h+arg_28]
0x180004518  xor     edx, edx; Val
0x18000451a  mov     r8d, 98h; Size
0x180004520  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004525  call    memset_0
0x18000452a  nop
0x18000452b  xor     r13d, r13d
0x18000452e  mov     [rbp+13F0h+OutputString], r13w
0x180004536  mov     [rbp+13F0h+var_1430], r13b
0x18000453a  mov     rbx, [rbp+13F0h+arg_30]
0x180004541  mov     ecx, [rbx]; this
0x180004543  mov     [rsp+14F0h+var_14C8], ecx
0x180004547  mov     eax, [rbx+4]
0x18000454a  mov     [rsp+14F0h+var_14C4], eax
0x18000454e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004553  mov     r12d, eax
0x180004556  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000455e  mov     ecx, r13d
0x180004561  lea     eax, [r13+8]
0x180004565  cmp     dword ptr [rbx+8], 1
0x180004569  cmovz   ecx, eax
0x18000456c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004570  lea     ecx, [rax-7]
0x180004573  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000457b  inc     ecx
0x18000457d  mov     [rsp+14F0h+var_14C0], ecx
0x180004581  mov     rcx, [rbp+13F0h+arg_38]
0x180004588  test    rcx, rcx
0x18000458b  jz      short loc_180004598
0x18000458d  cmp     [rcx], r13w
0x180004591  mov     [rsp+14F0h+var_14B8], rcx
0x180004596  jnz     short loc_18000459D
0x180004598  mov     [rsp+14F0h+var_14B8], r13
0x18000459d  call    cs:__imp_GetCurrentThreadId
0x1800045a3  mov     [rsp+14F0h+var_14B0], eax
0x1800045a7  mov     [rsp+14F0h+var_1498], r14
0x1800045ac  mov     [rsp+14F0h+var_1490], esi
0x1800045b0  mov     [rsp+14F0h+var_148C], r12d
0x1800045b5  mov     [rsp+14F0h+var_14A8], r13
0x1800045ba  mov     [rsp+14F0h+var_14A0], r13
0x1800045bf  mov     [rbp+13F0h+var_1448], r15
0x1800045c3  mov     [rbp+13F0h+var_1440], rdi
0x1800045c7  mov     [rsp+14F0h+var_1488], r13
0x1800045cc  xorps   xmm0, xmm0
0x1800045cf  xor     eax, eax
0x1800045d1  movups  [rbp+13F0h+var_1468], xmm0
0x1800045d5  mov     [rbp+13F0h+var_1458], rax
0x1800045d9  xorps   xmm1, xmm1
0x1800045dc  movups  [rsp+14F0h+var_1480], xmm1
0x1800045e1  mov     [rbp+13F0h+var_1470], rax
0x1800045e5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800045ec  test    rax, rax
0x1800045ef  jz      short loc_1800045FC
0x1800045f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045f6  mov     [rbp+13F0h+var_1450], rax
0x1800045fa  jmp     short loc_180004600
0x1800045fc  mov     [rbp+13F0h+var_1450], r13
0x180004600  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004607  test    rax, rax
0x18000460a  jz      short loc_180004616
0x18000460c  lea     rcx, [rsp+14F0h+var_14D0]
0x180004611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004616  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000461d  test    rax, rax
0x180004620  jz      short loc_180004636
0x180004622  mov     r8d, 400h
0x180004628  lea     rdx, [rbp+13F0h+var_1430]
0x18000462c  lea     rcx, [rsp+14F0h+var_14D0]
0x180004631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004636  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000463d  test    rax, rax
0x180004640  jz      short loc_18000464C
0x180004642  lea     rcx, [rsp+14F0h+var_14D0]
0x180004647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000464c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004653  test    rax, rax
0x180004656  jz      short loc_180004669
0x180004658  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000465d  jnz     short loc_180004669
0x18000465f  lea     rcx, [rsp+14F0h+var_14D0]
0x180004664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004669  cmp     [rsp+14F0h+var_14C8], r13d
0x18000466e  jl      short loc_180004682
0x180004670  mov     ecx, 8000FFFFh; this
0x180004675  mov     [rsp+14F0h+var_14C8], ecx
0x180004679  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000467e  mov     [rsp+14F0h+var_14C4], eax
0x180004682  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004689  jnz     short loc_1800046AA
0x18000468b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004692  test    rax, rax
0x180004695  jz      short loc_1800046A0
0x180004697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000469c  test    al, al
0x18000469e  jmp     short loc_1800046A8
0x1800046a0  call    cs:__imp_IsDebuggerPresent
0x1800046a6  test    eax, eax
0x1800046a8  jz      short loc_1800046B1
0x1800046aa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800046af  jz      short loc_1800046D7
0x1800046b1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046b8  test    rax, rax
0x1800046bb  jz      short loc_180004730
0x1800046bd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800046c4  jnz     short loc_180004730
0x1800046c6  xor     r8d, r8d
0x1800046c9  xor     edx, edx
0x1800046cb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800046d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d5  jmp     short loc_180004730
0x1800046d7  mov     ebx, 800h
0x1800046dc  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046e3  test    rax, rax
0x1800046e6  jz      short loc_180004705
0x1800046e8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800046ef  jnz     short loc_180004705
0x1800046f1  mov     r8d, ebx
0x1800046f4  lea     rdx, [rbp+13F0h+OutputString]
0x1800046fb  lea     rcx, [rsp+14F0h+var_14D0]
0x180004700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004705  cmp     [rbp+13F0h+OutputString], r13w
0x18000470d  jnz     short loc_180004723
0x18000470f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004714  mov     rdx, rbx; unsigned __int16 *
0x180004717  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000471e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004723  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000472a  call    cs:__imp_OutputDebugStringW
0x180004730  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004735  jnz     short loc_180004740
0x180004737  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000473e  jz      short loc_180004752
0x180004740  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004747  test    rax, rax
0x18000474a  jz      short loc_180004752
0x18000474c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004751  nop
0x180004752  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004757  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
