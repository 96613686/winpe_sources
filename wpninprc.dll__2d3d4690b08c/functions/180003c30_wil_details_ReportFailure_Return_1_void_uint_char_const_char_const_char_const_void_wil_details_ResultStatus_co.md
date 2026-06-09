# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003c30`
- end: `0x180003ec6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003718`

## callees

- `0x180001510`
- `0x18000209e`
- `0x180002554`
- `0x180003c30`
- `0x180005108`
- `0x180005834`
- `0x180005910`
- `0x180006680`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cdb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003dd6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003dd6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003e60`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003e60`

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
0x180003c30  mov     [rsp-8+arg_10], rbx
0x180003c35  push    rbp
0x180003c36  push    rsi
0x180003c37  push    rdi
0x180003c38  push    r14
0x180003c3a  push    r15
0x180003c3c  lea     rbp, [rsp-13D0h]
0x180003c44  mov     eax, 14D0h
0x180003c49  call    _alloca_probe
0x180003c4e  sub     rsp, rax
0x180003c51  mov     rax, cs:__security_cookie
0x180003c58  xor     rax, rsp
0x180003c5b  mov     [rbp+13F0h+var_30], rax
0x180003c62  mov     esi, edx
0x180003c64  mov     r14, rcx
0x180003c67  mov     rdi, [rbp+13F0h+arg_28]
0x180003c6e  xor     edx, edx; Val
0x180003c70  mov     r8d, 98h; Size
0x180003c76  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003c7b  call    memset_0
0x180003c80  nop
0x180003c81  xor     r15d, r15d
0x180003c84  mov     [rbp+13F0h+OutputString], r15w
0x180003c8c  mov     [rbp+13F0h+var_1430], r15b
0x180003c90  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003c97  mov     ecx, [rdx]; this
0x180003c99  mov     [rsp+14F0h+var_14C8], ecx
0x180003c9d  mov     eax, [rdx+4]
0x180003ca0  mov     [rsp+14F0h+var_14C4], eax
0x180003ca4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003ca9  mov     ebx, eax
0x180003cab  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003cb3  mov     ecx, r15d
0x180003cb6  lea     eax, [r15+8]
0x180003cba  cmp     dword ptr [rdx+8], 1
0x180003cbe  cmovz   ecx, eax
0x180003cc1  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003cc5  lea     ecx, [rax-7]
0x180003cc8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003cd0  inc     ecx
0x180003cd2  mov     [rsp+14F0h+var_14C0], ecx
0x180003cd6  mov     [rsp+14F0h+var_14B8], r15
0x180003cdb  call    cs:__imp_GetCurrentThreadId
0x180003ce1  mov     [rsp+14F0h+var_14B0], eax
0x180003ce5  lea     rax, aWil; "wil"
0x180003cec  mov     [rsp+14F0h+var_1498], rax
0x180003cf1  mov     [rsp+14F0h+var_1490], esi
0x180003cf5  mov     [rsp+14F0h+var_148C], ebx
0x180003cf9  mov     [rsp+14F0h+var_14A8], r15
0x180003cfe  mov     [rsp+14F0h+var_14A0], r15
0x180003d03  mov     [rbp+13F0h+var_1448], rdi
0x180003d07  mov     [rbp+13F0h+var_1440], r14
0x180003d0b  mov     [rsp+14F0h+var_1488], r15
0x180003d10  xorps   xmm0, xmm0
0x180003d13  xor     eax, eax
0x180003d15  movups  [rbp+13F0h+var_1468], xmm0
0x180003d19  mov     [rbp+13F0h+var_1458], rax
0x180003d1d  xorps   xmm1, xmm1
0x180003d20  movups  [rsp+14F0h+var_1480], xmm1
0x180003d25  mov     [rbp+13F0h+var_1470], rax
0x180003d29  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003d30  test    rax, rax
0x180003d33  jz      short loc_180003D40
0x180003d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d3a  mov     [rbp+13F0h+var_1450], rax
0x180003d3e  jmp     short loc_180003D44
0x180003d40  mov     [rbp+13F0h+var_1450], r15
0x180003d44  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003d4b  test    rax, rax
0x180003d4e  jz      short loc_180003D5A
0x180003d50  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d5a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003d61  test    rax, rax
0x180003d64  jz      short loc_180003D7A
0x180003d66  mov     r8d, 400h
0x180003d6c  lea     rdx, [rbp+13F0h+var_1430]
0x180003d70  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d7a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003d81  test    rax, rax
0x180003d84  jz      short loc_180003D90
0x180003d86  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d90  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003d97  test    rax, rax
0x180003d9a  jz      short loc_180003DAD
0x180003d9c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003da1  jnz     short loc_180003DAD
0x180003da3  lea     rcx, [rsp+14F0h+var_14D0]
0x180003da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dad  cmp     [rsp+14F0h+var_14C8], r15d
0x180003db2  jge     loc_180003EC0
0x180003db8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003dbf  jnz     short loc_180003DE0
0x180003dc1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003dc8  test    rax, rax
0x180003dcb  jz      short loc_180003DD6
0x180003dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dd2  test    al, al
0x180003dd4  jmp     short loc_180003DDE
0x180003dd6  call    cs:__imp_IsDebuggerPresent
0x180003ddc  test    eax, eax
0x180003dde  jz      short loc_180003DE7
0x180003de0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003de5  jz      short loc_180003E0D
0x180003de7  mov     rax, cs:g_pfnResultLoggingCallback
0x180003dee  test    rax, rax
0x180003df1  jz      short loc_180003E66
0x180003df3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003dfa  jnz     short loc_180003E66
0x180003dfc  xor     r8d, r8d
0x180003dff  xor     edx, edx
0x180003e01  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0b  jmp     short loc_180003E66
0x180003e0d  mov     ebx, 800h
0x180003e12  mov     rax, cs:g_pfnResultLoggingCallback
0x180003e19  test    rax, rax
0x180003e1c  jz      short loc_180003E3B
0x180003e1e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003e25  jnz     short loc_180003E3B
0x180003e27  mov     r8d, ebx
0x180003e2a  lea     rdx, [rbp+13F0h+OutputString]
0x180003e31  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3b  cmp     [rbp+13F0h+OutputString], r15w
0x180003e43  jnz     short loc_180003E59
0x180003e45  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003e4a  mov     rdx, rbx; unsigned __int16 *
0x180003e4d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003e54  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003e59  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003e60  call    cs:__imp_OutputDebugStringW
0x180003e66  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003e6b  jnz     short loc_180003E76
0x180003e6d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003e74  jz      short loc_180003E88
0x180003e76  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003e7d  test    rax, rax
0x180003e80  jz      short loc_180003E88
0x180003e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e87  nop
0x180003e88  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003e8d  jnz     short loc_180003EB5
0x180003e8f  mov     rcx, [rbp+13F0h+var_30]
0x180003e96  xor     rcx, rsp; StackCookie
0x180003e99  call    __security_check_cookie
0x180003e9e  mov     rbx, [rsp+14F0h+arg_10]
0x180003ea6  add     rsp, 14D0h
0x180003ead  pop     r15
0x180003eaf  pop     r14
0x180003eb1  pop     rdi
0x180003eb2  pop     rsi
0x180003eb3  pop     rbp
0x180003eb4  retn
0x180003eb5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003eba  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003ec0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
