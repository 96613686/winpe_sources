# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180025a04`
- end: `0x180025c6b`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800257b8`

## callees

- `0x180025a04`
- `0x18002c960`
- `0x18002d8c8`
- `0x18002f4a0`
- `0x180030d80`
- `0x180068fe6`
- `0x1800690e0`
- `0x18006f010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180025baf`
- `KERNEL32!IsDebuggerPresent` at `0x180025baf`
- `KERNEL32!OutputDebugStringW` at `0x180025c39`
- `KERNEL32!OutputDebugStringW` at `0x180025c39`
- `KERNEL32!GetCurrentThreadId` at `0x180025aa5`
- `KERNEL32!GetCurrentThreadId` at `0x180025aa5`

## string_xrefs

- `0x180025aba`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180025a04  mov     [rsp-8+arg_10], rbx
0x180025a09  mov     [rsp-8+arg_18], rsi
0x180025a0e  push    rbp
0x180025a0f  push    rdi
0x180025a10  push    r12
0x180025a12  push    r14
0x180025a14  push    r15
0x180025a16  lea     rbp, [rsp-13C0h]
0x180025a1e  mov     eax, 14C0h
0x180025a23  call    _alloca_probe
0x180025a28  sub     rsp, rax
0x180025a2b  mov     rsi, [rbp+13E0h+arg_28]
0x180025a32  mov     r14d, edx
0x180025a35  mov     r15, rcx
0x180025a38  xor     edx, edx; Val
0x180025a3a  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180025a3f  mov     r8d, 98h; Size
0x180025a45  call    memset_0
0x180025a4a  mov     rbx, [rbp+13E0h+arg_30]
0x180025a51  xor     r12d, r12d
0x180025a54  mov     [rbp+13E0h+OutputString], r12w
0x180025a5c  mov     [rbp+13E0h+var_1420], r12b
0x180025a60  mov     ecx, [rbx]; this
0x180025a62  mov     eax, [rbx+4]
0x180025a65  mov     [rsp+14E0h+var_14B8], ecx
0x180025a69  mov     [rsp+14E0h+var_14B4], eax
0x180025a6d  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180025a72  cmp     dword ptr [rbx+8], 1
0x180025a76  mov     edi, eax
0x180025a78  lea     eax, [r12+8]
0x180025a7d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180025a85  mov     ecx, r12d
0x180025a88  cmovz   ecx, eax
0x180025a8b  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180025a8f  lea     ecx, [rax-7]
0x180025a92  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180025a9a  inc     ecx
0x180025a9c  mov     [rsp+14E0h+var_14A8], r12
0x180025aa1  mov     [rsp+14E0h+var_14B0], ecx
0x180025aa5  call    cs:__imp_GetCurrentThreadId
0x180025aab  xorps   xmm0, xmm0
0x180025aae  mov     [rsp+14E0h+var_1480], r14d
0x180025ab3  mov     [rsp+14E0h+var_14A0], eax
0x180025ab7  xorps   xmm1, xmm1
0x180025aba  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025ac1  mov     [rsp+14E0h+var_147C], edi
0x180025ac5  mov     [rsp+14E0h+var_1488], rax
0x180025aca  xor     eax, eax
0x180025acc  mov     [rbp+13E0h+var_1448], rax
0x180025ad0  mov     [rbp+13E0h+var_1460], rax
0x180025ad4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180025adb  mov     [rsp+14E0h+var_1498], r12
0x180025ae0  mov     [rsp+14E0h+var_1490], r12
0x180025ae5  mov     [rbp+13E0h+var_1438], rsi
0x180025ae9  mov     [rbp+13E0h+var_1430], r15
0x180025aed  mov     [rsp+14E0h+var_1478], r12
0x180025af2  movups  [rbp+13E0h+var_1458], xmm0
0x180025af6  movups  [rsp+14E0h+var_1470], xmm1
0x180025afb  test    rax, rax
0x180025afe  jz      short loc_180025B0B
0x180025b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b05  mov     [rbp+13E0h+var_1440], rax
0x180025b09  jmp     short loc_180025B0F
0x180025b0b  mov     [rbp+13E0h+var_1440], r12
0x180025b0f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025b16  test    rax, rax
0x180025b19  jz      short loc_180025B25
0x180025b1b  lea     rcx, [rsp+14E0h+var_14C0]
0x180025b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b25  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025b2c  test    rax, rax
0x180025b2f  jz      short loc_180025B45
0x180025b31  mov     r8d, 400h
0x180025b37  lea     rdx, [rbp+13E0h+var_1420]
0x180025b3b  lea     rcx, [rsp+14E0h+var_14C0]
0x180025b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b45  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025b4c  test    rax, rax
0x180025b4f  jz      short loc_180025B5B
0x180025b51  lea     rcx, [rsp+14E0h+var_14C0]
0x180025b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b5b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025b62  test    rax, rax
0x180025b65  jz      short loc_180025B78
0x180025b67  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180025b6c  jnz     short loc_180025B78
0x180025b6e  lea     rcx, [rsp+14E0h+var_14C0]
0x180025b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b78  cmp     [rsp+14E0h+var_14B8], r12d
0x180025b7d  jl      short loc_180025B91
0x180025b7f  mov     ecx, 8000FFFFh; this
0x180025b84  mov     [rsp+14E0h+var_14B8], ecx
0x180025b88  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025b8d  mov     [rsp+14E0h+var_14B4], eax
0x180025b91  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180025b98  jnz     short loc_180025BB9
0x180025b9a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180025ba1  test    rax, rax
0x180025ba4  jz      short loc_180025BAF
0x180025ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bab  test    al, al
0x180025bad  jmp     short loc_180025BB7
0x180025baf  call    cs:__imp_IsDebuggerPresent
0x180025bb5  test    eax, eax
0x180025bb7  jz      short loc_180025BC0
0x180025bb9  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180025bbe  jz      short loc_180025BE6
0x180025bc0  mov     rax, cs:g_pfnResultLoggingCallback
0x180025bc7  test    rax, rax
0x180025bca  jz      short loc_180025C3F
0x180025bcc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180025bd3  jnz     short loc_180025C3F
0x180025bd5  xor     r8d, r8d
0x180025bd8  lea     rcx, [rsp+14E0h+var_14C0]
0x180025bdd  xor     edx, edx
0x180025bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025be4  jmp     short loc_180025C3F
0x180025be6  mov     rax, cs:g_pfnResultLoggingCallback
0x180025bed  mov     ebx, 800h
0x180025bf2  test    rax, rax
0x180025bf5  jz      short loc_180025C14
0x180025bf7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180025bfe  jnz     short loc_180025C14
0x180025c00  mov     r8d, ebx
0x180025c03  lea     rdx, [rbp+13E0h+OutputString]
0x180025c0a  lea     rcx, [rsp+14E0h+var_14C0]
0x180025c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c14  cmp     [rbp+13E0h+OutputString], r12w
0x180025c1c  jnz     short loc_180025C32
0x180025c1e  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180025c23  mov     rdx, rbx; unsigned __int16 *
0x180025c26  lea     rcx, [rbp+13E0h+OutputString]; this
0x180025c2d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025c32  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180025c39  call    cs:__imp_OutputDebugStringW
0x180025c3f  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180025c44  jnz     short loc_180025C4F
0x180025c46  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180025c4d  jz      short loc_180025C60
0x180025c4f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025c56  test    rax, rax
0x180025c59  jz      short loc_180025C60
0x180025c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c60  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180025c65  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
