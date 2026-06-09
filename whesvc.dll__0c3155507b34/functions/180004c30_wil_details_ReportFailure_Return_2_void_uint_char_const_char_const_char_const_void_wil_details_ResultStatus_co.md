# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004c30`
- end: `0x180004f30`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180004614`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x1800046a0`
- `0x180004c30`
- `0x180005414`
- `0x1800056d0`
- `0x180005974`
- `0x18000626c`
- `0x180006348`
- `0x1800265e0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d51`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004ecd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004ecd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004e44`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004e44`

## pseudocode

```c
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
    ModuleName = wil::details::g_pfnGetModuleName(v19);
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
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v19) == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v19);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x180004c30  push    rbp
0x180004c32  push    rbx
0x180004c33  push    rsi
0x180004c34  push    rdi
0x180004c35  push    r12
0x180004c37  push    r13
0x180004c39  push    r14
0x180004c3b  push    r15
0x180004c3d  lea     rbp, [rsp-1408h]
0x180004c45  mov     eax, 1508h
0x180004c4a  call    _alloca_probe
0x180004c4f  sub     rsp, rax
0x180004c52  mov     rax, cs:__security_cookie
0x180004c59  xor     rax, rsp
0x180004c5c  mov     [rbp+1440h+var_50], rax
0x180004c63  mov     r12, r9
0x180004c66  mov     r15, r8
0x180004c69  mov     r14d, edx
0x180004c6c  mov     rsi, rcx
0x180004c6f  mov     r13, [rbp+1440h+arg_20]
0x180004c76  mov     rax, [rbp+1440h+arg_28]
0x180004c7d  mov     [rsp+1540h+var_1500], rax
0x180004c82  xor     edx, edx; Val
0x180004c84  mov     r8d, 98h; Size
0x180004c8a  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180004c8f  call    memset_0
0x180004c94  nop
0x180004c95  xor     eax, eax
0x180004c97  mov     [rbp+1440h+OutputString], ax
0x180004c9e  mov     [rbp+1440h+var_1450], al
0x180004ca1  mov     rdi, [rbp+1440h+arg_30]
0x180004ca8  mov     ebx, [rdi]
0x180004caa  mov     [rsp+1540h+var_14E8], ebx
0x180004cae  mov     eax, [rdi+4]
0x180004cb1  mov     [rsp+1540h+var_14E4], eax
0x180004cb5  test    ebx, ebx
0x180004cb7  js      short loc_180004CF9
0x180004cb9  mov     [rsp+1540h+var_1508], 0
0x180004cc1  mov     ebx, 8007029Ch
0x180004cc6  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180004cca  mov     rax, [rsp+1540h+var_1500]
0x180004ccf  mov     [rsp+1540h+var_1518], rax; __int64
0x180004cd4  mov     [rsp+1540h+var_1520], r13; __int64
0x180004cd9  mov     r9, r12; int
0x180004cdc  mov     r8, r15; int
0x180004cdf  mov     edx, r14d; int
0x180004ce2  mov     rcx, rsi; int
0x180004ce5  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004cea  mov     [rsp+1540h+var_14E8], ebx
0x180004cee  mov     ecx, ebx; this
0x180004cf0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004cf5  mov     [rsp+1540h+var_14E4], eax
0x180004cf9  mov     ecx, ebx; this
0x180004cfb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004d00  mov     ebx, eax
0x180004d02  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180004d0a  mov     ecx, [rbp+1440h+arg_48]
0x180004d10  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180004d14  cmp     dword ptr [rdi+8], 1
0x180004d18  jnz     short loc_180004D21
0x180004d1a  or      ecx, 8
0x180004d1d  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180004d21  mov     ecx, 1
0x180004d26  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004d2e  inc     ecx
0x180004d30  mov     [rsp+1540h+var_14E0], ecx
0x180004d34  mov     rax, [rbp+1440h+arg_38]
0x180004d3b  xor     edi, edi
0x180004d3d  test    rax, rax
0x180004d40  jz      short loc_180004D4C
0x180004d42  cmp     [rax], di
0x180004d45  mov     [rsp+1540h+var_14D8], rax
0x180004d4a  jnz     short loc_180004D51
0x180004d4c  mov     [rsp+1540h+var_14D8], rdi
0x180004d51  call    cs:__imp_GetCurrentThreadId
0x180004d57  mov     [rsp+1540h+var_14D0], eax
0x180004d5b  mov     [rbp+1440h+var_14B8], r15
0x180004d5f  mov     [rbp+1440h+var_14B0], r14d
0x180004d63  mov     [rbp+1440h+var_14AC], ebx
0x180004d66  mov     [rsp+1540h+var_14C8], r13
0x180004d6b  mov     [rbp+1440h+var_14C0], r12
0x180004d6f  mov     rax, [rsp+1540h+var_1500]
0x180004d74  mov     [rbp+1440h+var_1468], rax
0x180004d78  mov     [rbp+1440h+var_1460], rsi
0x180004d7c  mov     [rbp+1440h+var_14A8], rdi
0x180004d80  xorps   xmm0, xmm0
0x180004d83  xor     eax, eax
0x180004d85  movups  [rbp+1440h+var_1488], xmm0
0x180004d89  mov     [rbp+1440h+var_1478], rax
0x180004d8d  xorps   xmm1, xmm1
0x180004d90  movups  [rbp+1440h+var_14A0], xmm1
0x180004d94  mov     [rbp+1440h+var_1490], rax
0x180004d98  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004d9f  test    rax, rax
0x180004da2  jz      short loc_180004DAF
0x180004da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004da9  mov     [rbp+1440h+var_1470], rax
0x180004dad  jmp     short loc_180004DB3
0x180004daf  mov     [rbp+1440h+var_1470], rdi
0x180004db3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004dba  test    rax, rax
0x180004dbd  jz      short loc_180004DC9
0x180004dbf  lea     rcx, [rsp+1540h+var_14F0]
0x180004dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dc9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004dd0  test    rax, rax
0x180004dd3  jz      short loc_180004DE9
0x180004dd5  mov     r8d, 400h
0x180004ddb  lea     rdx, [rbp+1440h+var_1450]
0x180004ddf  lea     rcx, [rsp+1540h+var_14F0]
0x180004de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004de9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004df0  test    rax, rax
0x180004df3  jz      short loc_180004DFF
0x180004df5  lea     rcx, [rsp+1540h+var_14F0]
0x180004dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004e06  test    rax, rax
0x180004e09  jz      short loc_180004E1C
0x180004e0b  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180004e10  jnz     short loc_180004E1C
0x180004e12  lea     rcx, [rsp+1540h+var_14F0]
0x180004e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e1c  cmp     [rsp+1540h+var_14E8], edi
0x180004e20  jge     loc_180004F2A
0x180004e26  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004e2d  jnz     short loc_180004E4E
0x180004e2f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004e36  test    rax, rax
0x180004e39  jz      short loc_180004E44
0x180004e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e40  test    al, al
0x180004e42  jmp     short loc_180004E4C
0x180004e44  call    cs:__imp_IsDebuggerPresent
0x180004e4a  test    eax, eax
0x180004e4c  jz      short loc_180004E55
0x180004e4e  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180004e53  jz      short loc_180004E7B
0x180004e55  mov     rax, cs:g_pfnResultLoggingCallback
0x180004e5c  test    rax, rax
0x180004e5f  jz      short loc_180004ED3
0x180004e61  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004e68  jnz     short loc_180004ED3
0x180004e6a  xor     r8d, r8d
0x180004e6d  xor     edx, edx
0x180004e6f  lea     rcx, [rsp+1540h+var_14F0]
0x180004e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e79  jmp     short loc_180004ED3
0x180004e7b  mov     ebx, 800h
0x180004e80  mov     rax, cs:g_pfnResultLoggingCallback
0x180004e87  test    rax, rax
0x180004e8a  jz      short loc_180004EA9
0x180004e8c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004e93  jnz     short loc_180004EA9
0x180004e95  mov     r8d, ebx
0x180004e98  lea     rdx, [rbp+1440h+OutputString]
0x180004e9f  lea     rcx, [rsp+1540h+var_14F0]
0x180004ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ea9  cmp     [rbp+1440h+OutputString], di
0x180004eb0  jnz     short loc_180004EC6
0x180004eb2  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180004eb7  mov     rdx, rbx; unsigned __int16 *
0x180004eba  lea     rcx, [rbp+1440h+OutputString]; this
0x180004ec1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004ec6  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180004ecd  call    cs:__imp_OutputDebugStringW
0x180004ed3  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180004ed8  jnz     short loc_180004EE3
0x180004eda  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004ee1  jz      short loc_180004EF5
0x180004ee3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004eea  test    rax, rax
0x180004eed  jz      short loc_180004EF5
0x180004eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ef4  nop
0x180004ef5  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180004efa  jnz     short loc_180004F1F
0x180004efc  mov     rcx, [rbp+1440h+var_50]
0x180004f03  xor     rcx, rsp; StackCookie
0x180004f06  call    __security_check_cookie
0x180004f0b  add     rsp, 1508h
0x180004f12  pop     r15
0x180004f14  pop     r14
0x180004f16  pop     r13
0x180004f18  pop     r12
0x180004f1a  pop     rdi
0x180004f1b  pop     rsi
0x180004f1c  pop     rbx
0x180004f1d  pop     rbp
0x180004f1e  retn
0x180004f1f  lea     rcx, [rsp+1540h+var_14F0]; this
0x180004f24  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004f2a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
