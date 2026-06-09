# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18002e76c`
- end: `0x18002ea2a`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002e590`

## callees

- `0x180002f34`
- `0x180006374`
- `0x180007450`
- `0x18000819c`
- `0x18000852c`
- `0x1800086c4`
- `0x18002e76c`
- `0x1800556e0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e815`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e815`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002e9b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002e9b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e916`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e916`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x18002e76c  mov     [rsp-8+arg_18], rbx
0x18002e771  push    rbp
0x18002e772  push    rsi
0x18002e773  push    rdi
0x18002e774  push    r12
0x18002e776  push    r13
0x18002e778  push    r14
0x18002e77a  push    r15
0x18002e77c  lea     rbp, [rsp-13C0h]
0x18002e784  mov     eax, 14C0h
0x18002e789  call    _alloca_probe
0x18002e78e  sub     rsp, rax
0x18002e791  mov     r14, r8
0x18002e794  mov     esi, edx
0x18002e796  mov     r15, rcx
0x18002e799  mov     rdi, [rbp+13F0h+arg_28]
0x18002e7a0  xor     r13d, r13d
0x18002e7a3  cmp     cs:g_pfnThrowPlatformException, r13
0x18002e7aa  setnz   r12b
0x18002e7ae  xor     edx, edx; Val
0x18002e7b0  mov     r8d, 98h; Size
0x18002e7b6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18002e7bb  call    memset_0
0x18002e7c0  nop
0x18002e7c1  mov     [rbp+13F0h+OutputString], r13w
0x18002e7c9  mov     [rbp+13F0h+var_1430], r13b
0x18002e7cd  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18002e7d4  mov     ecx, [rdx]; this
0x18002e7d6  mov     [rsp+14F0h+var_14C8], ecx
0x18002e7da  mov     eax, [rdx+4]
0x18002e7dd  mov     [rsp+14F0h+var_14C4], eax
0x18002e7e1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002e7e6  mov     ebx, eax
0x18002e7e8  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18002e7ed  mov     ecx, r13d
0x18002e7f0  lea     eax, [r13+8]
0x18002e7f4  cmp     dword ptr [rdx+8], 1
0x18002e7f8  cmovz   ecx, eax
0x18002e7fb  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18002e7ff  lea     ecx, [rax-7]
0x18002e802  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002e80a  inc     ecx
0x18002e80c  mov     [rsp+14F0h+var_14C0], ecx
0x18002e810  mov     [rsp+14F0h+var_14B8], r13
0x18002e815  call    cs:__imp_GetCurrentThreadId
0x18002e81c  nop     dword ptr [rax+rax+00h]
0x18002e821  mov     [rsp+14F0h+var_14B0], eax
0x18002e825  mov     [rsp+14F0h+var_1498], r14
0x18002e82a  mov     [rsp+14F0h+var_1490], esi
0x18002e82e  mov     [rsp+14F0h+var_148C], ebx
0x18002e832  mov     [rsp+14F0h+var_14A8], r13
0x18002e837  mov     [rsp+14F0h+var_14A0], r13
0x18002e83c  mov     [rbp+13F0h+var_1448], rdi
0x18002e840  mov     [rbp+13F0h+var_1440], r15
0x18002e844  mov     [rsp+14F0h+var_1488], r13
0x18002e849  xorps   xmm0, xmm0
0x18002e84c  xor     eax, eax
0x18002e84e  movups  [rbp+13F0h+var_1468], xmm0
0x18002e852  mov     [rbp+13F0h+var_1458], rax
0x18002e856  xorps   xmm1, xmm1
0x18002e859  movups  [rsp+14F0h+var_1480], xmm1
0x18002e85e  mov     [rbp+13F0h+var_1470], rax
0x18002e862  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002e869  test    rax, rax
0x18002e86c  jz      short loc_18002E879
0x18002e86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e873  mov     [rbp+13F0h+var_1450], rax
0x18002e877  jmp     short loc_18002E87D
0x18002e879  mov     [rbp+13F0h+var_1450], r13
0x18002e87d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002e884  test    rax, rax
0x18002e887  jz      short loc_18002E893
0x18002e889  lea     rcx, [rsp+14F0h+var_14D0]
0x18002e88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e893  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002e89a  test    rax, rax
0x18002e89d  jz      short loc_18002E8B3
0x18002e89f  mov     r8d, 400h
0x18002e8a5  lea     rdx, [rbp+13F0h+var_1430]
0x18002e8a9  lea     rcx, [rsp+14F0h+var_14D0]
0x18002e8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8b3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002e8ba  test    rax, rax
0x18002e8bd  jz      short loc_18002E8C9
0x18002e8bf  lea     rcx, [rsp+14F0h+var_14D0]
0x18002e8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8c9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002e8d0  test    rax, rax
0x18002e8d3  jz      short loc_18002E8EB
0x18002e8d5  test    r12b, r12b
0x18002e8d8  jnz     short loc_18002E8EB
0x18002e8da  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002e8df  jnz     short loc_18002E8EB
0x18002e8e1  lea     rcx, [rsp+14F0h+var_14D0]
0x18002e8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8eb  cmp     [rsp+14F0h+var_14C8], r13d
0x18002e8f0  jl      short loc_18002E8F8
0x18002e8f2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002e8f8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18002e8ff  jnz     short loc_18002E926
0x18002e901  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002e908  test    rax, rax
0x18002e90b  jz      short loc_18002E916
0x18002e90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e912  test    al, al
0x18002e914  jmp     short loc_18002E924
0x18002e916  call    cs:__imp_IsDebuggerPresent
0x18002e91d  nop     dword ptr [rax+rax+00h]
0x18002e922  test    eax, eax
0x18002e924  jz      short loc_18002E92F
0x18002e926  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002e92b  mov     bl, 1
0x18002e92d  jz      short loc_18002E932
0x18002e92f  mov     bl, r13b
0x18002e932  test    r12b, r12b
0x18002e935  jnz     short loc_18002E961
0x18002e937  test    bl, bl
0x18002e939  jnz     short loc_18002E961
0x18002e93b  mov     rax, cs:g_pfnResultLoggingCallback
0x18002e942  test    rax, rax
0x18002e945  jz      short loc_18002E9C4
0x18002e947  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002e94e  jnz     short loc_18002E9C4
0x18002e950  xor     r8d, r8d
0x18002e953  xor     edx, edx
0x18002e955  lea     rcx, [rsp+14F0h+var_14D0]
0x18002e95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e95f  jmp     short loc_18002E9C4
0x18002e961  mov     edi, 800h
0x18002e966  mov     rax, cs:g_pfnResultLoggingCallback
0x18002e96d  test    rax, rax
0x18002e970  jz      short loc_18002E98F
0x18002e972  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002e979  jnz     short loc_18002E98F
0x18002e97b  mov     r8d, edi
0x18002e97e  lea     rdx, [rbp+13F0h+OutputString]
0x18002e985  lea     rcx, [rsp+14F0h+var_14D0]
0x18002e98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e98f  cmp     [rbp+13F0h+OutputString], r13w
0x18002e997  jnz     short loc_18002E9AD
0x18002e999  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002e99e  mov     rdx, rdi; unsigned __int16 *
0x18002e9a1  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002e9a8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002e9ad  test    bl, bl
0x18002e9af  jz      short loc_18002E9C4
0x18002e9b1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18002e9b8  call    cs:__imp_OutputDebugStringW
0x18002e9bf  nop     dword ptr [rax+rax+00h]
0x18002e9c4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002e9c9  jnz     short loc_18002E9D4
0x18002e9cb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18002e9d2  jz      short loc_18002E9E6
0x18002e9d4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002e9db  test    rax, rax
0x18002e9de  jz      short loc_18002E9E6
0x18002e9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9e5  nop
0x18002e9e6  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002e9eb  jz      short loc_18002E9F8
0x18002e9ed  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002e9f2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002e9f8  test    r12b, r12b
0x18002e9fb  jz      short loc_18002EA15
0x18002e9fd  lea     rdx, [rbp+13F0h+OutputString]
0x18002ea04  lea     rcx, [rsp+14F0h+var_14D0]
0x18002ea09  mov     rax, cs:g_pfnThrowPlatformException
0x18002ea10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea15  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002ea1a  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18002ea1f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002ea24  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
