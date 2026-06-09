# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800043b8`
- end: `0x180004631`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004128`

## callees

- `0x1800021f4`
- `0x180002704`
- `0x180002aec`
- `0x180002e90`
- `0x1800043b8`
- `0x18000b1bc`
- `0x18000d740`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004471`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004471`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045fe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004574`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004574`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v18, v16);
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
0x1800043b8  mov     [rsp-8+arg_18], rbx
0x1800043bd  push    rbp
0x1800043be  push    rsi
0x1800043bf  push    rdi
0x1800043c0  push    r12
0x1800043c2  push    r13
0x1800043c4  push    r14
0x1800043c6  push    r15
0x1800043c8  lea     rbp, [rsp-13C0h]
0x1800043d0  mov     eax, 14C0h
0x1800043d5  call    _alloca_probe
0x1800043da  sub     rsp, rax
0x1800043dd  mov     r14, r8
0x1800043e0  mov     esi, edx
0x1800043e2  mov     rdi, rcx
0x1800043e5  mov     r15, [rbp+13F0h+arg_28]
0x1800043ec  xor     edx, edx; Val
0x1800043ee  mov     r8d, 98h; Size
0x1800043f4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800043f9  call    memset_0
0x1800043fe  nop
0x1800043ff  xor     r13d, r13d
0x180004402  mov     [rbp+13F0h+OutputString], r13w
0x18000440a  mov     [rbp+13F0h+var_1430], r13b
0x18000440e  mov     rbx, [rbp+13F0h+arg_30]
0x180004415  mov     ecx, [rbx]; this
0x180004417  mov     [rsp+14F0h+var_14C8], ecx
0x18000441b  mov     eax, [rbx+4]
0x18000441e  mov     [rsp+14F0h+var_14C4], eax
0x180004422  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004427  mov     r12d, eax
0x18000442a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180004432  mov     ecx, r13d
0x180004435  lea     eax, [r13+8]
0x180004439  cmp     dword ptr [rbx+8], 1
0x18000443d  cmovz   ecx, eax
0x180004440  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004444  lea     ecx, [rax-7]
0x180004447  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000444f  inc     ecx
0x180004451  mov     [rsp+14F0h+var_14C0], ecx
0x180004455  mov     rcx, [rbp+13F0h+arg_38]
0x18000445c  test    rcx, rcx
0x18000445f  jz      short loc_18000446C
0x180004461  cmp     [rcx], r13w
0x180004465  mov     [rsp+14F0h+var_14B8], rcx
0x18000446a  jnz     short loc_180004471
0x18000446c  mov     [rsp+14F0h+var_14B8], r13
0x180004471  call    cs:__imp_GetCurrentThreadId
0x180004477  mov     [rsp+14F0h+var_14B0], eax
0x18000447b  mov     [rsp+14F0h+var_1498], r14
0x180004480  mov     [rsp+14F0h+var_1490], esi
0x180004484  mov     [rsp+14F0h+var_148C], r12d
0x180004489  mov     [rsp+14F0h+var_14A8], r13
0x18000448e  mov     [rsp+14F0h+var_14A0], r13
0x180004493  mov     [rbp+13F0h+var_1448], r15
0x180004497  mov     [rbp+13F0h+var_1440], rdi
0x18000449b  mov     [rsp+14F0h+var_1488], r13
0x1800044a0  xorps   xmm0, xmm0
0x1800044a3  xor     eax, eax
0x1800044a5  movups  [rbp+13F0h+var_1468], xmm0
0x1800044a9  mov     [rbp+13F0h+var_1458], rax
0x1800044ad  xorps   xmm1, xmm1
0x1800044b0  movups  [rsp+14F0h+var_1480], xmm1
0x1800044b5  mov     [rbp+13F0h+var_1470], rax
0x1800044b9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800044c0  test    rax, rax
0x1800044c3  jz      short loc_1800044D0
0x1800044c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ca  mov     [rbp+13F0h+var_1450], rax
0x1800044ce  jmp     short loc_1800044D4
0x1800044d0  mov     [rbp+13F0h+var_1450], r13
0x1800044d4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800044db  test    rax, rax
0x1800044de  jz      short loc_1800044EA
0x1800044e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800044e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ea  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800044f1  test    rax, rax
0x1800044f4  jz      short loc_18000450A
0x1800044f6  mov     r8d, 400h
0x1800044fc  lea     rdx, [rbp+13F0h+var_1430]
0x180004500  lea     rcx, [rsp+14F0h+var_14D0]
0x180004505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000450a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004511  test    rax, rax
0x180004514  jz      short loc_180004520
0x180004516  lea     rcx, [rsp+14F0h+var_14D0]
0x18000451b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004520  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004527  test    rax, rax
0x18000452a  jz      short loc_18000453D
0x18000452c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004531  jnz     short loc_18000453D
0x180004533  lea     rcx, [rsp+14F0h+var_14D0]
0x180004538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000453d  cmp     [rsp+14F0h+var_14C8], r13d
0x180004542  jl      short loc_180004556
0x180004544  mov     ecx, 8000FFFFh; this
0x180004549  mov     [rsp+14F0h+var_14C8], ecx
0x18000454d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004552  mov     [rsp+14F0h+var_14C4], eax
0x180004556  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000455d  jnz     short loc_18000457E
0x18000455f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004566  test    rax, rax
0x180004569  jz      short loc_180004574
0x18000456b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004570  test    al, al
0x180004572  jmp     short loc_18000457C
0x180004574  call    cs:__imp_IsDebuggerPresent
0x18000457a  test    eax, eax
0x18000457c  jz      short loc_180004585
0x18000457e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004583  jz      short loc_1800045AB
0x180004585  mov     rax, cs:g_pfnResultLoggingCallback
0x18000458c  test    rax, rax
0x18000458f  jz      short loc_180004604
0x180004591  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004598  jnz     short loc_180004604
0x18000459a  xor     r8d, r8d
0x18000459d  xor     edx, edx
0x18000459f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800045a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a9  jmp     short loc_180004604
0x1800045ab  mov     ebx, 800h
0x1800045b0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800045b7  test    rax, rax
0x1800045ba  jz      short loc_1800045D9
0x1800045bc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800045c3  jnz     short loc_1800045D9
0x1800045c5  mov     r8d, ebx
0x1800045c8  lea     rdx, [rbp+13F0h+OutputString]
0x1800045cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800045d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045d9  cmp     [rbp+13F0h+OutputString], r13w
0x1800045e1  jnz     short loc_1800045F7
0x1800045e3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800045e8  mov     rdx, rbx; wchar_t *
0x1800045eb  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800045f2  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800045f7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800045fe  call    cs:__imp_OutputDebugStringW
0x180004604  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004609  jnz     short loc_180004614
0x18000460b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180004612  jz      short loc_180004626
0x180004614  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000461b  test    rax, rax
0x18000461e  jz      short loc_180004626
0x180004620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004625  nop
0x180004626  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000462b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
