# wil::details::ReportFailure_CustomExceptionHelper<ComputeService::Reporting::ComputeException>(ComputeService::Reporting::ComputeException &,void *,uint,char const *,char const *,char const *,void *,ushort const *)

- ea: `0x140016bd8`
- end: `0x140016e5a`
- name: `??$ReportFailure_CustomExceptionHelper@VComputeException@Reporting@ComputeService@@@details@wil@@YAXAEAVComputeException@Reporting@ComputeService@@PEAXIPEBD221PEBG@Z`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x140016ba8`

## callees

- `0x140006098`
- `0x1400060c8`
- `0x14000a5dc`
- `0x14000ad18`
- `0x14000bb60`
- `0x14000e7a0`
- `0x14000ea34`
- `0x140016bd8`
- `0x1400282f4`
- `0x14003385c`
- `0x1400f4e40`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016c64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016c64`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140016d76`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140016d76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140016dfc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140016dfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_CustomExceptionHelper<ComputeService::Reporting::ComputeException>(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7)
{
  unsigned int v11; // ebx
  int v12; // edx
  int v13; // eax
  int v14; // edx
  int v15; // ebx
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  struct wil::ResultException *v18; // r8
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  _BYTE pExceptionObject[304]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v22; // [rsp+150h] [rbp+50h] BYREF
  int v23; // [rsp+158h] [rbp+58h]
  int v24; // [rsp+15Ch] [rbp+5Ch]
  signed __int32 v25; // [rsp+160h] [rbp+60h]
  __int64 v26; // [rsp+168h] [rbp+68h]
  DWORD CurrentThreadId; // [rsp+170h] [rbp+70h]
  __int64 v28; // [rsp+178h] [rbp+78h]
  __int64 v29; // [rsp+180h] [rbp+80h]
  __int64 v30; // [rsp+188h] [rbp+88h]
  int v31; // [rsp+190h] [rbp+90h]
  int v32; // [rsp+194h] [rbp+94h]
  __int64 v33; // [rsp+198h] [rbp+98h]
  __int128 v34; // [rsp+1A0h] [rbp+A0h]
  __int64 v35; // [rsp+1B0h] [rbp+B0h]
  __int128 v36; // [rsp+1B8h] [rbp+B8h]
  __int64 v37; // [rsp+1C8h] [rbp+C8h]
  __int64 ModuleName; // [rsp+1D0h] [rbp+D0h]
  __int64 v39; // [rsp+1D8h] [rbp+D8h]
  __int64 v40; // [rsp+1E0h] [rbp+E0h]
  _BYTE v41[1024]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR OutputString[2080]; // [rsp+5F0h] [rbp+4F0h] BYREF

  v11 = *(_DWORD *)(a1 + 32);
  memset_0(&v22, 0, 0x98u);
  v13 = wil::details::HrToNtStatus((wil::details *)v11, v12);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = v11;
  v24 = v13;
  v15 = wil::details::RecordException((wil::details *)v11, v14);
  v22 = 0;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a4;
  v31 = a3;
  v32 = v15;
  v28 = 0;
  v29 = 0;
  v39 = a7;
  v40 = a2;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v22);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v22, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v22);
  if ( wil::details::g_pfnOriginateCallback && (v22 & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(&v22);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v20)
    || (v22 & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v22, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v22, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v22, v19);
    OutputDebugStringW(OutputString);
  }
  if ( ((v22 & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v22 & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)&v22, v16);
  wil::details::SetFailureInfo((wil::details *)&v22, (const struct wil::FailureInfo *)a1, v18);
  ComputeService::Reporting::ComputeException::ComputeException(
    (ComputeService::Reporting::ComputeException *)pExceptionObject,
    (const struct ComputeService::Reporting::ComputeException *)a1);
  throw (ComputeService::Reporting::ComputeException *)pExceptionObject;
}

```

## disassembly

