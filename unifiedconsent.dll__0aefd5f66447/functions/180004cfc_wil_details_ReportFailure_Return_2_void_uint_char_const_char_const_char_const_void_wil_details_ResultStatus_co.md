# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004cfc`
- end: `0x180004ffc`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18000400c`

## callees

- `0x180002810`
- `0x180003384`
- `0x1800043b0`
- `0x180004cfc`
- `0x180009274`
- `0x180009b28`
- `0x18000adcc`
- `0x18000e140`
- `0x18000e434`
- `0x180070720`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e1d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004f99`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004f99`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004f10`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004f10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0, v20);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048, v20);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x180004cfc  push    rbp
0x180004cfe  push    rbx
0x180004cff  push    rsi
0x180004d00  push    rdi
0x180004d01  push    r12
0x180004d03  push    r13
0x180004d05  push    r14
0x180004d07  push    r15
0x180004d09  lea     rbp, [rsp-1408h]
0x180004d11  mov     eax, 1508h
0x180004d16  call    _alloca_probe
0x180004d1b  sub     rsp, rax
0x180004d1e  mov     rax, cs:__security_cookie
0x180004d25  xor     rax, rsp
0x180004d28  mov     [rbp+1440h+var_50], rax
0x180004d2f  mov     r12, r9
0x180004d32  mov     r15, r8
0x180004d35  mov     r14d, edx
0x180004d38  mov     rsi, rcx
0x180004d3b  mov     r13, [rbp+1440h+arg_20]
0x180004d42  mov     rax, [rbp+1440h+arg_28]
0x180004d49  mov     [rsp+1540h+var_1500], rax
0x180004d4e  xor     edx, edx; Val
0x180004d50  mov     r8d, 98h; Size
0x180004d56  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180004d5b  call    memset_0
0x180004d60  nop
0x180004d61  xor     eax, eax
0x180004d63  mov     [rbp+1440h+OutputString], ax
0x180004d6a  mov     [rbp+1440h+var_1450], al
0x180004d6d  mov     rdi, [rbp+1440h+arg_30]
0x180004d74  mov     ebx, [rdi]
0x180004d76  mov     [rsp+1540h+var_14E8], ebx
0x180004d7a  mov     eax, [rdi+4]
0x180004d7d  mov     [rsp+1540h+var_14E4], eax
0x180004d81  test    ebx, ebx
0x180004d83  js      short loc_180004DC5
0x180004d85  mov     [rsp+1540h+var_1508], 0
0x180004d8d  mov     ebx, 8007029Ch
0x180004d92  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180004d96  mov     rax, [rsp+1540h+var_1500]
0x180004d9b  mov     [rsp+1540h+var_1518], rax; __int64
0x180004da0  mov     [rsp+1540h+var_1520], r13; __int64
0x180004da5  mov     r9, r12; int
0x180004da8  mov     r8, r15; int
0x180004dab  mov     edx, r14d; int
0x180004dae  mov     rcx, rsi; int
0x180004db1  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004db6  mov     [rsp+1540h+var_14E8], ebx
0x180004dba  mov     ecx, ebx; this
0x180004dbc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004dc1  mov     [rsp+1540h+var_14E4], eax
0x180004dc5  mov     ecx, ebx; this
0x180004dc7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004dcc  mov     ebx, eax
0x180004dce  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180004dd6  mov     ecx, [rbp+1440h+arg_48]
0x180004ddc  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180004de0  cmp     dword ptr [rdi+8], 1
0x180004de4  jnz     short loc_180004DED
0x180004de6  or      ecx, 8
0x180004de9  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180004ded  mov     ecx, 1
0x180004df2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004dfa  inc     ecx
0x180004dfc  mov     [rsp+1540h+var_14E0], ecx
0x180004e00  mov     rax, [rbp+1440h+arg_38]
0x180004e07  xor     edi, edi
0x180004e09  test    rax, rax
0x180004e0c  jz      short loc_180004E18
0x180004e0e  cmp     [rax], di
0x180004e11  mov     [rsp+1540h+var_14D8], rax
0x180004e16  jnz     short loc_180004E1D
0x180004e18  mov     [rsp+1540h+var_14D8], rdi
0x180004e1d  call    cs:__imp_GetCurrentThreadId
0x180004e23  mov     [rsp+1540h+var_14D0], eax
0x180004e27  mov     [rbp+1440h+var_14B8], r15
0x180004e2b  mov     [rbp+1440h+var_14B0], r14d
0x180004e2f  mov     [rbp+1440h+var_14AC], ebx
0x180004e32  mov     [rsp+1540h+var_14C8], r13
0x180004e37  mov     [rbp+1440h+var_14C0], r12
0x180004e3b  mov     rax, [rsp+1540h+var_1500]
0x180004e40  mov     [rbp+1440h+var_1468], rax
0x180004e44  mov     [rbp+1440h+var_1460], rsi
0x180004e48  mov     [rbp+1440h+var_14A8], rdi
0x180004e4c  xorps   xmm0, xmm0
0x180004e4f  xor     eax, eax
0x180004e51  movups  [rbp+1440h+var_1488], xmm0
0x180004e55  mov     [rbp+1440h+var_1478], rax
0x180004e59  xorps   xmm1, xmm1
0x180004e5c  movups  [rbp+1440h+var_14A0], xmm1
0x180004e60  mov     [rbp+1440h+var_1490], rax
0x180004e64  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004e6b  test    rax, rax
0x180004e6e  jz      short loc_180004E7B
0x180004e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e75  mov     [rbp+1440h+var_1470], rax
0x180004e79  jmp     short loc_180004E7F
0x180004e7b  mov     [rbp+1440h+var_1470], rdi
0x180004e7f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004e86  test    rax, rax
0x180004e89  jz      short loc_180004E95
0x180004e8b  lea     rcx, [rsp+1540h+var_14F0]
0x180004e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e95  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004e9c  test    rax, rax
0x180004e9f  jz      short loc_180004EB5
0x180004ea1  mov     r8d, 400h
0x180004ea7  lea     rdx, [rbp+1440h+var_1450]
0x180004eab  lea     rcx, [rsp+1540h+var_14F0]
0x180004eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ebc  test    rax, rax
0x180004ebf  jz      short loc_180004ECB
0x180004ec1  lea     rcx, [rsp+1540h+var_14F0]
0x180004ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ecb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ed2  test    rax, rax
0x180004ed5  jz      short loc_180004EE8
0x180004ed7  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180004edc  jnz     short loc_180004EE8
0x180004ede  lea     rcx, [rsp+1540h+var_14F0]
0x180004ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee8  cmp     [rsp+1540h+var_14E8], edi
0x180004eec  jge     loc_180004FF6
0x180004ef2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004ef9  jnz     short loc_180004F1A
0x180004efb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004f02  test    rax, rax
0x180004f05  jz      short loc_180004F10
0x180004f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f0c  test    al, al
0x180004f0e  jmp     short loc_180004F18
0x180004f10  call    cs:__imp_IsDebuggerPresent
0x180004f16  test    eax, eax
0x180004f18  jz      short loc_180004F21
0x180004f1a  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180004f1f  jz      short loc_180004F47
0x180004f21  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f28  test    rax, rax
0x180004f2b  jz      short loc_180004F9F
0x180004f2d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004f34  jnz     short loc_180004F9F
0x180004f36  xor     r8d, r8d
0x180004f39  xor     edx, edx
0x180004f3b  lea     rcx, [rsp+1540h+var_14F0]
0x180004f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f45  jmp     short loc_180004F9F
0x180004f47  mov     ebx, 800h
0x180004f4c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f53  test    rax, rax
0x180004f56  jz      short loc_180004F75
0x180004f58  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004f5f  jnz     short loc_180004F75
0x180004f61  mov     r8d, ebx
0x180004f64  lea     rdx, [rbp+1440h+OutputString]
0x180004f6b  lea     rcx, [rsp+1540h+var_14F0]
0x180004f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f75  cmp     [rbp+1440h+OutputString], di
0x180004f7c  jnz     short loc_180004F92
0x180004f7e  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180004f83  mov     rdx, rbx; unsigned __int16 *
0x180004f86  lea     rcx, [rbp+1440h+OutputString]; this
0x180004f8d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004f92  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180004f99  call    cs:__imp_OutputDebugStringW
0x180004f9f  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180004fa4  jnz     short loc_180004FAF
0x180004fa6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004fad  jz      short loc_180004FC1
0x180004faf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004fb6  test    rax, rax
0x180004fb9  jz      short loc_180004FC1
0x180004fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc0  nop
0x180004fc1  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180004fc6  jnz     short loc_180004FEB
0x180004fc8  mov     rcx, [rbp+1440h+var_50]
0x180004fcf  xor     rcx, rsp; StackCookie
0x180004fd2  call    __security_check_cookie
0x180004fd7  add     rsp, 1508h
0x180004fde  pop     r15
0x180004fe0  pop     r14
0x180004fe2  pop     r13
0x180004fe4  pop     r12
0x180004fe6  pop     rdi
0x180004fe7  pop     rsi
0x180004fe8  pop     rbx
0x180004fe9  pop     rbp
0x180004fea  retn
0x180004feb  lea     rcx, [rsp+1540h+var_14F0]; this
0x180004ff0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004ff6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
