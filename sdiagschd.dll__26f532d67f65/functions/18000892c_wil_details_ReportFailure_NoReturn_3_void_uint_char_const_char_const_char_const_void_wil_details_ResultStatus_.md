# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000892c`
- end: `0x180008ba7`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800086c8`

## callees

- `0x18000892c`
- `0x180009b84`
- `0x18000a3a0`
- `0x18000adc0`
- `0x18000c38c`
- `0x18000c836`
- `0x18000c920`
- `0x18000d010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180008ade`
- `KERNEL32!IsDebuggerPresent` at `0x180008ade`
- `KERNEL32!OutputDebugStringW` at `0x180008b6e`
- `KERNEL32!OutputDebugStringW` at `0x180008b6e`
- `KERNEL32!GetCurrentThreadId` at `0x1800089ce`
- `KERNEL32!GetCurrentThreadId` at `0x1800089ce`

## string_xrefs

- `0x1800089de`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000892c  mov     [rsp-8+arg_10], rbx
0x180008931  mov     [rsp-8+arg_18], rsi
0x180008936  push    rbp
0x180008937  push    rdi
0x180008938  push    r12
0x18000893a  push    r14
0x18000893c  push    r15
0x18000893e  lea     rbp, [rsp-13C0h]
0x180008946  mov     eax, 14C0h
0x18000894b  call    _alloca_probe
0x180008950  sub     rsp, rax
0x180008953  mov     r14d, edx
0x180008956  mov     r15, rcx
0x180008959  mov     rsi, [rbp+13E0h+arg_28]
0x180008960  xor     edx, edx; Val
0x180008962  mov     r8d, 98h; Size
0x180008968  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000896d  call    memset_0
0x180008972  nop
0x180008973  xor     r12d, r12d
0x180008976  mov     [rbp+13E0h+OutputString], r12w
0x18000897e  mov     [rbp+13E0h+var_1420], r12b
0x180008982  mov     rbx, [rbp+13E0h+arg_30]
0x180008989  mov     ecx, [rbx]; this
0x18000898b  mov     [rsp+14E0h+var_14B8], ecx
0x18000898f  mov     eax, [rbx+4]
0x180008992  mov     [rsp+14E0h+var_14B4], eax
0x180008996  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000899b  mov     edi, eax
0x18000899d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800089a5  mov     ecx, r12d
0x1800089a8  lea     eax, [r12+8]
0x1800089ad  cmp     dword ptr [rbx+8], 1
0x1800089b1  cmovz   ecx, eax
0x1800089b4  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800089b8  lea     ecx, [rax-7]
0x1800089bb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x1800089c3  inc     ecx
0x1800089c5  mov     [rsp+14E0h+var_14B0], ecx
0x1800089c9  mov     [rsp+14E0h+var_14A8], r12
0x1800089ce  call    cs:__imp_GetCurrentThreadId
0x1800089d5  nop     dword ptr [rax+rax+00h]
0x1800089da  mov     [rsp+14E0h+var_14A0], eax
0x1800089de  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800089e5  mov     [rsp+14E0h+var_1488], rax
0x1800089ea  mov     [rsp+14E0h+var_1480], r14d
0x1800089ef  mov     [rsp+14E0h+var_147C], edi
0x1800089f3  mov     [rsp+14E0h+var_1498], r12
0x1800089f8  mov     [rsp+14E0h+var_1490], r12
0x1800089fd  mov     [rbp+13E0h+var_1438], rsi
0x180008a01  mov     [rbp+13E0h+var_1430], r15
0x180008a05  mov     [rsp+14E0h+var_1478], r12
0x180008a0a  xorps   xmm0, xmm0
0x180008a0d  xor     eax, eax
0x180008a0f  movups  [rbp+13E0h+var_1458], xmm0
0x180008a13  mov     [rbp+13E0h+var_1448], rax
0x180008a17  xorps   xmm1, xmm1
0x180008a1a  movups  [rsp+14E0h+var_1470], xmm1
0x180008a1f  mov     [rbp+13E0h+var_1460], rax
0x180008a23  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008a2a  test    rax, rax
0x180008a2d  jz      short loc_180008A3A
0x180008a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a34  mov     [rbp+13E0h+var_1440], rax
0x180008a38  jmp     short loc_180008A3E
0x180008a3a  mov     [rbp+13E0h+var_1440], r12
0x180008a3e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008a45  test    rax, rax
0x180008a48  jz      short loc_180008A54
0x180008a4a  lea     rcx, [rsp+14E0h+var_14C0]
0x180008a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a54  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008a5b  test    rax, rax
0x180008a5e  jz      short loc_180008A74
0x180008a60  mov     r8d, 400h
0x180008a66  lea     rdx, [rbp+13E0h+var_1420]
0x180008a6a  lea     rcx, [rsp+14E0h+var_14C0]
0x180008a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a74  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008a7b  test    rax, rax
0x180008a7e  jz      short loc_180008A8A
0x180008a80  lea     rcx, [rsp+14E0h+var_14C0]
0x180008a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a8a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008a91  test    rax, rax
0x180008a94  jz      short loc_180008AA7
0x180008a96  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180008a9b  jnz     short loc_180008AA7
0x180008a9d  lea     rcx, [rsp+14E0h+var_14C0]
0x180008aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa7  cmp     [rsp+14E0h+var_14B8], r12d
0x180008aac  jl      short loc_180008AC0
0x180008aae  mov     ecx, 8000FFFFh; this
0x180008ab3  mov     [rsp+14E0h+var_14B8], ecx
0x180008ab7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008abc  mov     [rsp+14E0h+var_14B4], eax
0x180008ac0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180008ac7  jnz     short loc_180008AEE
0x180008ac9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008ad0  test    rax, rax
0x180008ad3  jz      short loc_180008ADE
0x180008ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ada  test    al, al
0x180008adc  jmp     short loc_180008AEC
0x180008ade  call    cs:__imp_IsDebuggerPresent
0x180008ae5  nop     dword ptr [rax+rax+00h]
0x180008aea  test    eax, eax
0x180008aec  jz      short loc_180008AF5
0x180008aee  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180008af3  jz      short loc_180008B1B
0x180008af5  mov     rax, cs:g_pfnResultLoggingCallback
0x180008afc  test    rax, rax
0x180008aff  jz      short loc_180008B7A
0x180008b01  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008b08  jnz     short loc_180008B7A
0x180008b0a  xor     r8d, r8d
0x180008b0d  xor     edx, edx
0x180008b0f  lea     rcx, [rsp+14E0h+var_14C0]
0x180008b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b19  jmp     short loc_180008B7A
0x180008b1b  mov     ebx, 800h
0x180008b20  mov     rax, cs:g_pfnResultLoggingCallback
0x180008b27  test    rax, rax
0x180008b2a  jz      short loc_180008B49
0x180008b2c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008b33  jnz     short loc_180008B49
0x180008b35  mov     r8d, ebx
0x180008b38  lea     rdx, [rbp+13E0h+OutputString]
0x180008b3f  lea     rcx, [rsp+14E0h+var_14C0]
0x180008b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b49  cmp     [rbp+13E0h+OutputString], r12w
0x180008b51  jnz     short loc_180008B67
0x180008b53  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180008b58  mov     rdx, rbx; unsigned __int16 *
0x180008b5b  lea     rcx, [rbp+13E0h+OutputString]; this
0x180008b62  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008b67  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180008b6e  call    cs:__imp_OutputDebugStringW
0x180008b75  nop     dword ptr [rax+rax+00h]
0x180008b7a  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180008b7f  jnz     short loc_180008B8A
0x180008b81  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180008b88  jz      short loc_180008B9C
0x180008b8a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008b91  test    rax, rax
0x180008b94  jz      short loc_180008B9C
0x180008b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9b  nop
0x180008b9c  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180008ba1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
