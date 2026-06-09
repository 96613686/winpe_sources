# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180008bb0`
- end: `0x180008e59`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008678`

## callees

- `0x180008bb0`
- `0x180009b84`
- `0x18000adf4`
- `0x18000c38c`
- `0x18000c468`
- `0x18000c836`
- `0x18000c860`
- `0x18000c920`
- `0x18000d010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180008d5c`
- `KERNEL32!IsDebuggerPresent` at `0x180008d5c`
- `KERNEL32!OutputDebugStringW` at `0x180008dec`
- `KERNEL32!OutputDebugStringW` at `0x180008dec`
- `KERNEL32!GetCurrentThreadId` at `0x180008c5b`
- `KERNEL32!GetCurrentThreadId` at `0x180008c5b`

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
0x180008bb0  mov     [rsp-8+arg_10], rbx
0x180008bb5  push    rbp
0x180008bb6  push    rsi
0x180008bb7  push    rdi
0x180008bb8  push    r14
0x180008bba  push    r15
0x180008bbc  lea     rbp, [rsp-13D0h]
0x180008bc4  mov     eax, 14D0h
0x180008bc9  call    _alloca_probe
0x180008bce  sub     rsp, rax
0x180008bd1  mov     rax, cs:__security_cookie
0x180008bd8  xor     rax, rsp
0x180008bdb  mov     [rbp+13F0h+var_30], rax
0x180008be2  mov     esi, edx
0x180008be4  mov     r14, rcx
0x180008be7  mov     rdi, [rbp+13F0h+arg_28]
0x180008bee  xor     edx, edx; Val
0x180008bf0  mov     r8d, 98h; Size
0x180008bf6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008bfb  call    memset_0
0x180008c00  nop
0x180008c01  xor     r15d, r15d
0x180008c04  mov     [rbp+13F0h+OutputString], r15w
0x180008c0c  mov     [rbp+13F0h+var_1430], r15b
0x180008c10  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180008c17  mov     ecx, [rdx]; this
0x180008c19  mov     [rsp+14F0h+var_14C8], ecx
0x180008c1d  mov     eax, [rdx+4]
0x180008c20  mov     [rsp+14F0h+var_14C4], eax
0x180008c24  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008c29  mov     ebx, eax
0x180008c2b  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180008c33  mov     ecx, r15d
0x180008c36  lea     eax, [r15+8]
0x180008c3a  cmp     dword ptr [rdx+8], 1
0x180008c3e  cmovz   ecx, eax
0x180008c41  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008c45  lea     ecx, [rax-7]
0x180008c48  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180008c50  inc     ecx
0x180008c52  mov     [rsp+14F0h+var_14C0], ecx
0x180008c56  mov     [rsp+14F0h+var_14B8], r15
0x180008c5b  call    cs:__imp_GetCurrentThreadId
0x180008c62  nop     dword ptr [rax+rax+00h]
0x180008c67  mov     [rsp+14F0h+var_14B0], eax
0x180008c6b  lea     rax, aWil; "wil"
0x180008c72  mov     [rsp+14F0h+var_1498], rax
0x180008c77  mov     [rsp+14F0h+var_1490], esi
0x180008c7b  mov     [rsp+14F0h+var_148C], ebx
0x180008c7f  mov     [rsp+14F0h+var_14A8], r15
0x180008c84  mov     [rsp+14F0h+var_14A0], r15
0x180008c89  mov     [rbp+13F0h+var_1448], rdi
0x180008c8d  mov     [rbp+13F0h+var_1440], r14
0x180008c91  mov     [rsp+14F0h+var_1488], r15
0x180008c96  xorps   xmm0, xmm0
0x180008c99  xor     eax, eax
0x180008c9b  movups  [rbp+13F0h+var_1468], xmm0
0x180008c9f  mov     [rbp+13F0h+var_1458], rax
0x180008ca3  xorps   xmm1, xmm1
0x180008ca6  movups  [rsp+14F0h+var_1480], xmm1
0x180008cab  mov     [rbp+13F0h+var_1470], rax
0x180008caf  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008cb6  test    rax, rax
0x180008cb9  jz      short loc_180008CC6
0x180008cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc0  mov     [rbp+13F0h+var_1450], rax
0x180008cc4  jmp     short loc_180008CCA
0x180008cc6  mov     [rbp+13F0h+var_1450], r15
0x180008cca  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008cd1  test    rax, rax
0x180008cd4  jz      short loc_180008CE0
0x180008cd6  lea     rcx, [rsp+14F0h+var_14D0]
0x180008cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008ce7  test    rax, rax
0x180008cea  jz      short loc_180008D00
0x180008cec  mov     r8d, 400h
0x180008cf2  lea     rdx, [rbp+13F0h+var_1430]
0x180008cf6  lea     rcx, [rsp+14F0h+var_14D0]
0x180008cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d00  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008d07  test    rax, rax
0x180008d0a  jz      short loc_180008D16
0x180008d0c  lea     rcx, [rsp+14F0h+var_14D0]
0x180008d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d16  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008d1d  test    rax, rax
0x180008d20  jz      short loc_180008D33
0x180008d22  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008d27  jnz     short loc_180008D33
0x180008d29  lea     rcx, [rsp+14F0h+var_14D0]
0x180008d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d33  cmp     [rsp+14F0h+var_14C8], r15d
0x180008d38  jge     loc_180008E53
0x180008d3e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180008d45  jnz     short loc_180008D6C
0x180008d47  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008d4e  test    rax, rax
0x180008d51  jz      short loc_180008D5C
0x180008d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d58  test    al, al
0x180008d5a  jmp     short loc_180008D6A
0x180008d5c  call    cs:__imp_IsDebuggerPresent
0x180008d63  nop     dword ptr [rax+rax+00h]
0x180008d68  test    eax, eax
0x180008d6a  jz      short loc_180008D73
0x180008d6c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008d71  jz      short loc_180008D99
0x180008d73  mov     rax, cs:g_pfnResultLoggingCallback
0x180008d7a  test    rax, rax
0x180008d7d  jz      short loc_180008DF8
0x180008d7f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008d86  jnz     short loc_180008DF8
0x180008d88  xor     r8d, r8d
0x180008d8b  xor     edx, edx
0x180008d8d  lea     rcx, [rsp+14F0h+var_14D0]
0x180008d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d97  jmp     short loc_180008DF8
0x180008d99  mov     ebx, 800h
0x180008d9e  mov     rax, cs:g_pfnResultLoggingCallback
0x180008da5  test    rax, rax
0x180008da8  jz      short loc_180008DC7
0x180008daa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008db1  jnz     short loc_180008DC7
0x180008db3  mov     r8d, ebx
0x180008db6  lea     rdx, [rbp+13F0h+OutputString]
0x180008dbd  lea     rcx, [rsp+14F0h+var_14D0]
0x180008dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dc7  cmp     [rbp+13F0h+OutputString], r15w
0x180008dcf  jnz     short loc_180008DE5
0x180008dd1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008dd6  mov     rdx, rbx; unsigned __int16 *
0x180008dd9  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008de0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008de5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008dec  call    cs:__imp_OutputDebugStringW
0x180008df3  nop     dword ptr [rax+rax+00h]
0x180008df8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180008dfd  jnz     short loc_180008E08
0x180008dff  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180008e06  jz      short loc_180008E1A
0x180008e08  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008e0f  test    rax, rax
0x180008e12  jz      short loc_180008E1A
0x180008e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e19  nop
0x180008e1a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180008e1f  jnz     short loc_180008E48
0x180008e21  mov     rcx, [rbp+13F0h+var_30]
0x180008e28  xor     rcx, rsp; StackCookie
0x180008e2b  call    __security_check_cookie
0x180008e30  mov     rbx, [rsp+14F0h+arg_10]
0x180008e38  add     rsp, 14D0h
0x180008e3f  pop     r15
0x180008e41  pop     r14
0x180008e43  pop     rdi
0x180008e44  pop     rsi
0x180008e45  pop     rbp
0x180008e46  retn
0x180008e48  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008e4d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008e53  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
