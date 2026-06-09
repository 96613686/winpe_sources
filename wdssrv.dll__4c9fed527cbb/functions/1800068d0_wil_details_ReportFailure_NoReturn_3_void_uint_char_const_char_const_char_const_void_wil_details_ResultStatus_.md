# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800068d0`
- end: `0x180006b42`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000665c`

## callees

- `0x1800068d0`
- `0x1800091d4`
- `0x180009b0c`
- `0x18000b7f0`
- `0x18000e79c`
- `0x18001c12a`
- `0x18001c210`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006971`
- `KERNEL32!GetCurrentThreadId` at `0x180006971`
- `KERNEL32!IsDebuggerPresent` at `0x180006a7a`
- `KERNEL32!IsDebuggerPresent` at `0x180006a7a`
- `KERNEL32!OutputDebugStringW` at `0x180006b0a`
- `KERNEL32!OutputDebugStringW` at `0x180006b0a`

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
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x1800068d0  mov     [rsp-8+arg_18], rbx
0x1800068d5  push    rbp
0x1800068d6  push    rsi
0x1800068d7  push    rdi
0x1800068d8  push    r12
0x1800068da  push    r13
0x1800068dc  push    r14
0x1800068de  push    r15
0x1800068e0  lea     rbp, [rsp-13C0h]
0x1800068e8  mov     eax, 14C0h
0x1800068ed  call    _alloca_probe
0x1800068f2  sub     rsp, rax
0x1800068f5  mov     rsi, [rbp+13F0h+arg_28]
0x1800068fc  mov     r15, r8
0x1800068ff  mov     r14d, edx
0x180006902  mov     r12, rcx
0x180006905  xor     edx, edx; Val
0x180006907  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000690c  mov     r8d, 98h; Size
0x180006912  call    memset_0
0x180006917  mov     rbx, [rbp+13F0h+arg_30]
0x18000691e  xor     r13d, r13d
0x180006921  mov     [rbp+13F0h+OutputString], r13w
0x180006929  mov     [rbp+13F0h+var_1430], r13b
0x18000692d  mov     ecx, [rbx]; this
0x18000692f  mov     eax, [rbx+4]
0x180006932  mov     [rsp+14F0h+var_14C8], ecx
0x180006936  mov     [rsp+14F0h+var_14C4], eax
0x18000693a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000693f  cmp     dword ptr [rbx+8], 1
0x180006943  mov     edi, eax
0x180006945  lea     eax, [r13+8]
0x180006949  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180006951  mov     ecx, r13d
0x180006954  cmovz   ecx, eax
0x180006957  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000695b  lea     ecx, [rax-7]
0x18000695e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180006966  inc     ecx
0x180006968  mov     [rsp+14F0h+var_14B8], r13
0x18000696d  mov     [rsp+14F0h+var_14C0], ecx
0x180006971  call    cs:__imp_GetCurrentThreadId
0x180006978  nop     dword ptr [rax+rax+00h]
0x18000697d  xorps   xmm0, xmm0
0x180006980  mov     [rsp+14F0h+var_1498], r15
0x180006985  mov     [rsp+14F0h+var_14B0], eax
0x180006989  xorps   xmm1, xmm1
0x18000698c  xor     eax, eax
0x18000698e  mov     [rsp+14F0h+var_1490], r14d
0x180006993  mov     [rbp+13F0h+var_1458], rax
0x180006997  mov     [rbp+13F0h+var_1470], rax
0x18000699b  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800069a2  mov     [rsp+14F0h+var_148C], edi
0x1800069a6  mov     [rsp+14F0h+var_14A8], r13
0x1800069ab  mov     [rsp+14F0h+var_14A0], r13
0x1800069b0  mov     [rbp+13F0h+var_1448], rsi
0x1800069b4  mov     [rbp+13F0h+var_1440], r12
0x1800069b8  mov     [rsp+14F0h+var_1488], r13
0x1800069bd  movups  [rbp+13F0h+var_1468], xmm0
0x1800069c1  movups  [rsp+14F0h+var_1480], xmm1
0x1800069c6  test    rax, rax
0x1800069c9  jz      short loc_1800069D6
0x1800069cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d0  mov     [rbp+13F0h+var_1450], rax
0x1800069d4  jmp     short loc_1800069DA
0x1800069d6  mov     [rbp+13F0h+var_1450], r13
0x1800069da  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800069e1  test    rax, rax
0x1800069e4  jz      short loc_1800069F0
0x1800069e6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800069eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800069f7  test    rax, rax
0x1800069fa  jz      short loc_180006A10
0x1800069fc  mov     r8d, 400h
0x180006a02  lea     rdx, [rbp+13F0h+var_1430]
0x180006a06  lea     rcx, [rsp+14F0h+var_14D0]
0x180006a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a10  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006a17  test    rax, rax
0x180006a1a  jz      short loc_180006A26
0x180006a1c  lea     rcx, [rsp+14F0h+var_14D0]
0x180006a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a26  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006a2d  test    rax, rax
0x180006a30  jz      short loc_180006A43
0x180006a32  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006a37  jnz     short loc_180006A43
0x180006a39  lea     rcx, [rsp+14F0h+var_14D0]
0x180006a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a43  cmp     [rsp+14F0h+var_14C8], r13d
0x180006a48  jl      short loc_180006A5C
0x180006a4a  mov     ecx, 8000FFFFh; this
0x180006a4f  mov     [rsp+14F0h+var_14C8], ecx
0x180006a53  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006a58  mov     [rsp+14F0h+var_14C4], eax
0x180006a5c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006a63  jnz     short loc_180006A8A
0x180006a65  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006a6c  test    rax, rax
0x180006a6f  jz      short loc_180006A7A
0x180006a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a76  test    al, al
0x180006a78  jmp     short loc_180006A88
0x180006a7a  call    cs:__imp_IsDebuggerPresent
0x180006a81  nop     dword ptr [rax+rax+00h]
0x180006a86  test    eax, eax
0x180006a88  jz      short loc_180006A91
0x180006a8a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006a8f  jz      short loc_180006AB7
0x180006a91  mov     rax, cs:g_pfnResultLoggingCallback
0x180006a98  test    rax, rax
0x180006a9b  jz      short loc_180006B16
0x180006a9d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006aa4  jnz     short loc_180006B16
0x180006aa6  xor     r8d, r8d
0x180006aa9  lea     rcx, [rsp+14F0h+var_14D0]
0x180006aae  xor     edx, edx
0x180006ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab5  jmp     short loc_180006B16
0x180006ab7  mov     rax, cs:g_pfnResultLoggingCallback
0x180006abe  mov     ebx, 800h
0x180006ac3  test    rax, rax
0x180006ac6  jz      short loc_180006AE5
0x180006ac8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006acf  jnz     short loc_180006AE5
0x180006ad1  mov     r8d, ebx
0x180006ad4  lea     rdx, [rbp+13F0h+OutputString]
0x180006adb  lea     rcx, [rsp+14F0h+var_14D0]
0x180006ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae5  cmp     [rbp+13F0h+OutputString], r13w
0x180006aed  jnz     short loc_180006B03
0x180006aef  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006af4  mov     rdx, rbx; unsigned __int16 *
0x180006af7  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006afe  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006b03  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006b0a  call    cs:__imp_OutputDebugStringW
0x180006b11  nop     dword ptr [rax+rax+00h]
0x180006b16  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006b1b  jnz     short loc_180006B26
0x180006b1d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006b24  jz      short loc_180006B37
0x180006b26  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006b2d  test    rax, rax
0x180006b30  jz      short loc_180006B37
0x180006b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b37  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006b3c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
