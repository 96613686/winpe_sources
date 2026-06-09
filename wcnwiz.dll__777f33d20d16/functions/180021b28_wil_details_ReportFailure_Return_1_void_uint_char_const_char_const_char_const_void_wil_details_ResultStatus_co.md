# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180021b28`
- end: `0x180021dbe`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800217f0`

## callees

- `0x180001820`
- `0x180002294`
- `0x180021b28`
- `0x1800229c4`
- `0x180023c20`
- `0x1800249b8`
- `0x180024a94`
- `0x18002f7b0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021bd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021bd3`
- `KERNEL32!OutputDebugStringW` at `0x180021d58`
- `KERNEL32!OutputDebugStringW` at `0x180021d58`
- `KERNEL32!IsDebuggerPresent` at `0x180021cce`
- `KERNEL32!IsDebuggerPresent` at `0x180021cce`

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
0x180021b28  mov     [rsp-8+arg_10], rbx
0x180021b2d  push    rbp
0x180021b2e  push    rsi
0x180021b2f  push    rdi
0x180021b30  push    r14
0x180021b32  push    r15
0x180021b34  lea     rbp, [rsp-13D0h]
0x180021b3c  mov     eax, 14D0h
0x180021b41  call    _alloca_probe
0x180021b46  sub     rsp, rax
0x180021b49  mov     rax, cs:__security_cookie
0x180021b50  xor     rax, rsp
0x180021b53  mov     [rbp+13F0h+var_30], rax
0x180021b5a  mov     esi, edx
0x180021b5c  mov     r14, rcx
0x180021b5f  mov     rdi, [rbp+13F0h+arg_28]
0x180021b66  xor     edx, edx; Val
0x180021b68  mov     r8d, 98h; Size
0x180021b6e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180021b73  call    memset_0
0x180021b78  nop
0x180021b79  xor     r15d, r15d
0x180021b7c  mov     [rbp+13F0h+OutputString], r15w
0x180021b84  mov     [rbp+13F0h+var_1430], r15b
0x180021b88  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180021b8f  mov     ecx, [rdx]; this
0x180021b91  mov     [rsp+14F0h+var_14C8], ecx
0x180021b95  mov     eax, [rdx+4]
0x180021b98  mov     [rsp+14F0h+var_14C4], eax
0x180021b9c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180021ba1  mov     ebx, eax
0x180021ba3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180021bab  mov     ecx, r15d
0x180021bae  lea     eax, [r15+8]
0x180021bb2  cmp     dword ptr [rdx+8], 1
0x180021bb6  cmovz   ecx, eax
0x180021bb9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180021bbd  lea     ecx, [rax-7]
0x180021bc0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180021bc8  inc     ecx
0x180021bca  mov     [rsp+14F0h+var_14C0], ecx
0x180021bce  mov     [rsp+14F0h+var_14B8], r15
0x180021bd3  call    cs:__imp_GetCurrentThreadId
0x180021bd9  mov     [rsp+14F0h+var_14B0], eax
0x180021bdd  lea     rax, aWil; "wil"
0x180021be4  mov     [rsp+14F0h+var_1498], rax
0x180021be9  mov     [rsp+14F0h+var_1490], esi
0x180021bed  mov     [rsp+14F0h+var_148C], ebx
0x180021bf1  mov     [rsp+14F0h+var_14A8], r15
0x180021bf6  mov     [rsp+14F0h+var_14A0], r15
0x180021bfb  mov     [rbp+13F0h+var_1448], rdi
0x180021bff  mov     [rbp+13F0h+var_1440], r14
0x180021c03  mov     [rsp+14F0h+var_1488], r15
0x180021c08  xorps   xmm0, xmm0
0x180021c0b  xor     eax, eax
0x180021c0d  movups  [rbp+13F0h+var_1468], xmm0
0x180021c11  mov     [rbp+13F0h+var_1458], rax
0x180021c15  xorps   xmm1, xmm1
0x180021c18  movups  [rsp+14F0h+var_1480], xmm1
0x180021c1d  mov     [rbp+13F0h+var_1470], rax
0x180021c21  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180021c28  test    rax, rax
0x180021c2b  jz      short loc_180021C38
0x180021c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c32  mov     [rbp+13F0h+var_1450], rax
0x180021c36  jmp     short loc_180021C3C
0x180021c38  mov     [rbp+13F0h+var_1450], r15
0x180021c3c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180021c43  test    rax, rax
0x180021c46  jz      short loc_180021C52
0x180021c48  lea     rcx, [rsp+14F0h+var_14D0]
0x180021c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c52  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180021c59  test    rax, rax
0x180021c5c  jz      short loc_180021C72
0x180021c5e  mov     r8d, 400h
0x180021c64  lea     rdx, [rbp+13F0h+var_1430]
0x180021c68  lea     rcx, [rsp+14F0h+var_14D0]
0x180021c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c72  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021c79  test    rax, rax
0x180021c7c  jz      short loc_180021C88
0x180021c7e  lea     rcx, [rsp+14F0h+var_14D0]
0x180021c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c88  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021c8f  test    rax, rax
0x180021c92  jz      short loc_180021CA5
0x180021c94  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180021c99  jnz     short loc_180021CA5
0x180021c9b  lea     rcx, [rsp+14F0h+var_14D0]
0x180021ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ca5  cmp     [rsp+14F0h+var_14C8], r15d
0x180021caa  jge     loc_180021DB8
0x180021cb0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180021cb7  jnz     short loc_180021CD8
0x180021cb9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180021cc0  test    rax, rax
0x180021cc3  jz      short loc_180021CCE
0x180021cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cca  test    al, al
0x180021ccc  jmp     short loc_180021CD6
0x180021cce  call    cs:__imp_IsDebuggerPresent
0x180021cd4  test    eax, eax
0x180021cd6  jz      short loc_180021CDF
0x180021cd8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180021cdd  jz      short loc_180021D05
0x180021cdf  mov     rax, cs:g_pfnResultLoggingCallback
0x180021ce6  test    rax, rax
0x180021ce9  jz      short loc_180021D5E
0x180021ceb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180021cf2  jnz     short loc_180021D5E
0x180021cf4  xor     r8d, r8d
0x180021cf7  xor     edx, edx
0x180021cf9  lea     rcx, [rsp+14F0h+var_14D0]
0x180021cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d03  jmp     short loc_180021D5E
0x180021d05  mov     ebx, 800h
0x180021d0a  mov     rax, cs:g_pfnResultLoggingCallback
0x180021d11  test    rax, rax
0x180021d14  jz      short loc_180021D33
0x180021d16  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180021d1d  jnz     short loc_180021D33
0x180021d1f  mov     r8d, ebx
0x180021d22  lea     rdx, [rbp+13F0h+OutputString]
0x180021d29  lea     rcx, [rsp+14F0h+var_14D0]
0x180021d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d33  cmp     [rbp+13F0h+OutputString], r15w
0x180021d3b  jnz     short loc_180021D51
0x180021d3d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180021d42  mov     rdx, rbx; unsigned __int16 *
0x180021d45  lea     rcx, [rbp+13F0h+OutputString]; this
0x180021d4c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180021d51  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180021d58  call    cs:__imp_OutputDebugStringW
0x180021d5e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180021d63  jnz     short loc_180021D6E
0x180021d65  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180021d6c  jz      short loc_180021D80
0x180021d6e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180021d75  test    rax, rax
0x180021d78  jz      short loc_180021D80
0x180021d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d7f  nop
0x180021d80  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180021d85  jnz     short loc_180021DAD
0x180021d87  mov     rcx, [rbp+13F0h+var_30]
0x180021d8e  xor     rcx, rsp; StackCookie
0x180021d91  call    __security_check_cookie
0x180021d96  mov     rbx, [rsp+14F0h+arg_10]
0x180021d9e  add     rsp, 14D0h
0x180021da5  pop     r15
0x180021da7  pop     r14
0x180021da9  pop     rdi
0x180021daa  pop     rsi
0x180021dab  pop     rbp
0x180021dac  retn
0x180021dad  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180021db2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180021db8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
