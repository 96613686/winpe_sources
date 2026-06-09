# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000551c`
- end: `0x18000577e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800052e8`

## callees

- `0x180003498`
- `0x18000551c`
- `0x180007344`
- `0x180007bc4`
- `0x180008b30`
- `0x18000a410`
- `0x180099f30`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055be`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000574b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000574b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800056c1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800056c1`

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
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
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
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
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
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x18000551c  mov     [rsp-8+arg_18], rbx
0x180005521  push    rbp
0x180005522  push    rsi
0x180005523  push    rdi
0x180005524  push    r12
0x180005526  push    r13
0x180005528  push    r14
0x18000552a  push    r15
0x18000552c  lea     rbp, [rsp-13C0h]
0x180005534  mov     eax, 14C0h
0x180005539  call    _alloca_probe
0x18000553e  sub     rsp, rax
0x180005541  mov     r15, r8
0x180005544  mov     r14d, edx
0x180005547  mov     r12, rcx
0x18000554a  mov     rsi, [rbp+13F0h+arg_28]
0x180005551  xor     edx, edx; Val
0x180005553  mov     r8d, 98h; Size
0x180005559  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000555e  call    memset_0
0x180005563  nop
0x180005564  xor     r13d, r13d
0x180005567  mov     [rbp+13F0h+OutputString], r13w
0x18000556f  mov     [rbp+13F0h+var_1430], r13b
0x180005573  mov     rbx, [rbp+13F0h+arg_30]
0x18000557a  mov     ecx, [rbx]; this
0x18000557c  mov     [rsp+14F0h+var_14C8], ecx
0x180005580  mov     eax, [rbx+4]
0x180005583  mov     [rsp+14F0h+var_14C4], eax
0x180005587  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000558c  mov     edi, eax
0x18000558e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180005596  mov     ecx, r13d
0x180005599  lea     eax, [r13+8]
0x18000559d  cmp     dword ptr [rbx+8], 1
0x1800055a1  cmovz   ecx, eax
0x1800055a4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800055a8  lea     ecx, [rax-7]
0x1800055ab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800055b3  inc     ecx
0x1800055b5  mov     [rsp+14F0h+var_14C0], ecx
0x1800055b9  mov     [rsp+14F0h+var_14B8], r13
0x1800055be  call    cs:__imp_GetCurrentThreadId
0x1800055c4  mov     [rsp+14F0h+var_14B0], eax
0x1800055c8  mov     [rsp+14F0h+var_1498], r15
0x1800055cd  mov     [rsp+14F0h+var_1490], r14d
0x1800055d2  mov     [rsp+14F0h+var_148C], edi
0x1800055d6  mov     [rsp+14F0h+var_14A8], r13
0x1800055db  mov     [rsp+14F0h+var_14A0], r13
0x1800055e0  mov     [rbp+13F0h+var_1448], rsi
0x1800055e4  mov     [rbp+13F0h+var_1440], r12
0x1800055e8  mov     [rsp+14F0h+var_1488], r13
0x1800055ed  xorps   xmm0, xmm0
0x1800055f0  xor     eax, eax
0x1800055f2  movups  [rbp+13F0h+var_1468], xmm0
0x1800055f6  mov     [rbp+13F0h+var_1458], rax
0x1800055fa  xorps   xmm1, xmm1
0x1800055fd  movups  [rsp+14F0h+var_1480], xmm1
0x180005602  mov     [rbp+13F0h+var_1470], rax
0x180005606  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000560d  test    rax, rax
0x180005610  jz      short loc_18000561D
0x180005612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005617  mov     [rbp+13F0h+var_1450], rax
0x18000561b  jmp     short loc_180005621
0x18000561d  mov     [rbp+13F0h+var_1450], r13
0x180005621  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005628  test    rax, rax
0x18000562b  jz      short loc_180005637
0x18000562d  lea     rcx, [rsp+14F0h+var_14D0]
0x180005632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005637  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000563e  test    rax, rax
0x180005641  jz      short loc_180005657
0x180005643  mov     r8d, 400h
0x180005649  lea     rdx, [rbp+13F0h+var_1430]
0x18000564d  lea     rcx, [rsp+14F0h+var_14D0]
0x180005652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005657  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000565e  test    rax, rax
0x180005661  jz      short loc_18000566D
0x180005663  lea     rcx, [rsp+14F0h+var_14D0]
0x180005668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000566d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005674  test    rax, rax
0x180005677  jz      short loc_18000568A
0x180005679  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000567e  jnz     short loc_18000568A
0x180005680  lea     rcx, [rsp+14F0h+var_14D0]
0x180005685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000568a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000568f  jl      short loc_1800056A3
0x180005691  mov     ecx, 8000FFFFh; this
0x180005696  mov     [rsp+14F0h+var_14C8], ecx
0x18000569a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000569f  mov     [rsp+14F0h+var_14C4], eax
0x1800056a3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800056aa  jnz     short loc_1800056CB
0x1800056ac  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800056b3  test    rax, rax
0x1800056b6  jz      short loc_1800056C1
0x1800056b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056bd  test    al, al
0x1800056bf  jmp     short loc_1800056C9
0x1800056c1  call    cs:__imp_IsDebuggerPresent
0x1800056c7  test    eax, eax
0x1800056c9  jz      short loc_1800056D2
0x1800056cb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800056d0  jz      short loc_1800056F8
0x1800056d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056d9  test    rax, rax
0x1800056dc  jz      short loc_180005751
0x1800056de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800056e5  jnz     short loc_180005751
0x1800056e7  xor     r8d, r8d
0x1800056ea  xor     edx, edx
0x1800056ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1800056f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f6  jmp     short loc_180005751
0x1800056f8  mov     ebx, 800h
0x1800056fd  mov     rax, cs:g_pfnResultLoggingCallback
0x180005704  test    rax, rax
0x180005707  jz      short loc_180005726
0x180005709  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005710  jnz     short loc_180005726
0x180005712  mov     r8d, ebx
0x180005715  lea     rdx, [rbp+13F0h+OutputString]
0x18000571c  lea     rcx, [rsp+14F0h+var_14D0]
0x180005721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005726  cmp     [rbp+13F0h+OutputString], r13w
0x18000572e  jnz     short loc_180005744
0x180005730  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005735  mov     rdx, rbx; wchar_t *
0x180005738  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x18000573f  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005744  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000574b  call    cs:__imp_OutputDebugStringW
0x180005751  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005756  jnz     short loc_180005761
0x180005758  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000575f  jz      short loc_180005773
0x180005761  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005768  test    rax, rax
0x18000576b  jz      short loc_180005773
0x18000576d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005772  nop
0x180005773  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005778  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
