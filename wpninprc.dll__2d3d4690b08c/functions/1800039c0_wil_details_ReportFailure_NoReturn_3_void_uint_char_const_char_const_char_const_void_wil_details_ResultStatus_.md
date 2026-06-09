# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800039c0`
- end: `0x180003c29`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003774`

## callees

- `0x18000209e`
- `0x180002554`
- `0x18000293c`
- `0x180002ca0`
- `0x1800039c0`
- `0x180005834`
- `0x180006680`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a62`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003b6c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003b6c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003bf6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003bf6`

## string_xrefs

- `0x180003a6c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h";
  v26 = a2;
  v27 = v10;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x1800039c0  mov     [rsp-8+arg_10], rbx
0x1800039c5  mov     [rsp-8+arg_18], rsi
0x1800039ca  push    rbp
0x1800039cb  push    rdi
0x1800039cc  push    r12
0x1800039ce  push    r14
0x1800039d0  push    r15
0x1800039d2  lea     rbp, [rsp-13C0h]
0x1800039da  mov     eax, 14C0h
0x1800039df  call    _alloca_probe
0x1800039e4  sub     rsp, rax
0x1800039e7  mov     r14d, edx
0x1800039ea  mov     r15, rcx
0x1800039ed  mov     rsi, [rbp+13E0h+arg_28]
0x1800039f4  xor     edx, edx; Val
0x1800039f6  mov     r8d, 98h; Size
0x1800039fc  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180003a01  call    memset_0
0x180003a06  nop
0x180003a07  xor     r12d, r12d
0x180003a0a  mov     [rbp+13E0h+OutputString], r12w
0x180003a12  mov     [rbp+13E0h+var_1420], r12b
0x180003a16  mov     rbx, [rbp+13E0h+arg_30]
0x180003a1d  mov     ecx, [rbx]; this
0x180003a1f  mov     [rsp+14E0h+var_14B8], ecx
0x180003a23  mov     eax, [rbx+4]
0x180003a26  mov     [rsp+14E0h+var_14B4], eax
0x180003a2a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003a2f  mov     edi, eax
0x180003a31  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180003a39  mov     ecx, r12d
0x180003a3c  lea     eax, [r12+8]
0x180003a41  cmp     dword ptr [rbx+8], 1
0x180003a45  cmovz   ecx, eax
0x180003a48  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180003a4c  lea     ecx, [rax-7]
0x180003a4f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003a57  inc     ecx
0x180003a59  mov     [rsp+14E0h+var_14B0], ecx
0x180003a5d  mov     [rsp+14E0h+var_14A8], r12
0x180003a62  call    cs:__imp_GetCurrentThreadId
0x180003a68  mov     [rsp+14E0h+var_14A0], eax
0x180003a6c  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003a73  mov     [rsp+14E0h+var_1488], rax
0x180003a78  mov     [rsp+14E0h+var_1480], r14d
0x180003a7d  mov     [rsp+14E0h+var_147C], edi
0x180003a81  mov     [rsp+14E0h+var_1498], r12
0x180003a86  mov     [rsp+14E0h+var_1490], r12
0x180003a8b  mov     [rbp+13E0h+var_1438], rsi
0x180003a8f  mov     [rbp+13E0h+var_1430], r15
0x180003a93  mov     [rsp+14E0h+var_1478], r12
0x180003a98  xorps   xmm0, xmm0
0x180003a9b  xor     eax, eax
0x180003a9d  movups  [rbp+13E0h+var_1458], xmm0
0x180003aa1  mov     [rbp+13E0h+var_1448], rax
0x180003aa5  xorps   xmm1, xmm1
0x180003aa8  movups  [rsp+14E0h+var_1470], xmm1
0x180003aad  mov     [rbp+13E0h+var_1460], rax
0x180003ab1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003ab8  test    rax, rax
0x180003abb  jz      short loc_180003AC8
0x180003abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac2  mov     [rbp+13E0h+var_1440], rax
0x180003ac6  jmp     short loc_180003ACC
0x180003ac8  mov     [rbp+13E0h+var_1440], r12
0x180003acc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003ad3  test    rax, rax
0x180003ad6  jz      short loc_180003AE2
0x180003ad8  lea     rcx, [rsp+14E0h+var_14C0]
0x180003add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003ae9  test    rax, rax
0x180003aec  jz      short loc_180003B02
0x180003aee  mov     r8d, 400h
0x180003af4  lea     rdx, [rbp+13E0h+var_1420]
0x180003af8  lea     rcx, [rsp+14E0h+var_14C0]
0x180003afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b02  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003b09  test    rax, rax
0x180003b0c  jz      short loc_180003B18
0x180003b0e  lea     rcx, [rsp+14E0h+var_14C0]
0x180003b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b18  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003b1f  test    rax, rax
0x180003b22  jz      short loc_180003B35
0x180003b24  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180003b29  jnz     short loc_180003B35
0x180003b2b  lea     rcx, [rsp+14E0h+var_14C0]
0x180003b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b35  cmp     [rsp+14E0h+var_14B8], r12d
0x180003b3a  jl      short loc_180003B4E
0x180003b3c  mov     ecx, 8000FFFFh; this
0x180003b41  mov     [rsp+14E0h+var_14B8], ecx
0x180003b45  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003b4a  mov     [rsp+14E0h+var_14B4], eax
0x180003b4e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003b55  jnz     short loc_180003B76
0x180003b57  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003b5e  test    rax, rax
0x180003b61  jz      short loc_180003B6C
0x180003b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b68  test    al, al
0x180003b6a  jmp     short loc_180003B74
0x180003b6c  call    cs:__imp_IsDebuggerPresent
0x180003b72  test    eax, eax
0x180003b74  jz      short loc_180003B7D
0x180003b76  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180003b7b  jz      short loc_180003BA3
0x180003b7d  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b84  test    rax, rax
0x180003b87  jz      short loc_180003BFC
0x180003b89  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003b90  jnz     short loc_180003BFC
0x180003b92  xor     r8d, r8d
0x180003b95  xor     edx, edx
0x180003b97  lea     rcx, [rsp+14E0h+var_14C0]
0x180003b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba1  jmp     short loc_180003BFC
0x180003ba3  mov     ebx, 800h
0x180003ba8  mov     rax, cs:g_pfnResultLoggingCallback
0x180003baf  test    rax, rax
0x180003bb2  jz      short loc_180003BD1
0x180003bb4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003bbb  jnz     short loc_180003BD1
0x180003bbd  mov     r8d, ebx
0x180003bc0  lea     rdx, [rbp+13E0h+OutputString]
0x180003bc7  lea     rcx, [rsp+14E0h+var_14C0]
0x180003bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bd1  cmp     [rbp+13E0h+OutputString], r12w
0x180003bd9  jnz     short loc_180003BEF
0x180003bdb  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180003be0  mov     rdx, rbx; unsigned __int16 *
0x180003be3  lea     rcx, [rbp+13E0h+OutputString]; this
0x180003bea  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003bef  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180003bf6  call    cs:__imp_OutputDebugStringW
0x180003bfc  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180003c01  jnz     short loc_180003C0C
0x180003c03  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003c0a  jz      short loc_180003C1E
0x180003c0c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003c13  test    rax, rax
0x180003c16  jz      short loc_180003C1E
0x180003c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c1d  nop
0x180003c1e  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180003c23  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
