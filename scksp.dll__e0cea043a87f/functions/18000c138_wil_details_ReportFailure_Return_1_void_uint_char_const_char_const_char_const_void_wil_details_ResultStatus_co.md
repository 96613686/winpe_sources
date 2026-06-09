# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000c138`
- end: `0x18000c3ce`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000bdcc`

## callees

- `0x180009e82`
- `0x18000c138`
- `0x18000e0a4`
- `0x18000ffe0`
- `0x180011ea8`
- `0x180012228`
- `0x18003c240`
- `0x18003c300`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c1e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c1e3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c368`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c368`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c2de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c2de`

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
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
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
0x18000c138  mov     [rsp-8+arg_10], rbx
0x18000c13d  push    rbp
0x18000c13e  push    rsi
0x18000c13f  push    rdi
0x18000c140  push    r14
0x18000c142  push    r15
0x18000c144  lea     rbp, [rsp-13D0h]
0x18000c14c  mov     eax, 14D0h
0x18000c151  call    _alloca_probe
0x18000c156  sub     rsp, rax
0x18000c159  mov     rax, cs:__security_cookie
0x18000c160  xor     rax, rsp
0x18000c163  mov     [rbp+13F0h+var_30], rax
0x18000c16a  mov     esi, edx
0x18000c16c  mov     r14, rcx
0x18000c16f  mov     rdi, [rbp+13F0h+arg_28]
0x18000c176  xor     edx, edx; Val
0x18000c178  mov     r8d, 98h; Size
0x18000c17e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000c183  call    memset_0
0x18000c188  nop
0x18000c189  xor     r15d, r15d
0x18000c18c  mov     [rbp+13F0h+OutputString], r15w
0x18000c194  mov     [rbp+13F0h+var_1430], r15b
0x18000c198  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000c19f  mov     ecx, [rdx]; this
0x18000c1a1  mov     [rsp+14F0h+var_14C8], ecx
0x18000c1a5  mov     eax, [rdx+4]
0x18000c1a8  mov     [rsp+14F0h+var_14C4], eax
0x18000c1ac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000c1b1  mov     ebx, eax
0x18000c1b3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000c1bb  mov     ecx, r15d
0x18000c1be  lea     eax, [r15+8]
0x18000c1c2  cmp     dword ptr [rdx+8], 1
0x18000c1c6  cmovz   ecx, eax
0x18000c1c9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000c1cd  lea     ecx, [rax-7]
0x18000c1d0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c1d8  inc     ecx
0x18000c1da  mov     [rsp+14F0h+var_14C0], ecx
0x18000c1de  mov     [rsp+14F0h+var_14B8], r15
0x18000c1e3  call    cs:__imp_GetCurrentThreadId
0x18000c1e9  mov     [rsp+14F0h+var_14B0], eax
0x18000c1ed  lea     rax, aWil; "wil"
0x18000c1f4  mov     [rsp+14F0h+var_1498], rax
0x18000c1f9  mov     [rsp+14F0h+var_1490], esi
0x18000c1fd  mov     [rsp+14F0h+var_148C], ebx
0x18000c201  mov     [rsp+14F0h+var_14A8], r15
0x18000c206  mov     [rsp+14F0h+var_14A0], r15
0x18000c20b  mov     [rbp+13F0h+var_1448], rdi
0x18000c20f  mov     [rbp+13F0h+var_1440], r14
0x18000c213  mov     [rsp+14F0h+var_1488], r15
0x18000c218  xorps   xmm0, xmm0
0x18000c21b  xor     eax, eax
0x18000c21d  movups  [rbp+13F0h+var_1468], xmm0
0x18000c221  mov     [rbp+13F0h+var_1458], rax
0x18000c225  xorps   xmm1, xmm1
0x18000c228  movups  [rsp+14F0h+var_1480], xmm1
0x18000c22d  mov     [rbp+13F0h+var_1470], rax
0x18000c231  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c238  test    rax, rax
0x18000c23b  jz      short loc_18000C248
0x18000c23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c242  mov     [rbp+13F0h+var_1450], rax
0x18000c246  jmp     short loc_18000C24C
0x18000c248  mov     [rbp+13F0h+var_1450], r15
0x18000c24c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c253  test    rax, rax
0x18000c256  jz      short loc_18000C262
0x18000c258  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c262  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c269  test    rax, rax
0x18000c26c  jz      short loc_18000C282
0x18000c26e  mov     r8d, 400h
0x18000c274  lea     rdx, [rbp+13F0h+var_1430]
0x18000c278  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c282  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c289  test    rax, rax
0x18000c28c  jz      short loc_18000C298
0x18000c28e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c298  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c29f  test    rax, rax
0x18000c2a2  jz      short loc_18000C2B5
0x18000c2a4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000c2a9  jnz     short loc_18000C2B5
0x18000c2ab  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2b5  cmp     [rsp+14F0h+var_14C8], r15d
0x18000c2ba  jge     loc_18000C3C8
0x18000c2c0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000c2c7  jnz     short loc_18000C2E8
0x18000c2c9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c2d0  test    rax, rax
0x18000c2d3  jz      short loc_18000C2DE
0x18000c2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2da  test    al, al
0x18000c2dc  jmp     short loc_18000C2E6
0x18000c2de  call    cs:__imp_IsDebuggerPresent
0x18000c2e4  test    eax, eax
0x18000c2e6  jz      short loc_18000C2EF
0x18000c2e8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000c2ed  jz      short loc_18000C315
0x18000c2ef  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c2f6  test    rax, rax
0x18000c2f9  jz      short loc_18000C36E
0x18000c2fb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000c302  jnz     short loc_18000C36E
0x18000c304  xor     r8d, r8d
0x18000c307  xor     edx, edx
0x18000c309  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c313  jmp     short loc_18000C36E
0x18000c315  mov     ebx, 800h
0x18000c31a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c321  test    rax, rax
0x18000c324  jz      short loc_18000C343
0x18000c326  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000c32d  jnz     short loc_18000C343
0x18000c32f  mov     r8d, ebx
0x18000c332  lea     rdx, [rbp+13F0h+OutputString]
0x18000c339  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c343  cmp     [rbp+13F0h+OutputString], r15w
0x18000c34b  jnz     short loc_18000C361
0x18000c34d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000c352  mov     rdx, rbx; unsigned __int16 *
0x18000c355  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x18000c35c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c361  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000c368  call    cs:__imp_OutputDebugStringW
0x18000c36e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000c373  jnz     short loc_18000C37E
0x18000c375  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000c37c  jz      short loc_18000C390
0x18000c37e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c385  test    rax, rax
0x18000c388  jz      short loc_18000C390
0x18000c38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c38f  nop
0x18000c390  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000c395  jnz     short loc_18000C3BD
0x18000c397  mov     rcx, [rbp+13F0h+var_30]
0x18000c39e  xor     rcx, rsp; StackCookie
0x18000c3a1  call    __security_check_cookie
0x18000c3a6  mov     rbx, [rsp+14F0h+arg_10]
0x18000c3ae  add     rsp, 14D0h
0x18000c3b5  pop     r15
0x18000c3b7  pop     r14
0x18000c3b9  pop     rdi
0x18000c3ba  pop     rsi
0x18000c3bb  pop     rbp
0x18000c3bc  retn
0x18000c3bd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c3c2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000c3c8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
