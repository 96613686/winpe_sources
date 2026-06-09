# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180021c6c`
- end: `0x180021ef6`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `650`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180021a10`

## callees

- `0x180021c6c`
- `0x180025564`
- `0x180025d94`
- `0x180027050`
- `0x1800282a8`
- `0x1800319ae`
- `0x180031ab0`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180021d1d`
- `KERNEL32!GetCurrentThreadId` at `0x180021d1d`
- `KERNEL32!OutputDebugStringW` at `0x180021ebd`
- `KERNEL32!OutputDebugStringW` at `0x180021ebd`
- `KERNEL32!IsDebuggerPresent` at `0x180021e2d`
- `KERNEL32!IsDebuggerPresent` at `0x180021e2d`

## string_xrefs

- `0x180021d2d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v36; // [rsp+C0h] [rbp-40h]
  char v37[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2064]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v36 = -2;
  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
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
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v37, 1024);
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
0x180021c6c  push    rbp
0x180021c6e  push    rdi
0x180021c6f  push    r12
0x180021c71  push    r14
0x180021c73  push    r15
0x180021c75  lea     rbp, [rsp-13D0h]
0x180021c7d  mov     eax, 14D0h
0x180021c82  call    _alloca_probe
0x180021c87  sub     rsp, rax
0x180021c8a  mov     [rbp+13F0h+var_1430], 0FFFFFFFFFFFFFFFEh
0x180021c92  mov     [rsp+14F0h+arg_10], rbx
0x180021c9a  mov     [rsp+14F0h+arg_18], rsi
0x180021ca2  mov     r14d, edx
0x180021ca5  mov     r15, rcx
0x180021ca8  mov     rsi, [rbp+13F0h+arg_28]
0x180021caf  xor     edx, edx; Val
0x180021cb1  mov     r8d, 98h; Size
0x180021cb7  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180021cbc  call    memset_0
0x180021cc1  nop
0x180021cc2  xor     r12d, r12d
0x180021cc5  mov     [rbp+13F0h+OutputString], r12w
0x180021ccd  mov     [rbp+13F0h+var_1420], r12b
0x180021cd1  mov     rbx, [rbp+13F0h+arg_30]
0x180021cd8  mov     ecx, [rbx]; this
0x180021cda  mov     [rsp+14F0h+var_14C8], ecx
0x180021cde  mov     eax, [rbx+4]
0x180021ce1  mov     [rsp+14F0h+var_14C4], eax
0x180021ce5  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180021cea  mov     edi, eax
0x180021cec  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180021cf4  mov     ecx, r12d
0x180021cf7  lea     eax, [r12+8]
0x180021cfc  cmp     dword ptr [rbx+8], 1
0x180021d00  cmovz   ecx, eax
0x180021d03  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180021d07  lea     ecx, [rax-7]
0x180021d0a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180021d12  inc     ecx
0x180021d14  mov     [rsp+14F0h+var_14C0], ecx
0x180021d18  mov     [rsp+14F0h+var_14B8], r12
0x180021d1d  call    cs:__imp_GetCurrentThreadId
0x180021d24  nop     dword ptr [rax+rax+00h]
0x180021d29  mov     [rsp+14F0h+var_14B0], eax
0x180021d2d  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021d34  mov     [rsp+14F0h+var_1498], rax
0x180021d39  mov     [rsp+14F0h+var_1490], r14d
0x180021d3e  mov     [rsp+14F0h+var_148C], edi
0x180021d42  mov     [rsp+14F0h+var_14A8], r12
0x180021d47  mov     [rsp+14F0h+var_14A0], r12
0x180021d4c  mov     [rbp+13F0h+var_1448], rsi
0x180021d50  mov     [rbp+13F0h+var_1440], r15
0x180021d54  mov     [rsp+14F0h+var_1488], r12
0x180021d59  xorps   xmm0, xmm0
0x180021d5c  xor     eax, eax
0x180021d5e  movups  [rbp+13F0h+var_1468], xmm0
0x180021d62  mov     [rbp+13F0h+var_1458], rax
0x180021d66  xorps   xmm1, xmm1
0x180021d69  movups  [rsp+14F0h+var_1480], xmm1
0x180021d6e  mov     [rbp+13F0h+var_1470], rax
0x180021d72  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180021d79  test    rax, rax
0x180021d7c  jz      short loc_180021D89
0x180021d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d83  mov     [rbp+13F0h+var_1450], rax
0x180021d87  jmp     short loc_180021D8D
0x180021d89  mov     [rbp+13F0h+var_1450], r12
0x180021d8d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180021d94  test    rax, rax
0x180021d97  jz      short loc_180021DA3
0x180021d99  lea     rcx, [rsp+14F0h+var_14D0]
0x180021d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021da3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180021daa  test    rax, rax
0x180021dad  jz      short loc_180021DC3
0x180021daf  mov     r8d, 400h
0x180021db5  lea     rdx, [rbp+13F0h+var_1420]
0x180021db9  lea     rcx, [rsp+14F0h+var_14D0]
0x180021dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dc3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021dca  test    rax, rax
0x180021dcd  jz      short loc_180021DD9
0x180021dcf  lea     rcx, [rsp+14F0h+var_14D0]
0x180021dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dd9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021de0  test    rax, rax
0x180021de3  jz      short loc_180021DF6
0x180021de5  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180021dea  jnz     short loc_180021DF6
0x180021dec  lea     rcx, [rsp+14F0h+var_14D0]
0x180021df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021df6  cmp     [rsp+14F0h+var_14C8], r12d
0x180021dfb  jl      short loc_180021E0F
0x180021dfd  mov     ecx, 8000FFFFh; this
0x180021e02  mov     [rsp+14F0h+var_14C8], ecx
0x180021e06  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180021e0b  mov     [rsp+14F0h+var_14C4], eax
0x180021e0f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180021e16  jnz     short loc_180021E3D
0x180021e18  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180021e1f  test    rax, rax
0x180021e22  jz      short loc_180021E2D
0x180021e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e29  test    al, al
0x180021e2b  jmp     short loc_180021E3B
0x180021e2d  call    cs:__imp_IsDebuggerPresent
0x180021e34  nop     dword ptr [rax+rax+00h]
0x180021e39  test    eax, eax
0x180021e3b  jz      short loc_180021E44
0x180021e3d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180021e42  jz      short loc_180021E6A
0x180021e44  mov     rax, cs:g_pfnResultLoggingCallback
0x180021e4b  test    rax, rax
0x180021e4e  jz      short loc_180021EC9
0x180021e50  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180021e57  jnz     short loc_180021EC9
0x180021e59  xor     r8d, r8d
0x180021e5c  xor     edx, edx
0x180021e5e  lea     rcx, [rsp+14F0h+var_14D0]
0x180021e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e68  jmp     short loc_180021EC9
0x180021e6a  mov     ebx, 800h
0x180021e6f  mov     rax, cs:g_pfnResultLoggingCallback
0x180021e76  test    rax, rax
0x180021e79  jz      short loc_180021E98
0x180021e7b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180021e82  jnz     short loc_180021E98
0x180021e84  mov     r8d, ebx
0x180021e87  lea     rdx, [rbp+13F0h+OutputString]
0x180021e8e  lea     rcx, [rsp+14F0h+var_14D0]
0x180021e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e98  cmp     [rbp+13F0h+OutputString], r12w
0x180021ea0  jnz     short loc_180021EB6
0x180021ea2  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180021ea7  mov     rdx, rbx; unsigned __int16 *
0x180021eaa  lea     rcx, [rbp+13F0h+OutputString]; this
0x180021eb1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180021eb6  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180021ebd  call    cs:__imp_OutputDebugStringW
0x180021ec4  nop     dword ptr [rax+rax+00h]
0x180021ec9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180021ece  jnz     short loc_180021ED9
0x180021ed0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180021ed7  jz      short loc_180021EEB
0x180021ed9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180021ee0  test    rax, rax
0x180021ee3  jz      short loc_180021EEB
0x180021ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021eea  nop
0x180021eeb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180021ef0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
