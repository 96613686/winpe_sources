# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000569c`
- end: `0x1800058fe`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005468`

## callees

- `0x180003514`
- `0x18000569c`
- `0x180007224`
- `0x180007aa4`
- `0x180008a10`
- `0x18000a2f0`
- `0x1800841e0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000573e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000573e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005841`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005841`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800058cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800058cb`

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
0x18000569c  mov     [rsp-8+arg_18], rbx
0x1800056a1  push    rbp
0x1800056a2  push    rsi
0x1800056a3  push    rdi
0x1800056a4  push    r12
0x1800056a6  push    r13
0x1800056a8  push    r14
0x1800056aa  push    r15
0x1800056ac  lea     rbp, [rsp-13C0h]
0x1800056b4  mov     eax, 14C0h
0x1800056b9  call    _alloca_probe
0x1800056be  sub     rsp, rax
0x1800056c1  mov     r15, r8
0x1800056c4  mov     r14d, edx
0x1800056c7  mov     r12, rcx
0x1800056ca  mov     rsi, [rbp+13F0h+arg_28]
0x1800056d1  xor     edx, edx; Val
0x1800056d3  mov     r8d, 98h; Size
0x1800056d9  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800056de  call    memset_0
0x1800056e3  nop
0x1800056e4  xor     r13d, r13d
0x1800056e7  mov     [rbp+13F0h+OutputString], r13w
0x1800056ef  mov     [rbp+13F0h+var_1430], r13b
0x1800056f3  mov     rbx, [rbp+13F0h+arg_30]
0x1800056fa  mov     ecx, [rbx]; this
0x1800056fc  mov     [rsp+14F0h+var_14C8], ecx
0x180005700  mov     eax, [rbx+4]
0x180005703  mov     [rsp+14F0h+var_14C4], eax
0x180005707  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000570c  mov     edi, eax
0x18000570e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180005716  mov     ecx, r13d
0x180005719  lea     eax, [r13+8]
0x18000571d  cmp     dword ptr [rbx+8], 1
0x180005721  cmovz   ecx, eax
0x180005724  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005728  lea     ecx, [rax-7]
0x18000572b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005733  inc     ecx
0x180005735  mov     [rsp+14F0h+var_14C0], ecx
0x180005739  mov     [rsp+14F0h+var_14B8], r13
0x18000573e  call    cs:__imp_GetCurrentThreadId
0x180005744  mov     [rsp+14F0h+var_14B0], eax
0x180005748  mov     [rsp+14F0h+var_1498], r15
0x18000574d  mov     [rsp+14F0h+var_1490], r14d
0x180005752  mov     [rsp+14F0h+var_148C], edi
0x180005756  mov     [rsp+14F0h+var_14A8], r13
0x18000575b  mov     [rsp+14F0h+var_14A0], r13
0x180005760  mov     [rbp+13F0h+var_1448], rsi
0x180005764  mov     [rbp+13F0h+var_1440], r12
0x180005768  mov     [rsp+14F0h+var_1488], r13
0x18000576d  xorps   xmm0, xmm0
0x180005770  xor     eax, eax
0x180005772  movups  [rbp+13F0h+var_1468], xmm0
0x180005776  mov     [rbp+13F0h+var_1458], rax
0x18000577a  xorps   xmm1, xmm1
0x18000577d  movups  [rsp+14F0h+var_1480], xmm1
0x180005782  mov     [rbp+13F0h+var_1470], rax
0x180005786  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000578d  test    rax, rax
0x180005790  jz      short loc_18000579D
0x180005792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005797  mov     [rbp+13F0h+var_1450], rax
0x18000579b  jmp     short loc_1800057A1
0x18000579d  mov     [rbp+13F0h+var_1450], r13
0x1800057a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800057a8  test    rax, rax
0x1800057ab  jz      short loc_1800057B7
0x1800057ad  lea     rcx, [rsp+14F0h+var_14D0]
0x1800057b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800057be  test    rax, rax
0x1800057c1  jz      short loc_1800057D7
0x1800057c3  mov     r8d, 400h
0x1800057c9  lea     rdx, [rbp+13F0h+var_1430]
0x1800057cd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800057d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800057de  test    rax, rax
0x1800057e1  jz      short loc_1800057ED
0x1800057e3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800057e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ed  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800057f4  test    rax, rax
0x1800057f7  jz      short loc_18000580A
0x1800057f9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800057fe  jnz     short loc_18000580A
0x180005800  lea     rcx, [rsp+14F0h+var_14D0]
0x180005805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000580a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000580f  jl      short loc_180005823
0x180005811  mov     ecx, 8000FFFFh; this
0x180005816  mov     [rsp+14F0h+var_14C8], ecx
0x18000581a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000581f  mov     [rsp+14F0h+var_14C4], eax
0x180005823  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000582a  jnz     short loc_18000584B
0x18000582c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005833  test    rax, rax
0x180005836  jz      short loc_180005841
0x180005838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000583d  test    al, al
0x18000583f  jmp     short loc_180005849
0x180005841  call    cs:__imp_IsDebuggerPresent
0x180005847  test    eax, eax
0x180005849  jz      short loc_180005852
0x18000584b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005850  jz      short loc_180005878
0x180005852  mov     rax, cs:g_pfnResultLoggingCallback
0x180005859  test    rax, rax
0x18000585c  jz      short loc_1800058D1
0x18000585e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005865  jnz     short loc_1800058D1
0x180005867  xor     r8d, r8d
0x18000586a  xor     edx, edx
0x18000586c  lea     rcx, [rsp+14F0h+var_14D0]
0x180005871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005876  jmp     short loc_1800058D1
0x180005878  mov     ebx, 800h
0x18000587d  mov     rax, cs:g_pfnResultLoggingCallback
0x180005884  test    rax, rax
0x180005887  jz      short loc_1800058A6
0x180005889  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005890  jnz     short loc_1800058A6
0x180005892  mov     r8d, ebx
0x180005895  lea     rdx, [rbp+13F0h+OutputString]
0x18000589c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800058a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a6  cmp     [rbp+13F0h+OutputString], r13w
0x1800058ae  jnz     short loc_1800058C4
0x1800058b0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800058b5  mov     rdx, rbx; wchar_t *
0x1800058b8  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x1800058bf  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800058c4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800058cb  call    cs:__imp_OutputDebugStringW
0x1800058d1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800058d6  jnz     short loc_1800058E1
0x1800058d8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800058df  jz      short loc_1800058F3
0x1800058e1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800058e8  test    rax, rax
0x1800058eb  jz      short loc_1800058F3
0x1800058ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f2  nop
0x1800058f3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800058f8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
