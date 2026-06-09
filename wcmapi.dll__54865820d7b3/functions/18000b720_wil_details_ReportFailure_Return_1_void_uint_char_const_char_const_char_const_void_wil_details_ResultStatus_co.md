# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000b720`
- end: `0x18000b9d9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007b70`

## callees

- `0x180008a90`
- `0x18000953c`
- `0x180009b44`
- `0x18000b720`
- `0x18000f270`
- `0x180010aa8`
- `0x180010c64`
- `0x18001c800`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7e6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b8e1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b8e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b971`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b971`

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
0x18000b720  push    rbp
0x18000b722  push    rbx
0x18000b723  push    rsi
0x18000b724  push    rdi
0x18000b725  push    r12
0x18000b727  push    r14
0x18000b729  push    r15
0x18000b72b  lea     rbp, [rsp-13D0h]
0x18000b733  mov     eax, 14D0h
0x18000b738  call    _alloca_probe
0x18000b73d  sub     rsp, rax
0x18000b740  mov     rax, cs:__security_cookie
0x18000b747  xor     rax, rsp
0x18000b74a  mov     [rbp+1400h+var_40], rax
0x18000b751  mov     rsi, r8
0x18000b754  mov     edi, edx
0x18000b756  mov     rbx, rcx
0x18000b759  mov     r14, [rbp+1400h+arg_28]
0x18000b760  xor     edx, edx; Val
0x18000b762  mov     r8d, 98h; Size
0x18000b768  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000b76d  call    memset_0
0x18000b772  nop
0x18000b773  xor     r12d, r12d
0x18000b776  mov     [rbp+1400h+OutputString], r12w
0x18000b77e  mov     [rbp+1400h+var_1440], r12b
0x18000b782  mov     rdx, [rbp+1400h+arg_30]; int
0x18000b789  mov     ecx, [rdx]; this
0x18000b78b  mov     [rsp+1500h+var_14D8], ecx
0x18000b78f  mov     eax, [rdx+4]
0x18000b792  mov     [rsp+1500h+var_14D4], eax
0x18000b796  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000b79b  mov     r15d, eax
0x18000b79e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000b7a6  mov     ecx, r12d
0x18000b7a9  lea     eax, [r12+8]
0x18000b7ae  cmp     dword ptr [rdx+8], 1
0x18000b7b2  cmovz   ecx, eax
0x18000b7b5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000b7b9  lea     ecx, [rax-7]
0x18000b7bc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b7c4  inc     ecx
0x18000b7c6  mov     [rsp+1500h+var_14D0], ecx
0x18000b7ca  mov     rcx, [rbp+1400h+arg_38]
0x18000b7d1  test    rcx, rcx
0x18000b7d4  jz      short loc_18000B7E1
0x18000b7d6  cmp     [rcx], r12w
0x18000b7da  mov     [rsp+1500h+var_14C8], rcx
0x18000b7df  jnz     short loc_18000B7E6
0x18000b7e1  mov     [rsp+1500h+var_14C8], r12
0x18000b7e6  call    cs:__imp_GetCurrentThreadId
0x18000b7ed  nop     dword ptr [rax+rax+00h]
0x18000b7f2  mov     [rsp+1500h+var_14C0], eax
0x18000b7f6  mov     [rsp+1500h+var_14A8], rsi
0x18000b7fb  mov     [rsp+1500h+var_14A0], edi
0x18000b7ff  mov     [rsp+1500h+var_149C], r15d
0x18000b804  mov     [rsp+1500h+var_14B8], r12
0x18000b809  mov     [rsp+1500h+var_14B0], r12
0x18000b80e  mov     [rbp+1400h+var_1458], r14
0x18000b812  mov     [rbp+1400h+var_1450], rbx
0x18000b816  mov     [rsp+1500h+var_1498], r12
0x18000b81b  xorps   xmm0, xmm0
0x18000b81e  xor     eax, eax
0x18000b820  movups  [rbp+1400h+var_1478], xmm0
0x18000b824  mov     [rbp+1400h+var_1468], rax
0x18000b828  xorps   xmm1, xmm1
0x18000b82b  movups  [rsp+1500h+var_1490], xmm1
0x18000b830  mov     [rbp+1400h+var_1480], rax
0x18000b834  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b83b  test    rax, rax
0x18000b83e  jz      short loc_18000B84B
0x18000b840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b845  mov     [rbp+1400h+var_1460], rax
0x18000b849  jmp     short loc_18000B84F
0x18000b84b  mov     [rbp+1400h+var_1460], r12
0x18000b84f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b856  test    rax, rax
0x18000b859  jz      short loc_18000B865
0x18000b85b  lea     rcx, [rsp+1500h+var_14E0]
0x18000b860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b865  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b86c  test    rax, rax
0x18000b86f  jz      short loc_18000B885
0x18000b871  mov     r8d, 400h
0x18000b877  lea     rdx, [rbp+1400h+var_1440]
0x18000b87b  lea     rcx, [rsp+1500h+var_14E0]
0x18000b880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b885  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b88c  test    rax, rax
0x18000b88f  jz      short loc_18000B89B
0x18000b891  lea     rcx, [rsp+1500h+var_14E0]
0x18000b896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b89b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b8a2  test    rax, rax
0x18000b8a5  jz      short loc_18000B8B8
0x18000b8a7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000b8ac  jnz     short loc_18000B8B8
0x18000b8ae  lea     rcx, [rsp+1500h+var_14E0]
0x18000b8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8b8  cmp     [rsp+1500h+var_14D8], r12d
0x18000b8bd  jge     loc_18000B9D3
0x18000b8c3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000b8ca  jnz     short loc_18000B8F1
0x18000b8cc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b8d3  test    rax, rax
0x18000b8d6  jz      short loc_18000B8E1
0x18000b8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8dd  test    al, al
0x18000b8df  jmp     short loc_18000B8EF
0x18000b8e1  call    cs:__imp_IsDebuggerPresent
0x18000b8e8  nop     dword ptr [rax+rax+00h]
0x18000b8ed  test    eax, eax
0x18000b8ef  jz      short loc_18000B8F8
0x18000b8f1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000b8f6  jz      short loc_18000B91E
0x18000b8f8  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b8ff  test    rax, rax
0x18000b902  jz      short loc_18000B97D
0x18000b904  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000b90b  jnz     short loc_18000B97D
0x18000b90d  xor     r8d, r8d
0x18000b910  xor     edx, edx
0x18000b912  lea     rcx, [rsp+1500h+var_14E0]
0x18000b917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b91c  jmp     short loc_18000B97D
0x18000b91e  mov     ebx, 800h
0x18000b923  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b92a  test    rax, rax
0x18000b92d  jz      short loc_18000B94C
0x18000b92f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000b936  jnz     short loc_18000B94C
0x18000b938  mov     r8d, ebx
0x18000b93b  lea     rdx, [rbp+1400h+OutputString]
0x18000b942  lea     rcx, [rsp+1500h+var_14E0]
0x18000b947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b94c  cmp     [rbp+1400h+OutputString], r12w
0x18000b954  jnz     short loc_18000B96A
0x18000b956  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000b95b  mov     rdx, rbx; unsigned __int16 *
0x18000b95e  lea     rcx, [rbp+1400h+OutputString]; this
0x18000b965  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b96a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000b971  call    cs:__imp_OutputDebugStringW
0x18000b978  nop     dword ptr [rax+rax+00h]
0x18000b97d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000b982  jnz     short loc_18000B98D
0x18000b984  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000b98b  jz      short loc_18000B99F
0x18000b98d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b994  test    rax, rax
0x18000b997  jz      short loc_18000B99F
0x18000b999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b99e  nop
0x18000b99f  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000b9a4  jnz     short loc_18000B9C8
0x18000b9a6  mov     rcx, [rbp+1400h+var_40]
0x18000b9ad  xor     rcx, rsp; StackCookie
0x18000b9b0  call    __security_check_cookie
0x18000b9b5  add     rsp, 14D0h
0x18000b9bc  pop     r15
0x18000b9be  pop     r14
0x18000b9c0  pop     r12
0x18000b9c2  pop     rdi
0x18000b9c3  pop     rsi
0x18000b9c4  pop     rbx
0x18000b9c5  pop     rbp
0x18000b9c6  retn
0x18000b9c8  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000b9cd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000b9d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
