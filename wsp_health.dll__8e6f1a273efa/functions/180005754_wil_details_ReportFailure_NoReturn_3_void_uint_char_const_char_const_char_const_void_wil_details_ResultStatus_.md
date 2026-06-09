# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180005754`
- end: `0x1800059c8`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005520`

## callees

- `0x1800035b4`
- `0x180005754`
- `0x180007494`
- `0x180007d7c`
- `0x180008d50`
- `0x18000a62c`
- `0x1800865f0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057f6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800058ff`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800058ff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000598f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000598f`

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
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (__int64)&v17, v15);
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
0x180005754  mov     [rsp-8+arg_18], rbx
0x180005759  push    rbp
0x18000575a  push    rsi
0x18000575b  push    rdi
0x18000575c  push    r12
0x18000575e  push    r13
0x180005760  push    r14
0x180005762  push    r15
0x180005764  lea     rbp, [rsp-13C0h]
0x18000576c  mov     eax, 14C0h
0x180005771  call    _alloca_probe
0x180005776  sub     rsp, rax
0x180005779  mov     r15, r8
0x18000577c  mov     r14d, edx
0x18000577f  mov     r12, rcx
0x180005782  mov     rsi, [rbp+13F0h+arg_28]
0x180005789  xor     edx, edx; Val
0x18000578b  mov     r8d, 98h; Size
0x180005791  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005796  call    memset_0
0x18000579b  nop
0x18000579c  xor     r13d, r13d
0x18000579f  mov     [rbp+13F0h+OutputString], r13w
0x1800057a7  mov     [rbp+13F0h+var_1430], r13b
0x1800057ab  mov     rbx, [rbp+13F0h+arg_30]
0x1800057b2  mov     ecx, [rbx]; this
0x1800057b4  mov     [rsp+14F0h+var_14C8], ecx
0x1800057b8  mov     eax, [rbx+4]
0x1800057bb  mov     [rsp+14F0h+var_14C4], eax
0x1800057bf  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800057c4  mov     edi, eax
0x1800057c6  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800057ce  mov     ecx, r13d
0x1800057d1  lea     eax, [r13+8]
0x1800057d5  cmp     dword ptr [rbx+8], 1
0x1800057d9  cmovz   ecx, eax
0x1800057dc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800057e0  lea     ecx, [rax-7]
0x1800057e3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800057eb  inc     ecx
0x1800057ed  mov     [rsp+14F0h+var_14C0], ecx
0x1800057f1  mov     [rsp+14F0h+var_14B8], r13
0x1800057f6  call    cs:__imp_GetCurrentThreadId
0x1800057fd  nop     dword ptr [rax+rax+00h]
0x180005802  mov     [rsp+14F0h+var_14B0], eax
0x180005806  mov     [rsp+14F0h+var_1498], r15
0x18000580b  mov     [rsp+14F0h+var_1490], r14d
0x180005810  mov     [rsp+14F0h+var_148C], edi
0x180005814  mov     [rsp+14F0h+var_14A8], r13
0x180005819  mov     [rsp+14F0h+var_14A0], r13
0x18000581e  mov     [rbp+13F0h+var_1448], rsi
0x180005822  mov     [rbp+13F0h+var_1440], r12
0x180005826  mov     [rsp+14F0h+var_1488], r13
0x18000582b  xorps   xmm0, xmm0
0x18000582e  xor     eax, eax
0x180005830  movups  [rbp+13F0h+var_1468], xmm0
0x180005834  mov     [rbp+13F0h+var_1458], rax
0x180005838  xorps   xmm1, xmm1
0x18000583b  movups  [rsp+14F0h+var_1480], xmm1
0x180005840  mov     [rbp+13F0h+var_1470], rax
0x180005844  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000584b  test    rax, rax
0x18000584e  jz      short loc_18000585B
0x180005850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005855  mov     [rbp+13F0h+var_1450], rax
0x180005859  jmp     short loc_18000585F
0x18000585b  mov     [rbp+13F0h+var_1450], r13
0x18000585f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005866  test    rax, rax
0x180005869  jz      short loc_180005875
0x18000586b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005875  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000587c  test    rax, rax
0x18000587f  jz      short loc_180005895
0x180005881  mov     r8d, 400h
0x180005887  lea     rdx, [rbp+13F0h+var_1430]
0x18000588b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005895  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000589c  test    rax, rax
0x18000589f  jz      short loc_1800058AB
0x1800058a1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800058a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800058b2  test    rax, rax
0x1800058b5  jz      short loc_1800058C8
0x1800058b7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800058bc  jnz     short loc_1800058C8
0x1800058be  lea     rcx, [rsp+14F0h+var_14D0]
0x1800058c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058c8  cmp     [rsp+14F0h+var_14C8], r13d
0x1800058cd  jl      short loc_1800058E1
0x1800058cf  mov     ecx, 8000FFFFh; this
0x1800058d4  mov     [rsp+14F0h+var_14C8], ecx
0x1800058d8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800058dd  mov     [rsp+14F0h+var_14C4], eax
0x1800058e1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800058e8  jnz     short loc_18000590F
0x1800058ea  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800058f1  test    rax, rax
0x1800058f4  jz      short loc_1800058FF
0x1800058f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058fb  test    al, al
0x1800058fd  jmp     short loc_18000590D
0x1800058ff  call    cs:__imp_IsDebuggerPresent
0x180005906  nop     dword ptr [rax+rax+00h]
0x18000590b  test    eax, eax
0x18000590d  jz      short loc_180005916
0x18000590f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005914  jz      short loc_18000593C
0x180005916  mov     rax, cs:g_pfnResultLoggingCallback
0x18000591d  test    rax, rax
0x180005920  jz      short loc_18000599B
0x180005922  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005929  jnz     short loc_18000599B
0x18000592b  xor     r8d, r8d
0x18000592e  xor     edx, edx
0x180005930  lea     rcx, [rsp+14F0h+var_14D0]
0x180005935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000593a  jmp     short loc_18000599B
0x18000593c  mov     ebx, 800h
0x180005941  mov     rax, cs:g_pfnResultLoggingCallback
0x180005948  test    rax, rax
0x18000594b  jz      short loc_18000596A
0x18000594d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005954  jnz     short loc_18000596A
0x180005956  mov     r8d, ebx
0x180005959  lea     rdx, [rbp+13F0h+OutputString]
0x180005960  lea     rcx, [rsp+14F0h+var_14D0]
0x180005965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000596a  cmp     [rbp+13F0h+OutputString], r13w
0x180005972  jnz     short loc_180005988
0x180005974  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005979  mov     rdx, rbx; wchar_t *
0x18000597c  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x180005983  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005988  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000598f  call    cs:__imp_OutputDebugStringW
0x180005996  nop     dword ptr [rax+rax+00h]
0x18000599b  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800059a0  jnz     short loc_1800059AB
0x1800059a2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800059a9  jz      short loc_1800059BD
0x1800059ab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800059b2  test    rax, rax
0x1800059b5  jz      short loc_1800059BD
0x1800059b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059bc  nop
0x1800059bd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800059c2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
