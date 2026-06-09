# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001c9b8`
- end: `0x18001cc5e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180018188`

## callees

- `0x180019a20`
- `0x18001a5bc`
- `0x18001bba4`
- `0x18001c9b8`
- `0x18001d354`
- `0x18001d394`
- `0x18001de18`
- `0x1800600d0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ca7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ca7e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cbfd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cbfd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001cb73`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001cb73`

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
0x18001c9b8  push    rbp
0x18001c9ba  push    rbx
0x18001c9bb  push    rsi
0x18001c9bc  push    rdi
0x18001c9bd  push    r12
0x18001c9bf  push    r14
0x18001c9c1  push    r15
0x18001c9c3  lea     rbp, [rsp-13D0h]
0x18001c9cb  mov     eax, 14D0h
0x18001c9d0  call    _alloca_probe
0x18001c9d5  sub     rsp, rax
0x18001c9d8  mov     rax, cs:__security_cookie
0x18001c9df  xor     rax, rsp
0x18001c9e2  mov     [rbp+1400h+var_40], rax
0x18001c9e9  mov     rsi, r8
0x18001c9ec  mov     edi, edx
0x18001c9ee  mov     rbx, rcx
0x18001c9f1  mov     r14, [rbp+1400h+arg_28]
0x18001c9f8  xor     edx, edx; Val
0x18001c9fa  mov     r8d, 98h; Size
0x18001ca00  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18001ca05  call    memset_0
0x18001ca0a  nop
0x18001ca0b  xor     r12d, r12d
0x18001ca0e  mov     [rbp+1400h+OutputString], r12w
0x18001ca16  mov     [rbp+1400h+var_1440], r12b
0x18001ca1a  mov     rdx, [rbp+1400h+arg_30]; int
0x18001ca21  mov     ecx, [rdx]; this
0x18001ca23  mov     [rsp+1500h+var_14D8], ecx
0x18001ca27  mov     eax, [rdx+4]
0x18001ca2a  mov     [rsp+1500h+var_14D4], eax
0x18001ca2e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001ca33  mov     r15d, eax
0x18001ca36  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18001ca3e  mov     ecx, r12d
0x18001ca41  lea     eax, [r12+8]
0x18001ca46  cmp     dword ptr [rdx+8], 1
0x18001ca4a  cmovz   ecx, eax
0x18001ca4d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18001ca51  lea     ecx, [rax-7]
0x18001ca54  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001ca5c  inc     ecx
0x18001ca5e  mov     [rsp+1500h+var_14D0], ecx
0x18001ca62  mov     rcx, [rbp+1400h+arg_38]
0x18001ca69  test    rcx, rcx
0x18001ca6c  jz      short loc_18001CA79
0x18001ca6e  cmp     [rcx], r12w
0x18001ca72  mov     [rsp+1500h+var_14C8], rcx
0x18001ca77  jnz     short loc_18001CA7E
0x18001ca79  mov     [rsp+1500h+var_14C8], r12
0x18001ca7e  call    cs:__imp_GetCurrentThreadId
0x18001ca84  mov     [rsp+1500h+var_14C0], eax
0x18001ca88  mov     [rsp+1500h+var_14A8], rsi
0x18001ca8d  mov     [rsp+1500h+var_14A0], edi
0x18001ca91  mov     [rsp+1500h+var_149C], r15d
0x18001ca96  mov     [rsp+1500h+var_14B8], r12
0x18001ca9b  mov     [rsp+1500h+var_14B0], r12
0x18001caa0  mov     [rbp+1400h+var_1458], r14
0x18001caa4  mov     [rbp+1400h+var_1450], rbx
0x18001caa8  mov     [rsp+1500h+var_1498], r12
0x18001caad  xorps   xmm0, xmm0
0x18001cab0  xor     eax, eax
0x18001cab2  movups  [rbp+1400h+var_1478], xmm0
0x18001cab6  mov     [rbp+1400h+var_1468], rax
0x18001caba  xorps   xmm1, xmm1
0x18001cabd  movups  [rsp+1500h+var_1490], xmm1
0x18001cac2  mov     [rbp+1400h+var_1480], rax
0x18001cac6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001cacd  test    rax, rax
0x18001cad0  jz      short loc_18001CADD
0x18001cad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cad7  mov     [rbp+1400h+var_1460], rax
0x18001cadb  jmp     short loc_18001CAE1
0x18001cadd  mov     [rbp+1400h+var_1460], r12
0x18001cae1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001cae8  test    rax, rax
0x18001caeb  jz      short loc_18001CAF7
0x18001caed  lea     rcx, [rsp+1500h+var_14E0]
0x18001caf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caf7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001cafe  test    rax, rax
0x18001cb01  jz      short loc_18001CB17
0x18001cb03  mov     r8d, 400h
0x18001cb09  lea     rdx, [rbp+1400h+var_1440]
0x18001cb0d  lea     rcx, [rsp+1500h+var_14E0]
0x18001cb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb17  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001cb1e  test    rax, rax
0x18001cb21  jz      short loc_18001CB2D
0x18001cb23  lea     rcx, [rsp+1500h+var_14E0]
0x18001cb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb2d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001cb34  test    rax, rax
0x18001cb37  jz      short loc_18001CB4A
0x18001cb39  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001cb3e  jnz     short loc_18001CB4A
0x18001cb40  lea     rcx, [rsp+1500h+var_14E0]
0x18001cb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb4a  cmp     [rsp+1500h+var_14D8], r12d
0x18001cb4f  jge     loc_18001CC58
0x18001cb55  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18001cb5c  jnz     short loc_18001CB7D
0x18001cb5e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001cb65  test    rax, rax
0x18001cb68  jz      short loc_18001CB73
0x18001cb6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb6f  test    al, al
0x18001cb71  jmp     short loc_18001CB7B
0x18001cb73  call    cs:__imp_IsDebuggerPresent
0x18001cb79  test    eax, eax
0x18001cb7b  jz      short loc_18001CB84
0x18001cb7d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001cb82  jz      short loc_18001CBAA
0x18001cb84  mov     rax, cs:g_pfnResultLoggingCallback
0x18001cb8b  test    rax, rax
0x18001cb8e  jz      short loc_18001CC03
0x18001cb90  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001cb97  jnz     short loc_18001CC03
0x18001cb99  xor     r8d, r8d
0x18001cb9c  xor     edx, edx
0x18001cb9e  lea     rcx, [rsp+1500h+var_14E0]
0x18001cba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cba8  jmp     short loc_18001CC03
0x18001cbaa  mov     ebx, 800h
0x18001cbaf  mov     rax, cs:g_pfnResultLoggingCallback
0x18001cbb6  test    rax, rax
0x18001cbb9  jz      short loc_18001CBD8
0x18001cbbb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001cbc2  jnz     short loc_18001CBD8
0x18001cbc4  mov     r8d, ebx
0x18001cbc7  lea     rdx, [rbp+1400h+OutputString]
0x18001cbce  lea     rcx, [rsp+1500h+var_14E0]
0x18001cbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbd8  cmp     [rbp+1400h+OutputString], r12w
0x18001cbe0  jnz     short loc_18001CBF6
0x18001cbe2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18001cbe7  mov     rdx, rbx; unsigned __int16 *
0x18001cbea  lea     rcx, [rbp+1400h+OutputString]; this
0x18001cbf1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001cbf6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18001cbfd  call    cs:__imp_OutputDebugStringW
0x18001cc03  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18001cc08  jnz     short loc_18001CC13
0x18001cc0a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18001cc11  jz      short loc_18001CC25
0x18001cc13  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001cc1a  test    rax, rax
0x18001cc1d  jz      short loc_18001CC25
0x18001cc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc24  nop
0x18001cc25  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18001cc2a  jnz     short loc_18001CC4D
0x18001cc2c  mov     rcx, [rbp+1400h+var_40]
0x18001cc33  xor     rcx, rsp; StackCookie
0x18001cc36  call    __security_check_cookie
0x18001cc3b  add     rsp, 14D0h
0x18001cc42  pop     r15
0x18001cc44  pop     r14
0x18001cc46  pop     r12
0x18001cc48  pop     rdi
0x18001cc49  pop     rsi
0x18001cc4a  pop     rbx
0x18001cc4b  pop     rbp
0x18001cc4c  retn
0x18001cc4d  lea     rcx, [rsp+1500h+var_14E0]; this
0x18001cc52  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001cc58  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
