# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18003e564`
- end: `0x18003e80b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003c420`

## callees

- `0x18003cb60`
- `0x18003d4b0`
- `0x18003e564`
- `0x180041bc4`
- `0x180043c24`
- `0x180046d20`
- `0x180046edc`
- `0x180057c40`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e60e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e60e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003e70f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003e70f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003e79f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003e79f`

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
0x18003e564  mov     [rsp-8+arg_10], rbx
0x18003e569  push    rbp
0x18003e56a  push    rsi
0x18003e56b  push    rdi
0x18003e56c  push    r14
0x18003e56e  push    r15
0x18003e570  lea     rbp, [rsp-13D0h]
0x18003e578  mov     eax, 14D0h
0x18003e57d  call    _alloca_probe
0x18003e582  sub     rsp, rax
0x18003e585  mov     rax, cs:__security_cookie
0x18003e58c  xor     rax, rsp
0x18003e58f  mov     [rbp+13F0h+var_30], rax
0x18003e596  mov     rdi, [rbp+13F0h+arg_28]
0x18003e59d  mov     esi, edx
0x18003e59f  mov     r14, rcx
0x18003e5a2  xor     edx, edx; Val
0x18003e5a4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18003e5a9  mov     r8d, 98h; Size
0x18003e5af  call    memset_0
0x18003e5b4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18003e5bb  xor     r15d, r15d
0x18003e5be  mov     [rbp+13F0h+OutputString], r15w
0x18003e5c6  mov     [rbp+13F0h+var_1430], r15b
0x18003e5ca  mov     ecx, [rdx]; this
0x18003e5cc  mov     eax, [rdx+4]
0x18003e5cf  mov     [rsp+14F0h+var_14C8], ecx
0x18003e5d3  mov     [rsp+14F0h+var_14C4], eax
0x18003e5d7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003e5dc  cmp     dword ptr [rdx+8], 1
0x18003e5e0  mov     ebx, eax
0x18003e5e2  lea     eax, [r15+8]
0x18003e5e6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18003e5ee  mov     ecx, r15d
0x18003e5f1  cmovz   ecx, eax
0x18003e5f4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18003e5f8  lea     ecx, [rax-7]
0x18003e5fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003e603  inc     ecx
0x18003e605  mov     [rsp+14F0h+var_14B8], r15
0x18003e60a  mov     [rsp+14F0h+var_14C0], ecx
0x18003e60e  call    cs:__imp_GetCurrentThreadId
0x18003e615  nop     dword ptr [rax+rax+00h]
0x18003e61a  xorps   xmm0, xmm0
0x18003e61d  mov     [rsp+14F0h+var_1490], esi
0x18003e621  mov     [rsp+14F0h+var_14B0], eax
0x18003e625  xorps   xmm1, xmm1
0x18003e628  lea     rax, aWil; "wil"
0x18003e62f  mov     [rsp+14F0h+var_148C], ebx
0x18003e633  mov     [rsp+14F0h+var_1498], rax
0x18003e638  xor     eax, eax
0x18003e63a  mov     [rbp+13F0h+var_1458], rax
0x18003e63e  mov     [rbp+13F0h+var_1470], rax
0x18003e642  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003e649  mov     [rsp+14F0h+var_14A8], r15
0x18003e64e  mov     [rsp+14F0h+var_14A0], r15
0x18003e653  mov     [rbp+13F0h+var_1448], rdi
0x18003e657  mov     [rbp+13F0h+var_1440], r14
0x18003e65b  mov     [rsp+14F0h+var_1488], r15
0x18003e660  movups  [rbp+13F0h+var_1468], xmm0
0x18003e664  movups  [rsp+14F0h+var_1480], xmm1
0x18003e669  test    rax, rax
0x18003e66c  jz      short loc_18003E679
0x18003e66e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e673  mov     [rbp+13F0h+var_1450], rax
0x18003e677  jmp     short loc_18003E67D
0x18003e679  mov     [rbp+13F0h+var_1450], r15
0x18003e67d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003e684  test    rax, rax
0x18003e687  jz      short loc_18003E693
0x18003e689  lea     rcx, [rsp+14F0h+var_14D0]
0x18003e68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e693  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003e69a  test    rax, rax
0x18003e69d  jz      short loc_18003E6B3
0x18003e69f  mov     r8d, 400h
0x18003e6a5  lea     rdx, [rbp+13F0h+var_1430]
0x18003e6a9  lea     rcx, [rsp+14F0h+var_14D0]
0x18003e6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6b3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003e6ba  test    rax, rax
0x18003e6bd  jz      short loc_18003E6C9
0x18003e6bf  lea     rcx, [rsp+14F0h+var_14D0]
0x18003e6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6c9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003e6d0  test    rax, rax
0x18003e6d3  jz      short loc_18003E6E6
0x18003e6d5  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003e6da  jnz     short loc_18003E6E6
0x18003e6dc  lea     rcx, [rsp+14F0h+var_14D0]
0x18003e6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6e6  cmp     [rsp+14F0h+var_14C8], r15d
0x18003e6eb  jge     loc_18003E7FA
0x18003e6f1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18003e6f8  jnz     short loc_18003E71F
0x18003e6fa  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003e701  test    rax, rax
0x18003e704  jz      short loc_18003E70F
0x18003e706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e70b  test    al, al
0x18003e70d  jmp     short loc_18003E71D
0x18003e70f  call    cs:__imp_IsDebuggerPresent
0x18003e716  nop     dword ptr [rax+rax+00h]
0x18003e71b  test    eax, eax
0x18003e71d  jz      short loc_18003E726
0x18003e71f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003e724  jz      short loc_18003E74C
0x18003e726  mov     rax, cs:g_pfnResultLoggingCallback
0x18003e72d  test    rax, rax
0x18003e730  jz      short loc_18003E7AB
0x18003e732  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003e739  jnz     short loc_18003E7AB
0x18003e73b  xor     r8d, r8d
0x18003e73e  lea     rcx, [rsp+14F0h+var_14D0]
0x18003e743  xor     edx, edx
0x18003e745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e74a  jmp     short loc_18003E7AB
0x18003e74c  mov     rax, cs:g_pfnResultLoggingCallback
0x18003e753  mov     ebx, 800h
0x18003e758  test    rax, rax
0x18003e75b  jz      short loc_18003E77A
0x18003e75d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003e764  jnz     short loc_18003E77A
0x18003e766  mov     r8d, ebx
0x18003e769  lea     rdx, [rbp+13F0h+OutputString]
0x18003e770  lea     rcx, [rsp+14F0h+var_14D0]
0x18003e775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e77a  cmp     [rbp+13F0h+OutputString], r15w
0x18003e782  jnz     short loc_18003E798
0x18003e784  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18003e789  mov     rdx, rbx; unsigned __int16 *
0x18003e78c  lea     rcx, [rbp+13F0h+OutputString]; this
0x18003e793  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003e798  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18003e79f  call    cs:__imp_OutputDebugStringW
0x18003e7a6  nop     dword ptr [rax+rax+00h]
0x18003e7ab  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18003e7b0  jnz     short loc_18003E7BB
0x18003e7b2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18003e7b9  jz      short loc_18003E7CC
0x18003e7bb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003e7c2  test    rax, rax
0x18003e7c5  jz      short loc_18003E7CC
0x18003e7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7cc  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18003e7d1  jnz     short loc_18003E800
0x18003e7d3  mov     rcx, [rbp+13F0h+var_30]
0x18003e7da  xor     rcx, rsp; StackCookie
0x18003e7dd  call    __security_check_cookie
0x18003e7e2  mov     rbx, [rsp+14F0h+arg_10]
0x18003e7ea  add     rsp, 14D0h
0x18003e7f1  pop     r15
0x18003e7f3  pop     r14
0x18003e7f5  pop     rdi
0x18003e7f6  pop     rsi
0x18003e7f7  pop     rbp
0x18003e7f8  retn
0x18003e7fa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003e800  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18003e805  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