```asm
0x140016bd8  push    rbp
0x140016bda  push    rbx
0x140016bdb  push    rsi
0x140016bdc  push    rdi
0x140016bdd  push    r12
0x140016bdf  push    r13
0x140016be1  push    r14
0x140016be3  push    r15
0x140016be5  lea     rbp, [rsp-14F8h]
0x140016bed  mov     eax, 15F8h
0x140016bf2  call    _alloca_probe
0x140016bf7  sub     rsp, rax
0x140016bfa  mov     r14, r9
0x140016bfd  mov     esi, r8d
0x140016c00  mov     r15, rdx
0x140016c03  mov     r13, rcx
0x140016c06  mov     rdi, [rbp+1530h+arg_30]
0x140016c0d  mov     ebx, [rcx+20h]
0x140016c10  xor     edx, edx; Val
0x140016c12  mov     r8d, 98h; Size
0x140016c18  lea     rcx, [rbp+1530h+var_14E0]; void *
0x140016c1c  call    memset_0
0x140016c21  mov     ecx, ebx; this
0x140016c23  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140016c28  nop
0x140016c29  xor     r12d, r12d
0x140016c2c  mov     [rbp+1530h+OutputString], r12w
0x140016c34  mov     [rbp+1530h+var_1440], r12b
0x140016c3b  mov     [rbp+1530h+var_14D8], ebx
0x140016c3e  mov     [rbp+1530h+var_14D4], eax
0x140016c41  mov     ecx, ebx; this
0x140016c43  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140016c48  mov     ebx, eax
0x140016c4a  mov     [rbp+1530h+var_14E0], r12
0x140016c4e  lea     ecx, [r12+1]
0x140016c53  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140016c5b  inc     ecx
0x140016c5d  mov     [rbp+1530h+var_14D0], ecx
0x140016c60  mov     [rbp+1530h+var_14C8], r12
0x140016c64  call    cs:__imp_GetCurrentThreadId
0x140016c6a  mov     [rbp+1530h+var_14C0], eax
0x140016c6d  mov     [rbp+1530h+var_14A8], r14
0x140016c74  mov     [rbp+1530h+var_14A0], esi
0x140016c7a  mov     [rbp+1530h+var_149C], ebx
0x140016c80  mov     [rbp+1530h+var_14B8], r12
0x140016c84  mov     [rbp+1530h+var_14B0], r12
0x140016c8b  mov     [rbp+1530h+var_1458], rdi
0x140016c92  mov     [rbp+1530h+var_1450], r15
0x140016c99  mov     [rbp+1530h+var_1498], r12
0x140016ca0  xorps   xmm0, xmm0
0x140016ca3  xor     eax, eax
0x140016ca5  movups  [rbp+1530h+var_1478], xmm0
0x140016cac  mov     [rbp+1530h+var_1468], rax
0x140016cb3  xorps   xmm1, xmm1
0x140016cb6  movups  [rbp+1530h+var_1490], xmm1
0x140016cbd  mov     [rbp+1530h+var_1480], rax
0x140016cc4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140016ccb  test    rax, rax
0x140016cce  jz      short loc_140016CDE
0x140016cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016cd5  mov     [rbp+1530h+var_1460], rax
0x140016cdc  jmp     short loc_140016CE5
0x140016cde  mov     [rbp+1530h+var_1460], r12
0x140016ce5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140016cec  test    rax, rax
0x140016cef  jz      short loc_140016CFA
0x140016cf1  lea     rcx, [rbp+1530h+var_14E0]
0x140016cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016cfa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140016d01  test    rax, rax
0x140016d04  jz      short loc_140016D1C
0x140016d06  mov     r8d, 400h
0x140016d0c  lea     rdx, [rbp+1530h+var_1440]
0x140016d13  lea     rcx, [rbp+1530h+var_14E0]
0x140016d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016d1c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140016d23  test    rax, rax
0x140016d26  jz      short loc_140016D31
0x140016d28  lea     rcx, [rbp+1530h+var_14E0]
0x140016d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016d31  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140016d38  test    rax, rax
0x140016d3b  jz      short loc_140016D4C
0x140016d3d  test    byte ptr [rbp+1530h+var_14E0+4], 2
0x140016d41  jnz     short loc_140016D4C
0x140016d43  lea     rcx, [rbp+1530h+var_14E0]
0x140016d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016d4c  cmp     [rbp+1530h+var_14D8], r12d
0x140016d50  jl      short loc_140016D58
0x140016d52  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140016d58  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140016d5f  jnz     short loc_140016D80
0x140016d61  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140016d68  test    rax, rax
0x140016d6b  jz      short loc_140016D76
0x140016d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016d72  test    al, al
0x140016d74  jmp     short loc_140016D7E
0x140016d76  call    cs:__imp_IsDebuggerPresent
0x140016d7c  test    eax, eax
0x140016d7e  jz      short loc_140016D86
0x140016d80  test    byte ptr [rbp+1530h+var_14E0+4], 2
0x140016d84  jz      short loc_140016DAB
0x140016d86  mov     rax, cs:g_pfnResultLoggingCallback
0x140016d8d  test    rax, rax
0x140016d90  jz      short loc_140016E02
0x140016d92  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140016d99  jnz     short loc_140016E02
0x140016d9b  xor     r8d, r8d
0x140016d9e  xor     edx, edx
0x140016da0  lea     rcx, [rbp+1530h+var_14E0]
0x140016da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016da9  jmp     short loc_140016E02
0x140016dab  mov     ebx, 800h
0x140016db0  mov     rax, cs:g_pfnResultLoggingCallback
0x140016db7  test    rax, rax
0x140016dba  jz      short loc_140016DD8
0x140016dbc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140016dc3  jnz     short loc_140016DD8
0x140016dc5  mov     r8d, ebx
0x140016dc8  lea     rdx, [rbp+1530h+OutputString]
0x140016dcf  lea     rcx, [rbp+1530h+var_14E0]
0x140016dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016dd8  cmp     [rbp+1530h+OutputString], r12w
0x140016de0  jnz     short loc_140016DF5
0x140016de2  lea     r8, [rbp+1530h+var_14E0]; unsigned __int64
0x140016de6  mov     rdx, rbx; unsigned __int16 *
0x140016de9  lea     rcx, [rbp+1530h+OutputString]; this
0x140016df0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140016df5  lea     rcx, [rbp+1530h+OutputString]; lpOutputString
0x140016dfc  call    cs:__imp_OutputDebugStringW
0x140016e02  test    byte ptr [rbp+1530h+var_14E0+4], 4
0x140016e06  jnz     short loc_140016E11
0x140016e08  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140016e0f  jz      short loc_140016E23
0x140016e11  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140016e18  test    rax, rax
0x140016e1b  jz      short loc_140016E23
0x140016e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016e22  nop
0x140016e23  lea     rcx, [rbp+1530h+var_14E0]; this
0x140016e27  test    byte ptr [rbp+1530h+var_14E0+4], 1
0x140016e2b  jz      short loc_140016E33
0x140016e2d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140016e33  mov     rdx, r13; struct wil::FailureInfo *
0x140016e36  call    ?SetFailureInfo@details@wil@@YAXAEBUFailureInfo@2@AEAVResultException@2@@Z; wil::details::SetFailureInfo(wil::FailureInfo const &,wil::ResultException &)
0x140016e3b  mov     rdx, r13; struct ComputeService::Reporting::ComputeException *
0x140016e3e  lea     rcx, [rsp+1630h+pExceptionObject]; this
0x140016e43  call    ??0ComputeException@Reporting@ComputeService@@QEAA@AEBV012@@Z; ComputeService::Reporting::ComputeException::ComputeException(ComputeService::Reporting::ComputeException const &)
0x140016e48  lea     rdx, _TI3?AVComputeException@Reporting@ComputeService@@; pThrowInfo
0x140016e4f  lea     rcx, [rsp+1630h+pExceptionObject]; pExceptionObject
0x140016e54  call    _CxxThrowException_0
```
