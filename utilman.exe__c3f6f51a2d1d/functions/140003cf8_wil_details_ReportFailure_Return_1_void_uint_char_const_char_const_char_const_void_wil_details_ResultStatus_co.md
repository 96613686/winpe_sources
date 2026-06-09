# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003cf8`
- end: `0x140003fb1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400037f0`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x140003cf8`
- `0x140005964`
- `0x1400077a4`
- `0x1400093f0`
- `0x140009694`
- `0x1400269f0`
- `0x140029010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003dbe`
- `KERNEL32!GetCurrentThreadId` at `0x140003dbe`
- `KERNEL32!OutputDebugStringW` at `0x140003f49`
- `KERNEL32!OutputDebugStringW` at `0x140003f49`
- `KERNEL32!IsDebuggerPresent` at `0x140003eb9`
- `KERNEL32!IsDebuggerPresent` at `0x140003eb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x140003cf8  push    rbp
0x140003cfa  push    rbx
0x140003cfb  push    rsi
0x140003cfc  push    rdi
0x140003cfd  push    r12
0x140003cff  push    r14
0x140003d01  push    r15
0x140003d03  lea     rbp, [rsp-13D0h]
0x140003d0b  mov     eax, 14D0h
0x140003d10  call    _alloca_probe
0x140003d15  sub     rsp, rax
0x140003d18  mov     rax, cs:__security_cookie
0x140003d1f  xor     rax, rsp
0x140003d22  mov     [rbp+1400h+var_40], rax
0x140003d29  mov     rsi, r8
0x140003d2c  mov     edi, edx
0x140003d2e  mov     rbx, rcx
0x140003d31  mov     r14, [rbp+1400h+arg_28]
0x140003d38  xor     edx, edx; Val
0x140003d3a  mov     r8d, 98h; Size
0x140003d40  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003d45  call    memset_0
0x140003d4a  nop
0x140003d4b  xor     r12d, r12d
0x140003d4e  mov     [rbp+1400h+OutputString], r12w
0x140003d56  mov     [rbp+1400h+var_1440], r12b
0x140003d5a  mov     rdx, [rbp+1400h+arg_30]; int
0x140003d61  mov     ecx, [rdx]; this
0x140003d63  mov     [rsp+1500h+var_14D8], ecx
0x140003d67  mov     eax, [rdx+4]
0x140003d6a  mov     [rsp+1500h+var_14D4], eax
0x140003d6e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003d73  mov     r15d, eax
0x140003d76  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003d7e  mov     ecx, r12d
0x140003d81  lea     eax, [r12+8]
0x140003d86  cmp     dword ptr [rdx+8], 1
0x140003d8a  cmovz   ecx, eax
0x140003d8d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003d91  lea     ecx, [rax-7]
0x140003d94  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003d9c  inc     ecx
0x140003d9e  mov     [rsp+1500h+var_14D0], ecx
0x140003da2  mov     rcx, [rbp+1400h+arg_38]
0x140003da9  test    rcx, rcx
0x140003dac  jz      short loc_140003DB9
0x140003dae  cmp     [rcx], r12w
0x140003db2  mov     [rsp+1500h+var_14C8], rcx
0x140003db7  jnz     short loc_140003DBE
0x140003db9  mov     [rsp+1500h+var_14C8], r12
0x140003dbe  call    cs:__imp_GetCurrentThreadId
0x140003dc5  nop     dword ptr [rax+rax+00h]
0x140003dca  mov     [rsp+1500h+var_14C0], eax
0x140003dce  mov     [rsp+1500h+var_14A8], rsi
0x140003dd3  mov     [rsp+1500h+var_14A0], edi
0x140003dd7  mov     [rsp+1500h+var_149C], r15d
0x140003ddc  mov     [rsp+1500h+var_14B8], r12
0x140003de1  mov     [rsp+1500h+var_14B0], r12
0x140003de6  mov     [rbp+1400h+var_1458], r14
0x140003dea  mov     [rbp+1400h+var_1450], rbx
0x140003dee  mov     [rsp+1500h+var_1498], r12
0x140003df3  xorps   xmm0, xmm0
0x140003df6  xor     eax, eax
0x140003df8  movups  [rbp+1400h+var_1478], xmm0
0x140003dfc  mov     [rbp+1400h+var_1468], rax
0x140003e00  xorps   xmm1, xmm1
0x140003e03  movups  [rsp+1500h+var_1490], xmm1
0x140003e08  mov     [rbp+1400h+var_1480], rax
0x140003e0c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003e13  test    rax, rax
0x140003e16  jz      short loc_140003E23
0x140003e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e1d  mov     [rbp+1400h+var_1460], rax
0x140003e21  jmp     short loc_140003E27
0x140003e23  mov     [rbp+1400h+var_1460], r12
0x140003e27  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003e2e  test    rax, rax
0x140003e31  jz      short loc_140003E3D
0x140003e33  lea     rcx, [rsp+1500h+var_14E0]
0x140003e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e3d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003e44  test    rax, rax
0x140003e47  jz      short loc_140003E5D
0x140003e49  mov     r8d, 400h
0x140003e4f  lea     rdx, [rbp+1400h+var_1440]
0x140003e53  lea     rcx, [rsp+1500h+var_14E0]
0x140003e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e5d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003e64  test    rax, rax
0x140003e67  jz      short loc_140003E73
0x140003e69  lea     rcx, [rsp+1500h+var_14E0]
0x140003e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e73  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003e7a  test    rax, rax
0x140003e7d  jz      short loc_140003E90
0x140003e7f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003e84  jnz     short loc_140003E90
0x140003e86  lea     rcx, [rsp+1500h+var_14E0]
0x140003e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e90  cmp     [rsp+1500h+var_14D8], r12d
0x140003e95  jge     loc_140003FAB
0x140003e9b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140003ea2  jnz     short loc_140003EC9
0x140003ea4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003eab  test    rax, rax
0x140003eae  jz      short loc_140003EB9
0x140003eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003eb5  test    al, al
0x140003eb7  jmp     short loc_140003EC7
0x140003eb9  call    cs:__imp_IsDebuggerPresent
0x140003ec0  nop     dword ptr [rax+rax+00h]
0x140003ec5  test    eax, eax
0x140003ec7  jz      short loc_140003ED0
0x140003ec9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003ece  jz      short loc_140003EF6
0x140003ed0  mov     rax, cs:g_pfnResultLoggingCallback
0x140003ed7  test    rax, rax
0x140003eda  jz      short loc_140003F55
0x140003edc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003ee3  jnz     short loc_140003F55
0x140003ee5  xor     r8d, r8d
0x140003ee8  xor     edx, edx
0x140003eea  lea     rcx, [rsp+1500h+var_14E0]
0x140003eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ef4  jmp     short loc_140003F55
0x140003ef6  mov     ebx, 800h
0x140003efb  mov     rax, cs:g_pfnResultLoggingCallback
0x140003f02  test    rax, rax
0x140003f05  jz      short loc_140003F24
0x140003f07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003f0e  jnz     short loc_140003F24
0x140003f10  mov     r8d, ebx
0x140003f13  lea     rdx, [rbp+1400h+OutputString]
0x140003f1a  lea     rcx, [rsp+1500h+var_14E0]
0x140003f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f24  cmp     [rbp+1400h+OutputString], r12w
0x140003f2c  jnz     short loc_140003F42
0x140003f2e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140003f33  mov     rdx, rbx; unsigned __int16 *
0x140003f36  lea     rcx, [rbp+1400h+OutputString]; this
0x140003f3d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003f42  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140003f49  call    cs:__imp_OutputDebugStringW
0x140003f50  nop     dword ptr [rax+rax+00h]
0x140003f55  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140003f5a  jnz     short loc_140003F65
0x140003f5c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140003f63  jz      short loc_140003F77
0x140003f65  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003f6c  test    rax, rax
0x140003f6f  jz      short loc_140003F77
0x140003f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f76  nop
0x140003f77  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140003f7c  jnz     short loc_140003FA0
0x140003f7e  mov     rcx, [rbp+1400h+var_40]
0x140003f85  xor     rcx, rsp; StackCookie
0x140003f88  call    __security_check_cookie
0x140003f8d  add     rsp, 14D0h
0x140003f94  pop     r15
0x140003f96  pop     r14
0x140003f98  pop     r12
0x140003f9a  pop     rdi
0x140003f9b  pop     rsi
0x140003f9c  pop     rbx
0x140003f9d  pop     rbp
0x140003f9e  retn
0x140003fa0  lea     rcx, [rsp+1500h+var_14E0]; this
0x140003fa5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140003fab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
