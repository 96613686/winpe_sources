# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000ce94`
- end: `0x18000d12a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000c99c`

## callees

- `0x18000ce94`
- `0x18000e894`
- `0x180010470`
- `0x180011c10`
- `0x180011dcc`
- `0x1800131a2`
- `0x1800131e0`
- `0x1800132a0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf3f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d0c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d0c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d03a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d03a`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
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
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x18000ce94  mov     [rsp-8+arg_10], rbx
0x18000ce99  push    rbp
0x18000ce9a  push    rsi
0x18000ce9b  push    rdi
0x18000ce9c  push    r14
0x18000ce9e  push    r15
0x18000cea0  lea     rbp, [rsp-13D0h]
0x18000cea8  mov     eax, 14D0h
0x18000cead  call    _alloca_probe
0x18000ceb2  sub     rsp, rax
0x18000ceb5  mov     rax, cs:__security_cookie
0x18000cebc  xor     rax, rsp
0x18000cebf  mov     [rbp+13F0h+var_30], rax
0x18000cec6  mov     esi, edx
0x18000cec8  mov     r14, rcx
0x18000cecb  mov     rdi, [rbp+13F0h+arg_28]
0x18000ced2  xor     edx, edx; Val
0x18000ced4  mov     r8d, 98h; Size
0x18000ceda  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000cedf  call    memset_0
0x18000cee4  nop
0x18000cee5  xor     r15d, r15d
0x18000cee8  mov     [rbp+13F0h+OutputString], r15w
0x18000cef0  mov     [rbp+13F0h+var_1430], r15b
0x18000cef4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000cefb  mov     ecx, [rdx]; this
0x18000cefd  mov     [rsp+14F0h+var_14C8], ecx
0x18000cf01  mov     eax, [rdx+4]
0x18000cf04  mov     [rsp+14F0h+var_14C4], eax
0x18000cf08  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000cf0d  mov     ebx, eax
0x18000cf0f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000cf17  mov     ecx, r15d
0x18000cf1a  lea     eax, [r15+8]
0x18000cf1e  cmp     dword ptr [rdx+8], 1
0x18000cf22  cmovz   ecx, eax
0x18000cf25  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000cf29  lea     ecx, [rax-7]
0x18000cf2c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000cf34  inc     ecx
0x18000cf36  mov     [rsp+14F0h+var_14C0], ecx
0x18000cf3a  mov     [rsp+14F0h+var_14B8], r15
0x18000cf3f  call    cs:__imp_GetCurrentThreadId
0x18000cf45  mov     [rsp+14F0h+var_14B0], eax
0x18000cf49  lea     rax, aWil; "wil"
0x18000cf50  mov     [rsp+14F0h+var_1498], rax
0x18000cf55  mov     [rsp+14F0h+var_1490], esi
0x18000cf59  mov     [rsp+14F0h+var_148C], ebx
0x18000cf5d  mov     [rsp+14F0h+var_14A8], r15
0x18000cf62  mov     [rsp+14F0h+var_14A0], r15
0x18000cf67  mov     [rbp+13F0h+var_1448], rdi
0x18000cf6b  mov     [rbp+13F0h+var_1440], r14
0x18000cf6f  mov     [rsp+14F0h+var_1488], r15
0x18000cf74  xorps   xmm0, xmm0
0x18000cf77  xor     eax, eax
0x18000cf79  movups  [rbp+13F0h+var_1468], xmm0
0x18000cf7d  mov     [rbp+13F0h+var_1458], rax
0x18000cf81  xorps   xmm1, xmm1
0x18000cf84  movups  [rsp+14F0h+var_1480], xmm1
0x18000cf89  mov     [rbp+13F0h+var_1470], rax
0x18000cf8d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cf94  test    rax, rax
0x18000cf97  jz      short loc_18000CFA4
0x18000cf99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf9e  mov     [rbp+13F0h+var_1450], rax
0x18000cfa2  jmp     short loc_18000CFA8
0x18000cfa4  mov     [rbp+13F0h+var_1450], r15
0x18000cfa8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000cfaf  test    rax, rax
0x18000cfb2  jz      short loc_18000CFBE
0x18000cfb4  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cfb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfbe  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000cfc5  test    rax, rax
0x18000cfc8  jz      short loc_18000CFDE
0x18000cfca  mov     r8d, 400h
0x18000cfd0  lea     rdx, [rbp+13F0h+var_1430]
0x18000cfd4  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfde  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cfe5  test    rax, rax
0x18000cfe8  jz      short loc_18000CFF4
0x18000cfea  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cfef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cff4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cffb  test    rax, rax
0x18000cffe  jz      short loc_18000D011
0x18000d000  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000d005  jnz     short loc_18000D011
0x18000d007  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d011  cmp     [rsp+14F0h+var_14C8], r15d
0x18000d016  jge     loc_18000D124
0x18000d01c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000d023  jnz     short loc_18000D044
0x18000d025  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d02c  test    rax, rax
0x18000d02f  jz      short loc_18000D03A
0x18000d031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d036  test    al, al
0x18000d038  jmp     short loc_18000D042
0x18000d03a  call    cs:__imp_IsDebuggerPresent
0x18000d040  test    eax, eax
0x18000d042  jz      short loc_18000D04B
0x18000d044  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000d049  jz      short loc_18000D071
0x18000d04b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d052  test    rax, rax
0x18000d055  jz      short loc_18000D0CA
0x18000d057  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000d05e  jnz     short loc_18000D0CA
0x18000d060  xor     r8d, r8d
0x18000d063  xor     edx, edx
0x18000d065  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d06f  jmp     short loc_18000D0CA
0x18000d071  mov     ebx, 800h
0x18000d076  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d07d  test    rax, rax
0x18000d080  jz      short loc_18000D09F
0x18000d082  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000d089  jnz     short loc_18000D09F
0x18000d08b  mov     r8d, ebx
0x18000d08e  lea     rdx, [rbp+13F0h+OutputString]
0x18000d095  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d09a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d09f  cmp     [rbp+13F0h+OutputString], r15w
0x18000d0a7  jnz     short loc_18000D0BD
0x18000d0a9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000d0ae  mov     rdx, rbx; unsigned __int16 *
0x18000d0b1  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000d0b8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000d0bd  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000d0c4  call    cs:__imp_OutputDebugStringW
0x18000d0ca  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000d0cf  jnz     short loc_18000D0DA
0x18000d0d1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000d0d8  jz      short loc_18000D0EC
0x18000d0da  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d0e1  test    rax, rax
0x18000d0e4  jz      short loc_18000D0EC
0x18000d0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0eb  nop
0x18000d0ec  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000d0f1  jnz     short loc_18000D119
0x18000d0f3  mov     rcx, [rbp+13F0h+var_30]
0x18000d0fa  xor     rcx, rsp; StackCookie
0x18000d0fd  call    __security_check_cookie
0x18000d102  mov     rbx, [rsp+14F0h+arg_10]
0x18000d10a  add     rsp, 14D0h
0x18000d111  pop     r15
0x18000d113  pop     r14
0x18000d115  pop     rdi
0x18000d116  pop     rsi
0x18000d117  pop     rbp
0x18000d118  retn
0x18000d119  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d11e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d124  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
