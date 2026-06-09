# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800089b8`
- end: `0x180008c4e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008498`

## callees

- `0x1800089b8`
- `0x18000b984`
- `0x18000eddc`
- `0x1800122f0`
- `0x1800125a4`
- `0x180029882`
- `0x1800298c0`
- `0x180029980`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008a63`
- `KERNEL32!GetCurrentThreadId` at `0x180008a63`
- `KERNEL32!IsDebuggerPresent` at `0x180008b5e`
- `KERNEL32!IsDebuggerPresent` at `0x180008b5e`
- `KERNEL32!OutputDebugStringW` at `0x180008be8`
- `KERNEL32!OutputDebugStringW` at `0x180008be8`

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
0x1800089b8  mov     [rsp-8+arg_10], rbx
0x1800089bd  push    rbp
0x1800089be  push    rsi
0x1800089bf  push    rdi
0x1800089c0  push    r14
0x1800089c2  push    r15
0x1800089c4  lea     rbp, [rsp-13D0h]
0x1800089cc  mov     eax, 14D0h
0x1800089d1  call    _alloca_probe
0x1800089d6  sub     rsp, rax
0x1800089d9  mov     rax, cs:__security_cookie
0x1800089e0  xor     rax, rsp
0x1800089e3  mov     [rbp+13F0h+var_30], rax
0x1800089ea  mov     esi, edx
0x1800089ec  mov     r14, rcx
0x1800089ef  mov     rdi, [rbp+13F0h+arg_28]
0x1800089f6  xor     edx, edx; Val
0x1800089f8  mov     r8d, 98h; Size
0x1800089fe  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008a03  call    memset_0
0x180008a08  nop
0x180008a09  xor     r15d, r15d
0x180008a0c  mov     [rbp+13F0h+OutputString], r15w
0x180008a14  mov     [rbp+13F0h+var_1430], r15b
0x180008a18  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180008a1f  mov     ecx, [rdx]; this
0x180008a21  mov     [rsp+14F0h+var_14C8], ecx
0x180008a25  mov     eax, [rdx+4]
0x180008a28  mov     [rsp+14F0h+var_14C4], eax
0x180008a2c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008a31  mov     ebx, eax
0x180008a33  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180008a3b  mov     ecx, r15d
0x180008a3e  lea     eax, [r15+8]
0x180008a42  cmp     dword ptr [rdx+8], 1
0x180008a46  cmovz   ecx, eax
0x180008a49  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008a4d  lea     ecx, [rax-7]
0x180008a50  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008a58  inc     ecx
0x180008a5a  mov     [rsp+14F0h+var_14C0], ecx
0x180008a5e  mov     [rsp+14F0h+var_14B8], r15
0x180008a63  call    cs:__imp_GetCurrentThreadId
0x180008a69  mov     [rsp+14F0h+var_14B0], eax
0x180008a6d  lea     rax, aWil; "wil"
0x180008a74  mov     [rsp+14F0h+var_1498], rax
0x180008a79  mov     [rsp+14F0h+var_1490], esi
0x180008a7d  mov     [rsp+14F0h+var_148C], ebx
0x180008a81  mov     [rsp+14F0h+var_14A8], r15
0x180008a86  mov     [rsp+14F0h+var_14A0], r15
0x180008a8b  mov     [rbp+13F0h+var_1448], rdi
0x180008a8f  mov     [rbp+13F0h+var_1440], r14
0x180008a93  mov     [rsp+14F0h+var_1488], r15
0x180008a98  xorps   xmm0, xmm0
0x180008a9b  xor     eax, eax
0x180008a9d  movups  [rbp+13F0h+var_1468], xmm0
0x180008aa1  mov     [rbp+13F0h+var_1458], rax
0x180008aa5  xorps   xmm1, xmm1
0x180008aa8  movups  [rsp+14F0h+var_1480], xmm1
0x180008aad  mov     [rbp+13F0h+var_1470], rax
0x180008ab1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008ab8  test    rax, rax
0x180008abb  jz      short loc_180008AC8
0x180008abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac2  mov     [rbp+13F0h+var_1450], rax
0x180008ac6  jmp     short loc_180008ACC
0x180008ac8  mov     [rbp+13F0h+var_1450], r15
0x180008acc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008ad3  test    rax, rax
0x180008ad6  jz      short loc_180008AE2
0x180008ad8  lea     rcx, [rsp+14F0h+var_14D0]
0x180008add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ae2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008ae9  test    rax, rax
0x180008aec  jz      short loc_180008B02
0x180008aee  mov     r8d, 400h
0x180008af4  lea     rdx, [rbp+13F0h+var_1430]
0x180008af8  lea     rcx, [rsp+14F0h+var_14D0]
0x180008afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b02  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008b09  test    rax, rax
0x180008b0c  jz      short loc_180008B18
0x180008b0e  lea     rcx, [rsp+14F0h+var_14D0]
0x180008b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b18  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008b1f  test    rax, rax
0x180008b22  jz      short loc_180008B35
0x180008b24  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008b29  jnz     short loc_180008B35
0x180008b2b  lea     rcx, [rsp+14F0h+var_14D0]
0x180008b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b35  cmp     [rsp+14F0h+var_14C8], r15d
0x180008b3a  jge     loc_180008C48
0x180008b40  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180008b47  jnz     short loc_180008B68
0x180008b49  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008b50  test    rax, rax
0x180008b53  jz      short loc_180008B5E
0x180008b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b5a  test    al, al
0x180008b5c  jmp     short loc_180008B66
0x180008b5e  call    cs:__imp_IsDebuggerPresent
0x180008b64  test    eax, eax
0x180008b66  jz      short loc_180008B6F
0x180008b68  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008b6d  jz      short loc_180008B95
0x180008b6f  mov     rax, cs:g_pfnResultLoggingCallback
0x180008b76  test    rax, rax
0x180008b79  jz      short loc_180008BEE
0x180008b7b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008b82  jnz     short loc_180008BEE
0x180008b84  xor     r8d, r8d
0x180008b87  xor     edx, edx
0x180008b89  lea     rcx, [rsp+14F0h+var_14D0]
0x180008b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b93  jmp     short loc_180008BEE
0x180008b95  mov     ebx, 800h
0x180008b9a  mov     rax, cs:g_pfnResultLoggingCallback
0x180008ba1  test    rax, rax
0x180008ba4  jz      short loc_180008BC3
0x180008ba6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008bad  jnz     short loc_180008BC3
0x180008baf  mov     r8d, ebx
0x180008bb2  lea     rdx, [rbp+13F0h+OutputString]
0x180008bb9  lea     rcx, [rsp+14F0h+var_14D0]
0x180008bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bc3  cmp     [rbp+13F0h+OutputString], r15w
0x180008bcb  jnz     short loc_180008BE1
0x180008bcd  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008bd2  mov     rdx, rbx; unsigned __int16 *
0x180008bd5  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008bdc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008be1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008be8  call    cs:__imp_OutputDebugStringW
0x180008bee  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180008bf3  jnz     short loc_180008BFE
0x180008bf5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180008bfc  jz      short loc_180008C10
0x180008bfe  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008c05  test    rax, rax
0x180008c08  jz      short loc_180008C10
0x180008c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c0f  nop
0x180008c10  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180008c15  jnz     short loc_180008C3D
0x180008c17  mov     rcx, [rbp+13F0h+var_30]
0x180008c1e  xor     rcx, rsp; StackCookie
0x180008c21  call    __security_check_cookie
0x180008c26  mov     rbx, [rsp+14F0h+arg_10]
0x180008c2e  add     rsp, 14D0h
0x180008c35  pop     r15
0x180008c37  pop     r14
0x180008c39  pop     rdi
0x180008c3a  pop     rsi
0x180008c3b  pop     rbp
0x180008c3c  retn
0x180008c3d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008c42  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008c48  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
