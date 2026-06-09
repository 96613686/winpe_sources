# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000b960`
- end: `0x18000bbe2`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000a99c`

## callees

- `0x1800091d4`
- `0x1800096a0`
- `0x1800098e0`
- `0x18000a8ec`
- `0x18000b960`
- `0x18002fda9`
- `0x1800369a0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba19`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bbaf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bbaf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bb1d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bb1d`

## pseudocode

```c
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
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v17; // r9
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
  if ( !a8 || (v14 = *a8 == 0, v23 = a8, v14) )
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
    ModuleName = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
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
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v19 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
  wil::details::WilFailFast((wil::details *)&v18, v15);
}

```

## disassembly

```asm
0x18000b960  mov     [rsp-8+arg_18], rbx
0x18000b965  push    rbp
0x18000b966  push    rsi
0x18000b967  push    rdi
0x18000b968  push    r12
0x18000b96a  push    r13
0x18000b96c  push    r14
0x18000b96e  push    r15
0x18000b970  lea     rbp, [rsp-13C0h]
0x18000b978  mov     eax, 14C0h
0x18000b97d  call    _alloca_probe
0x18000b982  sub     rsp, rax
0x18000b985  mov     r14, r8
0x18000b988  mov     esi, edx
0x18000b98a  mov     rdi, rcx
0x18000b98d  mov     r15, [rbp+13F0h+arg_28]
0x18000b994  xor     edx, edx; Val
0x18000b996  mov     r8d, 98h; Size
0x18000b99c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000b9a1  call    memset_0
0x18000b9a6  nop
0x18000b9a7  xor     r13d, r13d
0x18000b9aa  mov     [rbp+13F0h+OutputString], r13w
0x18000b9b2  mov     [rbp+13F0h+var_1430], r13b
0x18000b9b6  mov     rbx, [rbp+13F0h+arg_30]
0x18000b9bd  mov     ecx, [rbx]; this
0x18000b9bf  mov     [rsp+14F0h+var_14C8], ecx
0x18000b9c3  mov     eax, [rbx+4]
0x18000b9c6  mov     [rsp+14F0h+var_14C4], eax
0x18000b9ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000b9cf  mov     r12d, eax
0x18000b9d2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000b9da  mov     ecx, r13d
0x18000b9dd  lea     eax, [r13+8]
0x18000b9e1  cmp     dword ptr [rbx+8], 1
0x18000b9e5  cmovz   ecx, eax
0x18000b9e8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000b9ec  lea     ecx, [rax-7]
0x18000b9ef  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b9f7  inc     ecx
0x18000b9f9  mov     [rsp+14F0h+var_14C0], ecx
0x18000b9fd  mov     rcx, [rbp+13F0h+arg_38]
0x18000ba04  test    rcx, rcx
0x18000ba07  jz      short loc_18000BA14
0x18000ba09  cmp     [rcx], r13w
0x18000ba0d  mov     [rsp+14F0h+var_14B8], rcx
0x18000ba12  jnz     short loc_18000BA19
0x18000ba14  mov     [rsp+14F0h+var_14B8], r13
0x18000ba19  call    cs:__imp_GetCurrentThreadId
0x18000ba1f  mov     [rsp+14F0h+var_14B0], eax
0x18000ba23  mov     [rsp+14F0h+var_1498], r14
0x18000ba28  mov     [rsp+14F0h+var_1490], esi
0x18000ba2c  mov     [rsp+14F0h+var_148C], r12d
0x18000ba31  mov     [rsp+14F0h+var_14A8], r13
0x18000ba36  mov     [rsp+14F0h+var_14A0], r13
0x18000ba3b  mov     [rbp+13F0h+var_1448], r15
0x18000ba3f  mov     [rbp+13F0h+var_1440], rdi
0x18000ba43  mov     [rsp+14F0h+var_1488], r13
0x18000ba48  xorps   xmm0, xmm0
0x18000ba4b  xor     eax, eax
0x18000ba4d  movups  [rbp+13F0h+var_1468], xmm0
0x18000ba51  mov     [rbp+13F0h+var_1458], rax
0x18000ba55  xorps   xmm1, xmm1
0x18000ba58  movups  [rsp+14F0h+var_1480], xmm1
0x18000ba5d  mov     [rbp+13F0h+var_1470], rax
0x18000ba61  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ba68  test    rax, rax
0x18000ba6b  jz      short loc_18000BA78
0x18000ba6d  call    _guard_dispatch_icall
0x18000ba72  mov     [rbp+13F0h+var_1450], rax
0x18000ba76  jmp     short loc_18000BA7C
0x18000ba78  mov     [rbp+13F0h+var_1450], r13
0x18000ba7c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ba83  test    rax, rax
0x18000ba86  jz      short loc_18000BA92
0x18000ba88  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ba8d  call    _guard_dispatch_icall
0x18000ba92  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ba99  test    rax, rax
0x18000ba9c  jz      short loc_18000BAB2
0x18000ba9e  mov     r8d, 400h
0x18000baa4  lea     rdx, [rbp+13F0h+var_1430]
0x18000baa8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000baad  call    _guard_dispatch_icall
0x18000bab2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bab9  test    rax, rax
0x18000babc  jz      short loc_18000BAC8
0x18000babe  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bac3  call    _guard_dispatch_icall
0x18000bac8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bacf  test    rax, rax
0x18000bad2  jz      short loc_18000BAE5
0x18000bad4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000bad9  jnz     short loc_18000BAE5
0x18000badb  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bae0  call    _guard_dispatch_icall
0x18000bae5  cmp     [rsp+14F0h+var_14C8], r13d
0x18000baea  jl      short loc_18000BAFE
0x18000baec  mov     ecx, 8000FFFFh; this
0x18000baf1  mov     [rsp+14F0h+var_14C8], ecx
0x18000baf5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bafa  mov     [rsp+14F0h+var_14C4], eax
0x18000bafe  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000bb05  jnz     short loc_18000BB2F
0x18000bb07  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bb0e  test    rax, rax
0x18000bb11  jz      short loc_18000BB1D
0x18000bb13  call    _guard_dispatch_icall
0x18000bb18  movzx   ecx, al
0x18000bb1b  jmp     short loc_18000BB2B
0x18000bb1d  call    cs:__imp_IsDebuggerPresent
0x18000bb23  mov     ecx, r13d
0x18000bb26  test    eax, eax
0x18000bb28  setnz   cl
0x18000bb2b  test    ecx, ecx
0x18000bb2d  jz      short loc_18000BB36
0x18000bb2f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000bb34  jz      short loc_18000BB5C
0x18000bb36  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bb3d  test    rax, rax
0x18000bb40  jz      short loc_18000BBB5
0x18000bb42  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000bb49  jnz     short loc_18000BBB5
0x18000bb4b  xor     r8d, r8d
0x18000bb4e  xor     edx, edx
0x18000bb50  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bb55  call    _guard_dispatch_icall
0x18000bb5a  jmp     short loc_18000BBB5
0x18000bb5c  mov     ebx, 800h
0x18000bb61  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bb68  test    rax, rax
0x18000bb6b  jz      short loc_18000BB8A
0x18000bb6d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000bb74  jnz     short loc_18000BB8A
0x18000bb76  mov     r8d, ebx
0x18000bb79  lea     rdx, [rbp+13F0h+OutputString]
0x18000bb80  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bb85  call    _guard_dispatch_icall
0x18000bb8a  cmp     [rbp+13F0h+OutputString], r13w
0x18000bb92  jnz     short loc_18000BBA8
0x18000bb94  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000bb99  mov     rdx, rbx; wchar_t *
0x18000bb9c  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000bba3  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000bba8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000bbaf  call    cs:__imp_OutputDebugStringW
0x18000bbb5  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000bbba  jnz     short loc_18000BBC5
0x18000bbbc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000bbc3  jz      short loc_18000BBD7
0x18000bbc5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000bbcc  test    rax, rax
0x18000bbcf  jz      short loc_18000BBD7
0x18000bbd1  call    _guard_dispatch_icall
0x18000bbd6  nop
0x18000bbd7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000bbdc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
