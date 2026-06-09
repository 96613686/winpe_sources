# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180047c88`
- end: `0x180047f2f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180047a18`

## callees

- `0x180047c88`
- `0x180048764`
- `0x180049714`
- `0x180049ce0`
- `0x180049dbc`
- `0x180079436`
- `0x180079490`
- `0x180079520`
- `0x18007a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180047e33`
- `KERNEL32!IsDebuggerPresent` at `0x180047e33`
- `KERNEL32!OutputDebugStringW` at `0x180047ec3`
- `KERNEL32!OutputDebugStringW` at `0x180047ec3`
- `KERNEL32!GetCurrentThreadId` at `0x180047d32`
- `KERNEL32!GetCurrentThreadId` at `0x180047d32`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
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
  v28 = "wil";
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
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
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180047c88  mov     [rsp-8+arg_10], rbx
0x180047c8d  push    rbp
0x180047c8e  push    rsi
0x180047c8f  push    rdi
0x180047c90  push    r14
0x180047c92  push    r15
0x180047c94  lea     rbp, [rsp-13D0h]
0x180047c9c  mov     eax, 14D0h
0x180047ca1  call    _alloca_probe
0x180047ca6  sub     rsp, rax
0x180047ca9  mov     rax, cs:__security_cookie
0x180047cb0  xor     rax, rsp
0x180047cb3  mov     [rbp+13F0h+var_30], rax
0x180047cba  mov     rdi, [rbp+13F0h+arg_28]
0x180047cc1  mov     esi, edx
0x180047cc3  mov     r14, rcx
0x180047cc6  xor     edx, edx; Val
0x180047cc8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180047ccd  mov     r8d, 98h; Size
0x180047cd3  call    memset_0
0x180047cd8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180047cdf  xor     r15d, r15d
0x180047ce2  mov     [rbp+13F0h+OutputString], r15w
0x180047cea  mov     [rbp+13F0h+var_1430], r15b
0x180047cee  mov     ecx, [rdx]; this
0x180047cf0  mov     eax, [rdx+4]
0x180047cf3  mov     [rsp+14F0h+var_14C8], ecx
0x180047cf7  mov     [rsp+14F0h+var_14C4], eax
0x180047cfb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180047d00  cmp     dword ptr [rdx+8], 1
0x180047d04  mov     ebx, eax
0x180047d06  lea     eax, [r15+8]
0x180047d0a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180047d12  mov     ecx, r15d
0x180047d15  cmovz   ecx, eax
0x180047d18  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180047d1c  lea     ecx, [rax-7]
0x180047d1f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180047d27  inc     ecx
0x180047d29  mov     [rsp+14F0h+var_14B8], r15
0x180047d2e  mov     [rsp+14F0h+var_14C0], ecx
0x180047d32  call    cs:__imp_GetCurrentThreadId
0x180047d39  nop     dword ptr [rax+rax+00h]
0x180047d3e  xorps   xmm0, xmm0
0x180047d41  mov     [rsp+14F0h+var_1490], esi
0x180047d45  mov     [rsp+14F0h+var_14B0], eax
0x180047d49  xorps   xmm1, xmm1
0x180047d4c  lea     rax, aWil; "wil"
0x180047d53  mov     [rsp+14F0h+var_148C], ebx
0x180047d57  mov     [rsp+14F0h+var_1498], rax
0x180047d5c  xor     eax, eax
0x180047d5e  mov     [rbp+13F0h+var_1458], rax
0x180047d62  mov     [rbp+13F0h+var_1470], rax
0x180047d66  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180047d6d  mov     [rsp+14F0h+var_14A8], r15
0x180047d72  mov     [rsp+14F0h+var_14A0], r15
0x180047d77  mov     [rbp+13F0h+var_1448], rdi
0x180047d7b  mov     [rbp+13F0h+var_1440], r14
0x180047d7f  mov     [rsp+14F0h+var_1488], r15
0x180047d84  movups  [rbp+13F0h+var_1468], xmm0
0x180047d88  movups  [rsp+14F0h+var_1480], xmm1
0x180047d8d  test    rax, rax
0x180047d90  jz      short loc_180047D9D
0x180047d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d97  mov     [rbp+13F0h+var_1450], rax
0x180047d9b  jmp     short loc_180047DA1
0x180047d9d  mov     [rbp+13F0h+var_1450], r15
0x180047da1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180047da8  test    rax, rax
0x180047dab  jz      short loc_180047DB7
0x180047dad  lea     rcx, [rsp+14F0h+var_14D0]
0x180047db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047db7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180047dbe  test    rax, rax
0x180047dc1  jz      short loc_180047DD7
0x180047dc3  mov     r8d, 400h
0x180047dc9  lea     rdx, [rbp+13F0h+var_1430]
0x180047dcd  lea     rcx, [rsp+14F0h+var_14D0]
0x180047dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dd7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180047dde  test    rax, rax
0x180047de1  jz      short loc_180047DED
0x180047de3  lea     rcx, [rsp+14F0h+var_14D0]
0x180047de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ded  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180047df4  test    rax, rax
0x180047df7  jz      short loc_180047E0A
0x180047df9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180047dfe  jnz     short loc_180047E0A
0x180047e00  lea     rcx, [rsp+14F0h+var_14D0]
0x180047e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e0a  cmp     [rsp+14F0h+var_14C8], r15d
0x180047e0f  jge     loc_180047F1E
0x180047e15  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180047e1c  jnz     short loc_180047E43
0x180047e1e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180047e25  test    rax, rax
0x180047e28  jz      short loc_180047E33
0x180047e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e2f  test    al, al
0x180047e31  jmp     short loc_180047E41
0x180047e33  call    cs:__imp_IsDebuggerPresent
0x180047e3a  nop     dword ptr [rax+rax+00h]
0x180047e3f  test    eax, eax
0x180047e41  jz      short loc_180047E4A
0x180047e43  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180047e48  jz      short loc_180047E70
0x180047e4a  mov     rax, cs:g_pfnResultLoggingCallback
0x180047e51  test    rax, rax
0x180047e54  jz      short loc_180047ECF
0x180047e56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180047e5d  jnz     short loc_180047ECF
0x180047e5f  xor     r8d, r8d
0x180047e62  lea     rcx, [rsp+14F0h+var_14D0]
0x180047e67  xor     edx, edx
0x180047e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e6e  jmp     short loc_180047ECF
0x180047e70  mov     rax, cs:g_pfnResultLoggingCallback
0x180047e77  mov     ebx, 800h
0x180047e7c  test    rax, rax
0x180047e7f  jz      short loc_180047E9E
0x180047e81  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180047e88  jnz     short loc_180047E9E
0x180047e8a  mov     r8d, ebx
0x180047e8d  lea     rdx, [rbp+13F0h+OutputString]
0x180047e94  lea     rcx, [rsp+14F0h+var_14D0]
0x180047e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e9e  cmp     [rbp+13F0h+OutputString], r15w
0x180047ea6  jnz     short loc_180047EBC
0x180047ea8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180047ead  mov     rdx, rbx; unsigned __int16 *
0x180047eb0  lea     rcx, [rbp+13F0h+OutputString]; this
0x180047eb7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180047ebc  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180047ec3  call    cs:__imp_OutputDebugStringW
0x180047eca  nop     dword ptr [rax+rax+00h]
0x180047ecf  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180047ed4  jnz     short loc_180047EDF
0x180047ed6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180047edd  jz      short loc_180047EF0
0x180047edf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180047ee6  test    rax, rax
0x180047ee9  jz      short loc_180047EF0
0x180047eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ef0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180047ef5  jnz     short loc_180047F24
0x180047ef7  mov     rcx, [rbp+13F0h+var_30]
0x180047efe  xor     rcx, rsp; StackCookie
0x180047f01  call    __security_check_cookie
0x180047f06  mov     rbx, [rsp+14F0h+arg_10]
0x180047f0e  add     rsp, 14D0h
0x180047f15  pop     r15
0x180047f17  pop     r14
0x180047f19  pop     rdi
0x180047f1a  pop     rsi
0x180047f1b  pop     rbp
0x180047f1c  retn
0x180047f1e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180047f24  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180047f29  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
