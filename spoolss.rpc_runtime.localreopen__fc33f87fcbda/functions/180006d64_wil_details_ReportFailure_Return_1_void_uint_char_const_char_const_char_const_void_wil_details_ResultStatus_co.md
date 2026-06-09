# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006d64`
- end: `0x18000700d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004f80`

## callees

- `0x180005680`
- `0x18000601c`
- `0x180006d64`
- `0x180008c64`
- `0x18000a4c4`
- `0x18000c1b0`
- `0x18000c3c0`
- `0x1800169d0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e0f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006f10`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006f10`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006fa0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006fa0`

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
0x180006d64  mov     [rsp-8+arg_10], rbx
0x180006d69  push    rbp
0x180006d6a  push    rsi
0x180006d6b  push    rdi
0x180006d6c  push    r14
0x180006d6e  push    r15
0x180006d70  lea     rbp, [rsp-13D0h]
0x180006d78  mov     eax, 14D0h
0x180006d7d  call    _alloca_probe
0x180006d82  sub     rsp, rax
0x180006d85  mov     rax, cs:__security_cookie
0x180006d8c  xor     rax, rsp
0x180006d8f  mov     [rbp+13F0h+var_30], rax
0x180006d96  mov     esi, edx
0x180006d98  mov     r14, rcx
0x180006d9b  mov     rdi, [rbp+13F0h+arg_28]
0x180006da2  xor     edx, edx; Val
0x180006da4  mov     r8d, 98h; Size
0x180006daa  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006daf  call    memset_0
0x180006db4  nop
0x180006db5  xor     r15d, r15d
0x180006db8  mov     [rbp+13F0h+OutputString], r15w
0x180006dc0  mov     [rbp+13F0h+var_1430], r15b
0x180006dc4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180006dcb  mov     ecx, [rdx]; this
0x180006dcd  mov     [rsp+14F0h+var_14C8], ecx
0x180006dd1  mov     eax, [rdx+4]
0x180006dd4  mov     [rsp+14F0h+var_14C4], eax
0x180006dd8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006ddd  mov     ebx, eax
0x180006ddf  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180006de7  mov     ecx, r15d
0x180006dea  lea     eax, [r15+8]
0x180006dee  cmp     dword ptr [rdx+8], 1
0x180006df2  cmovz   ecx, eax
0x180006df5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006df9  lea     ecx, [rax-7]
0x180006dfc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006e04  inc     ecx
0x180006e06  mov     [rsp+14F0h+var_14C0], ecx
0x180006e0a  mov     [rsp+14F0h+var_14B8], r15
0x180006e0f  call    cs:__imp_GetCurrentThreadId
0x180006e16  nop     dword ptr [rax+rax+00h]
0x180006e1b  mov     [rsp+14F0h+var_14B0], eax
0x180006e1f  lea     rax, aWil; "wil"
0x180006e26  mov     [rsp+14F0h+var_1498], rax
0x180006e2b  mov     [rsp+14F0h+var_1490], esi
0x180006e2f  mov     [rsp+14F0h+var_148C], ebx
0x180006e33  mov     [rsp+14F0h+var_14A8], r15
0x180006e38  mov     [rsp+14F0h+var_14A0], r15
0x180006e3d  mov     [rbp+13F0h+var_1448], rdi
0x180006e41  mov     [rbp+13F0h+var_1440], r14
0x180006e45  mov     [rsp+14F0h+var_1488], r15
0x180006e4a  xorps   xmm0, xmm0
0x180006e4d  xor     eax, eax
0x180006e4f  movups  [rbp+13F0h+var_1468], xmm0
0x180006e53  mov     [rbp+13F0h+var_1458], rax
0x180006e57  xorps   xmm1, xmm1
0x180006e5a  movups  [rsp+14F0h+var_1480], xmm1
0x180006e5f  mov     [rbp+13F0h+var_1470], rax
0x180006e63  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006e6a  test    rax, rax
0x180006e6d  jz      short loc_180006E7A
0x180006e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e74  mov     [rbp+13F0h+var_1450], rax
0x180006e78  jmp     short loc_180006E7E
0x180006e7a  mov     [rbp+13F0h+var_1450], r15
0x180006e7e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006e85  test    rax, rax
0x180006e88  jz      short loc_180006E94
0x180006e8a  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e94  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006e9b  test    rax, rax
0x180006e9e  jz      short loc_180006EB4
0x180006ea0  mov     r8d, 400h
0x180006ea6  lea     rdx, [rbp+13F0h+var_1430]
0x180006eaa  lea     rcx, [rsp+14F0h+var_14D0]
0x180006eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eb4  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006ebb  test    rax, rax
0x180006ebe  jz      short loc_180006ECA
0x180006ec0  lea     rcx, [rsp+14F0h+var_14D0]
0x180006ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eca  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006ed1  test    rax, rax
0x180006ed4  jz      short loc_180006EE7
0x180006ed6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006edb  jnz     short loc_180006EE7
0x180006edd  lea     rcx, [rsp+14F0h+var_14D0]
0x180006ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ee7  cmp     [rsp+14F0h+var_14C8], r15d
0x180006eec  jge     loc_180007007
0x180006ef2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180006ef9  jnz     short loc_180006F20
0x180006efb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006f02  test    rax, rax
0x180006f05  jz      short loc_180006F10
0x180006f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f0c  test    al, al
0x180006f0e  jmp     short loc_180006F1E
0x180006f10  call    cs:__imp_IsDebuggerPresent
0x180006f17  nop     dword ptr [rax+rax+00h]
0x180006f1c  test    eax, eax
0x180006f1e  jz      short loc_180006F27
0x180006f20  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006f25  jz      short loc_180006F4D
0x180006f27  mov     rax, cs:g_pfnResultLoggingCallback
0x180006f2e  test    rax, rax
0x180006f31  jz      short loc_180006FAC
0x180006f33  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006f3a  jnz     short loc_180006FAC
0x180006f3c  xor     r8d, r8d
0x180006f3f  xor     edx, edx
0x180006f41  lea     rcx, [rsp+14F0h+var_14D0]
0x180006f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f4b  jmp     short loc_180006FAC
0x180006f4d  mov     ebx, 800h
0x180006f52  mov     rax, cs:g_pfnResultLoggingCallback
0x180006f59  test    rax, rax
0x180006f5c  jz      short loc_180006F7B
0x180006f5e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006f65  jnz     short loc_180006F7B
0x180006f67  mov     r8d, ebx
0x180006f6a  lea     rdx, [rbp+13F0h+OutputString]
0x180006f71  lea     rcx, [rsp+14F0h+var_14D0]
0x180006f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f7b  cmp     [rbp+13F0h+OutputString], r15w
0x180006f83  jnz     short loc_180006F99
0x180006f85  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006f8a  mov     rdx, rbx; unsigned __int16 *
0x180006f8d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006f94  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006f99  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006fa0  call    cs:__imp_OutputDebugStringW
0x180006fa7  nop     dword ptr [rax+rax+00h]
0x180006fac  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006fb1  jnz     short loc_180006FBC
0x180006fb3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180006fba  jz      short loc_180006FCE
0x180006fbc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006fc3  test    rax, rax
0x180006fc6  jz      short loc_180006FCE
0x180006fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fcd  nop
0x180006fce  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180006fd3  jnz     short loc_180006FFC
0x180006fd5  mov     rcx, [rbp+13F0h+var_30]
0x180006fdc  xor     rcx, rsp; StackCookie
0x180006fdf  call    __security_check_cookie
0x180006fe4  mov     rbx, [rsp+14F0h+arg_10]
0x180006fec  add     rsp, 14D0h
0x180006ff3  pop     r15
0x180006ff5  pop     r14
0x180006ff7  pop     rdi
0x180006ff8  pop     rsi
0x180006ff9  pop     rbp
0x180006ffa  retn
0x180006ffc  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007001  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007007  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
