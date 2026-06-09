# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14002c75c`
- end: `0x14002ca08`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14002c4c0`

## callees

- `0x140006314`
- `0x140011cc8`
- `0x140014f34`
- `0x140018ab4`
- `0x140019420`
- `0x14001b500`
- `0x14002c75c`
- `0x14009d330`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14002c900`
- `KERNEL32!IsDebuggerPresent` at `0x14002c900`
- `KERNEL32!OutputDebugStringW` at `0x14002c99c`
- `KERNEL32!OutputDebugStringW` at `0x14002c99c`
- `KERNEL32!GetCurrentThreadId` at `0x14002c805`
- `KERNEL32!GetCurrentThreadId` at `0x14002c805`

## pseudocode

```c
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
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
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
0x14002c75c  mov     [rsp-8+arg_18], rbx
0x14002c761  push    rbp
0x14002c762  push    rsi
0x14002c763  push    rdi
0x14002c764  push    r12
0x14002c766  push    r13
0x14002c768  push    r14
0x14002c76a  push    r15
0x14002c76c  lea     rbp, [rsp-13C0h]
0x14002c774  mov     eax, 14C0h
0x14002c779  call    _alloca_probe
0x14002c77e  sub     rsp, rax
0x14002c781  mov     r14, r8
0x14002c784  mov     esi, edx
0x14002c786  mov     r15, rcx
0x14002c789  mov     rdi, [rbp+13F0h+arg_28]
0x14002c790  xor     r13d, r13d
0x14002c793  cmp     cs:g_pfnThrowPlatformException, r13
0x14002c79a  setnz   r12b
0x14002c79e  xor     edx, edx; Val
0x14002c7a0  mov     r8d, 98h; Size
0x14002c7a6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14002c7ab  call    memset_0
0x14002c7b0  nop
0x14002c7b1  mov     [rbp+13F0h+OutputString], r13w
0x14002c7b9  mov     [rbp+13F0h+var_1430], r13b
0x14002c7bd  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14002c7c4  mov     ecx, [rdx]; this
0x14002c7c6  mov     [rsp+14F0h+var_14C8], ecx
0x14002c7ca  mov     eax, [rdx+4]
0x14002c7cd  mov     [rsp+14F0h+var_14C4], eax
0x14002c7d1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14002c7d6  mov     ebx, eax
0x14002c7d8  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x14002c7dd  mov     ecx, r13d
0x14002c7e0  lea     eax, [r13+8]
0x14002c7e4  cmp     dword ptr [rdx+8], 1
0x14002c7e8  cmovz   ecx, eax
0x14002c7eb  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14002c7ef  lea     ecx, [rax-7]
0x14002c7f2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14002c7fa  inc     ecx
0x14002c7fc  mov     [rsp+14F0h+var_14C0], ecx
0x14002c800  mov     [rsp+14F0h+var_14B8], r13
0x14002c805  call    cs:__imp_GetCurrentThreadId
0x14002c80b  mov     [rsp+14F0h+var_14B0], eax
0x14002c80f  mov     [rsp+14F0h+var_1498], r14
0x14002c814  mov     [rsp+14F0h+var_1490], esi
0x14002c818  mov     [rsp+14F0h+var_148C], ebx
0x14002c81c  mov     [rsp+14F0h+var_14A8], r13
0x14002c821  mov     [rsp+14F0h+var_14A0], r13
0x14002c826  mov     [rbp+13F0h+var_1448], rdi
0x14002c82a  mov     [rbp+13F0h+var_1440], r15
0x14002c82e  mov     [rsp+14F0h+var_1488], r13
0x14002c833  xorps   xmm0, xmm0
0x14002c836  xor     eax, eax
0x14002c838  movups  [rbp+13F0h+var_1468], xmm0
0x14002c83c  mov     [rbp+13F0h+var_1458], rax
0x14002c840  xorps   xmm1, xmm1
0x14002c843  movups  [rsp+14F0h+var_1480], xmm1
0x14002c848  mov     [rbp+13F0h+var_1470], rax
0x14002c84c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14002c853  test    rax, rax
0x14002c856  jz      short loc_14002C863
0x14002c858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c85d  mov     [rbp+13F0h+var_1450], rax
0x14002c861  jmp     short loc_14002C867
0x14002c863  mov     [rbp+13F0h+var_1450], r13
0x14002c867  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14002c86e  test    rax, rax
0x14002c871  jz      short loc_14002C87D
0x14002c873  lea     rcx, [rsp+14F0h+var_14D0]
0x14002c878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c87d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14002c884  test    rax, rax
0x14002c887  jz      short loc_14002C89D
0x14002c889  mov     r8d, 400h
0x14002c88f  lea     rdx, [rbp+13F0h+var_1430]
0x14002c893  lea     rcx, [rsp+14F0h+var_14D0]
0x14002c898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c89d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14002c8a4  test    rax, rax
0x14002c8a7  jz      short loc_14002C8B3
0x14002c8a9  lea     rcx, [rsp+14F0h+var_14D0]
0x14002c8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c8b3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14002c8ba  test    rax, rax
0x14002c8bd  jz      short loc_14002C8D5
0x14002c8bf  test    r12b, r12b
0x14002c8c2  jnz     short loc_14002C8D5
0x14002c8c4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14002c8c9  jnz     short loc_14002C8D5
0x14002c8cb  lea     rcx, [rsp+14F0h+var_14D0]
0x14002c8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c8d5  cmp     [rsp+14F0h+var_14C8], r13d
0x14002c8da  jl      short loc_14002C8E2
0x14002c8dc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14002c8e2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14002c8e9  jnz     short loc_14002C90A
0x14002c8eb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14002c8f2  test    rax, rax
0x14002c8f5  jz      short loc_14002C900
0x14002c8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c8fc  test    al, al
0x14002c8fe  jmp     short loc_14002C908
0x14002c900  call    cs:__imp_IsDebuggerPresent
0x14002c906  test    eax, eax
0x14002c908  jz      short loc_14002C913
0x14002c90a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14002c90f  mov     bl, 1
0x14002c911  jz      short loc_14002C916
0x14002c913  mov     bl, r13b
0x14002c916  test    r12b, r12b
0x14002c919  jnz     short loc_14002C945
0x14002c91b  test    bl, bl
0x14002c91d  jnz     short loc_14002C945
0x14002c91f  mov     rax, cs:g_pfnResultLoggingCallback
0x14002c926  test    rax, rax
0x14002c929  jz      short loc_14002C9A2
0x14002c92b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14002c932  jnz     short loc_14002C9A2
0x14002c934  xor     r8d, r8d
0x14002c937  xor     edx, edx
0x14002c939  lea     rcx, [rsp+14F0h+var_14D0]
0x14002c93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c943  jmp     short loc_14002C9A2
0x14002c945  mov     edi, 800h
0x14002c94a  mov     rax, cs:g_pfnResultLoggingCallback
0x14002c951  test    rax, rax
0x14002c954  jz      short loc_14002C973
0x14002c956  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14002c95d  jnz     short loc_14002C973
0x14002c95f  mov     r8d, edi
0x14002c962  lea     rdx, [rbp+13F0h+OutputString]
0x14002c969  lea     rcx, [rsp+14F0h+var_14D0]
0x14002c96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c973  cmp     [rbp+13F0h+OutputString], r13w
0x14002c97b  jnz     short loc_14002C991
0x14002c97d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14002c982  mov     rdx, rdi; unsigned __int16 *
0x14002c985  lea     rcx, [rbp+13F0h+OutputString]; this
0x14002c98c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14002c991  test    bl, bl
0x14002c993  jz      short loc_14002C9A2
0x14002c995  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14002c99c  call    cs:__imp_OutputDebugStringW
0x14002c9a2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14002c9a7  jnz     short loc_14002C9B2
0x14002c9a9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14002c9b0  jz      short loc_14002C9C4
0x14002c9b2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14002c9b9  test    rax, rax
0x14002c9bc  jz      short loc_14002C9C4
0x14002c9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c9c3  nop
0x14002c9c4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14002c9c9  jz      short loc_14002C9D6
0x14002c9cb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14002c9d0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14002c9d6  test    r12b, r12b
0x14002c9d9  jz      short loc_14002C9F3
0x14002c9db  lea     rdx, [rbp+13F0h+OutputString]
0x14002c9e2  lea     rcx, [rsp+14F0h+var_14D0]
0x14002c9e7  mov     rax, cs:g_pfnThrowPlatformException
0x14002c9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c9f3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14002c9f8  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x14002c9fd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14002ca02  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
