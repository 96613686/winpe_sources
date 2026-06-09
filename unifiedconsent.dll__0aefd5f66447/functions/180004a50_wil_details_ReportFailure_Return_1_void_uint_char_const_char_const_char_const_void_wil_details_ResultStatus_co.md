# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004a50`
- end: `0x180004cf6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004000`

## callees

- `0x180002810`
- `0x180003384`
- `0x180004a50`
- `0x180009274`
- `0x18000ade8`
- `0x18000e140`
- `0x18000e434`
- `0x180070720`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b16`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c95`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004c0b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004c0b`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180004a50  push    rbp
0x180004a52  push    rbx
0x180004a53  push    rsi
0x180004a54  push    rdi
0x180004a55  push    r12
0x180004a57  push    r14
0x180004a59  push    r15
0x180004a5b  lea     rbp, [rsp-13D0h]
0x180004a63  mov     eax, 14D0h
0x180004a68  call    _alloca_probe
0x180004a6d  sub     rsp, rax
0x180004a70  mov     rax, cs:__security_cookie
0x180004a77  xor     rax, rsp
0x180004a7a  mov     [rbp+1400h+var_40], rax
0x180004a81  mov     rsi, r8
0x180004a84  mov     edi, edx
0x180004a86  mov     rbx, rcx
0x180004a89  mov     r14, [rbp+1400h+arg_28]
0x180004a90  xor     edx, edx; Val
0x180004a92  mov     r8d, 98h; Size
0x180004a98  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004a9d  call    memset_0
0x180004aa2  nop
0x180004aa3  xor     r12d, r12d
0x180004aa6  mov     [rbp+1400h+OutputString], r12w
0x180004aae  mov     [rbp+1400h+var_1440], r12b
0x180004ab2  mov     rdx, [rbp+1400h+arg_30]; int
0x180004ab9  mov     ecx, [rdx]; this
0x180004abb  mov     [rsp+1500h+var_14D8], ecx
0x180004abf  mov     eax, [rdx+4]
0x180004ac2  mov     [rsp+1500h+var_14D4], eax
0x180004ac6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004acb  mov     r15d, eax
0x180004ace  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004ad6  mov     ecx, r12d
0x180004ad9  lea     eax, [r12+8]
0x180004ade  cmp     dword ptr [rdx+8], 1
0x180004ae2  cmovz   ecx, eax
0x180004ae5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004ae9  lea     ecx, [rax-7]
0x180004aec  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004af4  inc     ecx
0x180004af6  mov     [rsp+1500h+var_14D0], ecx
0x180004afa  mov     rcx, [rbp+1400h+arg_38]
0x180004b01  test    rcx, rcx
0x180004b04  jz      short loc_180004B11
0x180004b06  cmp     [rcx], r12w
0x180004b0a  mov     [rsp+1500h+var_14C8], rcx
0x180004b0f  jnz     short loc_180004B16
0x180004b11  mov     [rsp+1500h+var_14C8], r12
0x180004b16  call    cs:__imp_GetCurrentThreadId
0x180004b1c  mov     [rsp+1500h+var_14C0], eax
0x180004b20  mov     [rsp+1500h+var_14A8], rsi
0x180004b25  mov     [rsp+1500h+var_14A0], edi
0x180004b29  mov     [rsp+1500h+var_149C], r15d
0x180004b2e  mov     [rsp+1500h+var_14B8], r12
0x180004b33  mov     [rsp+1500h+var_14B0], r12
0x180004b38  mov     [rbp+1400h+var_1458], r14
0x180004b3c  mov     [rbp+1400h+var_1450], rbx
0x180004b40  mov     [rsp+1500h+var_1498], r12
0x180004b45  xorps   xmm0, xmm0
0x180004b48  xor     eax, eax
0x180004b4a  movups  [rbp+1400h+var_1478], xmm0
0x180004b4e  mov     [rbp+1400h+var_1468], rax
0x180004b52  xorps   xmm1, xmm1
0x180004b55  movups  [rsp+1500h+var_1490], xmm1
0x180004b5a  mov     [rbp+1400h+var_1480], rax
0x180004b5e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004b65  test    rax, rax
0x180004b68  jz      short loc_180004B75
0x180004b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b6f  mov     [rbp+1400h+var_1460], rax
0x180004b73  jmp     short loc_180004B79
0x180004b75  mov     [rbp+1400h+var_1460], r12
0x180004b79  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004b80  test    rax, rax
0x180004b83  jz      short loc_180004B8F
0x180004b85  lea     rcx, [rsp+1500h+var_14E0]
0x180004b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004b96  test    rax, rax
0x180004b99  jz      short loc_180004BAF
0x180004b9b  mov     r8d, 400h
0x180004ba1  lea     rdx, [rbp+1400h+var_1440]
0x180004ba5  lea     rcx, [rsp+1500h+var_14E0]
0x180004baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004baf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004bb6  test    rax, rax
0x180004bb9  jz      short loc_180004BC5
0x180004bbb  lea     rcx, [rsp+1500h+var_14E0]
0x180004bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bc5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004bcc  test    rax, rax
0x180004bcf  jz      short loc_180004BE2
0x180004bd1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004bd6  jnz     short loc_180004BE2
0x180004bd8  lea     rcx, [rsp+1500h+var_14E0]
0x180004bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be2  cmp     [rsp+1500h+var_14D8], r12d
0x180004be7  jge     loc_180004CF0
0x180004bed  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004bf4  jnz     short loc_180004C15
0x180004bf6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004bfd  test    rax, rax
0x180004c00  jz      short loc_180004C0B
0x180004c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c07  test    al, al
0x180004c09  jmp     short loc_180004C13
0x180004c0b  call    cs:__imp_IsDebuggerPresent
0x180004c11  test    eax, eax
0x180004c13  jz      short loc_180004C1C
0x180004c15  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004c1a  jz      short loc_180004C42
0x180004c1c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c23  test    rax, rax
0x180004c26  jz      short loc_180004C9B
0x180004c28  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004c2f  jnz     short loc_180004C9B
0x180004c31  xor     r8d, r8d
0x180004c34  xor     edx, edx
0x180004c36  lea     rcx, [rsp+1500h+var_14E0]
0x180004c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c40  jmp     short loc_180004C9B
0x180004c42  mov     ebx, 800h
0x180004c47  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c4e  test    rax, rax
0x180004c51  jz      short loc_180004C70
0x180004c53  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004c5a  jnz     short loc_180004C70
0x180004c5c  mov     r8d, ebx
0x180004c5f  lea     rdx, [rbp+1400h+OutputString]
0x180004c66  lea     rcx, [rsp+1500h+var_14E0]
0x180004c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c70  cmp     [rbp+1400h+OutputString], r12w
0x180004c78  jnz     short loc_180004C8E
0x180004c7a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004c7f  mov     rdx, rbx; unsigned __int16 *
0x180004c82  lea     rcx, [rbp+1400h+OutputString]; this
0x180004c89  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004c8e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004c95  call    cs:__imp_OutputDebugStringW
0x180004c9b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004ca0  jnz     short loc_180004CAB
0x180004ca2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004ca9  jz      short loc_180004CBD
0x180004cab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004cb2  test    rax, rax
0x180004cb5  jz      short loc_180004CBD
0x180004cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cbc  nop
0x180004cbd  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004cc2  jnz     short loc_180004CE5
0x180004cc4  mov     rcx, [rbp+1400h+var_40]
0x180004ccb  xor     rcx, rsp; StackCookie
0x180004cce  call    __security_check_cookie
0x180004cd3  add     rsp, 14D0h
0x180004cda  pop     r15
0x180004cdc  pop     r14
0x180004cde  pop     r12
0x180004ce0  pop     rdi
0x180004ce1  pop     rsi
0x180004ce2  pop     rbx
0x180004ce3  pop     rbp
0x180004ce4  retn
0x180004ce5  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004cea  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004cf0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
