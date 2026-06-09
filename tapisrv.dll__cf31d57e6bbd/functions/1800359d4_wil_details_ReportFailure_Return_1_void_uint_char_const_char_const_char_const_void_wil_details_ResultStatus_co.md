# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800359d4`
- end: `0x180035c68`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800354dc`

## callees

- `0x180001600`
- `0x180001f50`
- `0x1800359d4`
- `0x1800380e4`
- `0x18003a1f0`
- `0x18003c250`
- `0x18003c408`
- `0x18003fb10`
- `0x180040010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180035b79`
- `KERNEL32!IsDebuggerPresent` at `0x180035b79`
- `KERNEL32!OutputDebugStringW` at `0x180035c03`
- `KERNEL32!OutputDebugStringW` at `0x180035c03`
- `KERNEL32!GetCurrentThreadId` at `0x180035a7e`
- `KERNEL32!GetCurrentThreadId` at `0x180035a7e`

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
0x1800359d4  mov     [rsp-8+arg_10], rbx
0x1800359d9  push    rbp
0x1800359da  push    rsi
0x1800359db  push    rdi
0x1800359dc  push    r14
0x1800359de  push    r15
0x1800359e0  lea     rbp, [rsp-13D0h]
0x1800359e8  mov     eax, 14D0h
0x1800359ed  call    _alloca_probe
0x1800359f2  sub     rsp, rax
0x1800359f5  mov     rax, cs:__security_cookie
0x1800359fc  xor     rax, rsp
0x1800359ff  mov     [rbp+13F0h+var_30], rax
0x180035a06  mov     rdi, [rbp+13F0h+arg_28]
0x180035a0d  mov     esi, edx
0x180035a0f  mov     r14, rcx
0x180035a12  xor     edx, edx; Val
0x180035a14  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180035a19  mov     r8d, 98h; Size
0x180035a1f  call    memset_0
0x180035a24  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180035a2b  xor     r15d, r15d
0x180035a2e  mov     [rbp+13F0h+OutputString], r15w
0x180035a36  mov     [rbp+13F0h+var_1430], r15b
0x180035a3a  mov     ecx, [rdx]; this
0x180035a3c  mov     eax, [rdx+4]
0x180035a3f  mov     [rsp+14F0h+var_14C8], ecx
0x180035a43  mov     [rsp+14F0h+var_14C4], eax
0x180035a47  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180035a4c  cmp     dword ptr [rdx+8], 1
0x180035a50  mov     ebx, eax
0x180035a52  lea     eax, [r15+8]
0x180035a56  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180035a5e  mov     ecx, r15d
0x180035a61  cmovz   ecx, eax
0x180035a64  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180035a68  lea     ecx, [rax-7]
0x180035a6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180035a73  inc     ecx
0x180035a75  mov     [rsp+14F0h+var_14B8], r15
0x180035a7a  mov     [rsp+14F0h+var_14C0], ecx
0x180035a7e  call    cs:__imp_GetCurrentThreadId
0x180035a84  xorps   xmm0, xmm0
0x180035a87  mov     [rsp+14F0h+var_1490], esi
0x180035a8b  mov     [rsp+14F0h+var_14B0], eax
0x180035a8f  xorps   xmm1, xmm1
0x180035a92  lea     rax, aWil; "wil"
0x180035a99  mov     [rsp+14F0h+var_148C], ebx
0x180035a9d  mov     [rsp+14F0h+var_1498], rax
0x180035aa2  xor     eax, eax
0x180035aa4  mov     [rbp+13F0h+var_1458], rax
0x180035aa8  mov     [rbp+13F0h+var_1470], rax
0x180035aac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180035ab3  mov     [rsp+14F0h+var_14A8], r15
0x180035ab8  mov     [rsp+14F0h+var_14A0], r15
0x180035abd  mov     [rbp+13F0h+var_1448], rdi
0x180035ac1  mov     [rbp+13F0h+var_1440], r14
0x180035ac5  mov     [rsp+14F0h+var_1488], r15
0x180035aca  movups  [rbp+13F0h+var_1468], xmm0
0x180035ace  movups  [rsp+14F0h+var_1480], xmm1
0x180035ad3  test    rax, rax
0x180035ad6  jz      short loc_180035AE3
0x180035ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035add  mov     [rbp+13F0h+var_1450], rax
0x180035ae1  jmp     short loc_180035AE7
0x180035ae3  mov     [rbp+13F0h+var_1450], r15
0x180035ae7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180035aee  test    rax, rax
0x180035af1  jz      short loc_180035AFD
0x180035af3  lea     rcx, [rsp+14F0h+var_14D0]
0x180035af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035afd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180035b04  test    rax, rax
0x180035b07  jz      short loc_180035B1D
0x180035b09  mov     r8d, 400h
0x180035b0f  lea     rdx, [rbp+13F0h+var_1430]
0x180035b13  lea     rcx, [rsp+14F0h+var_14D0]
0x180035b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b1d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180035b24  test    rax, rax
0x180035b27  jz      short loc_180035B33
0x180035b29  lea     rcx, [rsp+14F0h+var_14D0]
0x180035b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b33  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180035b3a  test    rax, rax
0x180035b3d  jz      short loc_180035B50
0x180035b3f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180035b44  jnz     short loc_180035B50
0x180035b46  lea     rcx, [rsp+14F0h+var_14D0]
0x180035b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b50  cmp     [rsp+14F0h+var_14C8], r15d
0x180035b55  jge     loc_180035C57
0x180035b5b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180035b62  jnz     short loc_180035B83
0x180035b64  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180035b6b  test    rax, rax
0x180035b6e  jz      short loc_180035B79
0x180035b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b75  test    al, al
0x180035b77  jmp     short loc_180035B81
0x180035b79  call    cs:__imp_IsDebuggerPresent
0x180035b7f  test    eax, eax
0x180035b81  jz      short loc_180035B8A
0x180035b83  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180035b88  jz      short loc_180035BB0
0x180035b8a  mov     rax, cs:g_pfnResultLoggingCallback
0x180035b91  test    rax, rax
0x180035b94  jz      short loc_180035C09
0x180035b96  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180035b9d  jnz     short loc_180035C09
0x180035b9f  xor     r8d, r8d
0x180035ba2  lea     rcx, [rsp+14F0h+var_14D0]
0x180035ba7  xor     edx, edx
0x180035ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bae  jmp     short loc_180035C09
0x180035bb0  mov     rax, cs:g_pfnResultLoggingCallback
0x180035bb7  mov     ebx, 800h
0x180035bbc  test    rax, rax
0x180035bbf  jz      short loc_180035BDE
0x180035bc1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180035bc8  jnz     short loc_180035BDE
0x180035bca  mov     r8d, ebx
0x180035bcd  lea     rdx, [rbp+13F0h+OutputString]
0x180035bd4  lea     rcx, [rsp+14F0h+var_14D0]
0x180035bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bde  cmp     [rbp+13F0h+OutputString], r15w
0x180035be6  jnz     short loc_180035BFC
0x180035be8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180035bed  mov     rdx, rbx; unsigned __int16 *
0x180035bf0  lea     rcx, [rbp+13F0h+OutputString]; this
0x180035bf7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180035bfc  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180035c03  call    cs:__imp_OutputDebugStringW
0x180035c09  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180035c0e  jnz     short loc_180035C19
0x180035c10  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180035c17  jz      short loc_180035C2A
0x180035c19  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180035c20  test    rax, rax
0x180035c23  jz      short loc_180035C2A
0x180035c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c2a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180035c2f  jnz     short loc_180035C5D
0x180035c31  mov     rcx, [rbp+13F0h+var_30]
0x180035c38  xor     rcx, rsp; StackCookie
0x180035c3b  call    __security_check_cookie
0x180035c40  mov     rbx, [rsp+14F0h+arg_10]
0x180035c48  add     rsp, 14D0h
0x180035c4f  pop     r15
0x180035c51  pop     r14
0x180035c53  pop     rdi
0x180035c54  pop     rsi
0x180035c55  pop     rbp
0x180035c56  retn
0x180035c57  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180035c5d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180035c62  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
