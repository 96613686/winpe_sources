# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180006b48`
- end: `0x180006def`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000660c`

## callees

- `0x180006b48`
- `0x1800091d4`
- `0x18000b96c`
- `0x18000e79c`
- `0x18000eab4`
- `0x18001c12a`
- `0x18001c150`
- `0x18001c210`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006bf2`
- `KERNEL32!GetCurrentThreadId` at `0x180006bf2`
- `KERNEL32!IsDebuggerPresent` at `0x180006cf3`
- `KERNEL32!IsDebuggerPresent` at `0x180006cf3`
- `KERNEL32!OutputDebugStringW` at `0x180006d83`
- `KERNEL32!OutputDebugStringW` at `0x180006d83`

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
0x180006b48  mov     [rsp-8+arg_10], rbx
0x180006b4d  push    rbp
0x180006b4e  push    rsi
0x180006b4f  push    rdi
0x180006b50  push    r14
0x180006b52  push    r15
0x180006b54  lea     rbp, [rsp-13D0h]
0x180006b5c  mov     eax, 14D0h
0x180006b61  call    _alloca_probe
0x180006b66  sub     rsp, rax
0x180006b69  mov     rax, cs:__security_cookie
0x180006b70  xor     rax, rsp
0x180006b73  mov     [rbp+13F0h+var_30], rax
0x180006b7a  mov     rdi, [rbp+13F0h+arg_28]
0x180006b81  mov     esi, edx
0x180006b83  mov     r14, rcx
0x180006b86  xor     edx, edx; Val
0x180006b88  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006b8d  mov     r8d, 98h; Size
0x180006b93  call    memset_0
0x180006b98  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180006b9f  xor     r15d, r15d
0x180006ba2  mov     [rbp+13F0h+OutputString], r15w
0x180006baa  mov     [rbp+13F0h+var_1430], r15b
0x180006bae  mov     ecx, [rdx]; this
0x180006bb0  mov     eax, [rdx+4]
0x180006bb3  mov     [rsp+14F0h+var_14C8], ecx
0x180006bb7  mov     [rsp+14F0h+var_14C4], eax
0x180006bbb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006bc0  cmp     dword ptr [rdx+8], 1
0x180006bc4  mov     ebx, eax
0x180006bc6  lea     eax, [r15+8]
0x180006bca  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180006bd2  mov     ecx, r15d
0x180006bd5  cmovz   ecx, eax
0x180006bd8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006bdc  lea     ecx, [rax-7]
0x180006bdf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180006be7  inc     ecx
0x180006be9  mov     [rsp+14F0h+var_14B8], r15
0x180006bee  mov     [rsp+14F0h+var_14C0], ecx
0x180006bf2  call    cs:__imp_GetCurrentThreadId
0x180006bf9  nop     dword ptr [rax+rax+00h]
0x180006bfe  xorps   xmm0, xmm0
0x180006c01  mov     [rsp+14F0h+var_1490], esi
0x180006c05  mov     [rsp+14F0h+var_14B0], eax
0x180006c09  xorps   xmm1, xmm1
0x180006c0c  lea     rax, aWil; "wil"
0x180006c13  mov     [rsp+14F0h+var_148C], ebx
0x180006c17  mov     [rsp+14F0h+var_1498], rax
0x180006c1c  xor     eax, eax
0x180006c1e  mov     [rbp+13F0h+var_1458], rax
0x180006c22  mov     [rbp+13F0h+var_1470], rax
0x180006c26  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006c2d  mov     [rsp+14F0h+var_14A8], r15
0x180006c32  mov     [rsp+14F0h+var_14A0], r15
0x180006c37  mov     [rbp+13F0h+var_1448], rdi
0x180006c3b  mov     [rbp+13F0h+var_1440], r14
0x180006c3f  mov     [rsp+14F0h+var_1488], r15
0x180006c44  movups  [rbp+13F0h+var_1468], xmm0
0x180006c48  movups  [rsp+14F0h+var_1480], xmm1
0x180006c4d  test    rax, rax
0x180006c50  jz      short loc_180006C5D
0x180006c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c57  mov     [rbp+13F0h+var_1450], rax
0x180006c5b  jmp     short loc_180006C61
0x180006c5d  mov     [rbp+13F0h+var_1450], r15
0x180006c61  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006c68  test    rax, rax
0x180006c6b  jz      short loc_180006C77
0x180006c6d  lea     rcx, [rsp+14F0h+var_14D0]
0x180006c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c77  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006c7e  test    rax, rax
0x180006c81  jz      short loc_180006C97
0x180006c83  mov     r8d, 400h
0x180006c89  lea     rdx, [rbp+13F0h+var_1430]
0x180006c8d  lea     rcx, [rsp+14F0h+var_14D0]
0x180006c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c97  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006c9e  test    rax, rax
0x180006ca1  jz      short loc_180006CAD
0x180006ca3  lea     rcx, [rsp+14F0h+var_14D0]
0x180006ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cad  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006cb4  test    rax, rax
0x180006cb7  jz      short loc_180006CCA
0x180006cb9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006cbe  jnz     short loc_180006CCA
0x180006cc0  lea     rcx, [rsp+14F0h+var_14D0]
0x180006cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cca  cmp     [rsp+14F0h+var_14C8], r15d
0x180006ccf  jge     loc_180006DDE
0x180006cd5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180006cdc  jnz     short loc_180006D03
0x180006cde  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006ce5  test    rax, rax
0x180006ce8  jz      short loc_180006CF3
0x180006cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cef  test    al, al
0x180006cf1  jmp     short loc_180006D01
0x180006cf3  call    cs:__imp_IsDebuggerPresent
0x180006cfa  nop     dword ptr [rax+rax+00h]
0x180006cff  test    eax, eax
0x180006d01  jz      short loc_180006D0A
0x180006d03  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006d08  jz      short loc_180006D30
0x180006d0a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d11  test    rax, rax
0x180006d14  jz      short loc_180006D8F
0x180006d16  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006d1d  jnz     short loc_180006D8F
0x180006d1f  xor     r8d, r8d
0x180006d22  lea     rcx, [rsp+14F0h+var_14D0]
0x180006d27  xor     edx, edx
0x180006d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d2e  jmp     short loc_180006D8F
0x180006d30  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d37  mov     ebx, 800h
0x180006d3c  test    rax, rax
0x180006d3f  jz      short loc_180006D5E
0x180006d41  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006d48  jnz     short loc_180006D5E
0x180006d4a  mov     r8d, ebx
0x180006d4d  lea     rdx, [rbp+13F0h+OutputString]
0x180006d54  lea     rcx, [rsp+14F0h+var_14D0]
0x180006d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d5e  cmp     [rbp+13F0h+OutputString], r15w
0x180006d66  jnz     short loc_180006D7C
0x180006d68  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006d6d  mov     rdx, rbx; unsigned __int16 *
0x180006d70  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006d77  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006d7c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006d83  call    cs:__imp_OutputDebugStringW
0x180006d8a  nop     dword ptr [rax+rax+00h]
0x180006d8f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006d94  jnz     short loc_180006D9F
0x180006d96  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180006d9d  jz      short loc_180006DB0
0x180006d9f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006da6  test    rax, rax
0x180006da9  jz      short loc_180006DB0
0x180006dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180006db5  jnz     short loc_180006DE4
0x180006db7  mov     rcx, [rbp+13F0h+var_30]
0x180006dbe  xor     rcx, rsp; StackCookie
0x180006dc1  call    __security_check_cookie
0x180006dc6  mov     rbx, [rsp+14F0h+arg_10]
0x180006dce  add     rsp, 14D0h
0x180006dd5  pop     r15
0x180006dd7  pop     r14
0x180006dd9  pop     rdi
0x180006dda  pop     rsi
0x180006ddb  pop     rbp
0x180006ddc  retn
0x180006dde  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006de4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006de9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
