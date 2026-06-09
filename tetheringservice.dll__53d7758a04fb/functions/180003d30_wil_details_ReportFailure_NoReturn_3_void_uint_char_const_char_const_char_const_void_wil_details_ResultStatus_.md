# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003d30`
- end: `0x180003fa9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003aac`

## callees

- `0x180003088`
- `0x180003d30`
- `0x1800064a4`
- `0x180006c4c`
- `0x1800078d0`
- `0x18000a040`
- `0x180031580`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003de9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003de9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003eec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003eec`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f76`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180003d30  mov     [rsp-8+arg_18], rbx
0x180003d35  push    rbp
0x180003d36  push    rsi
0x180003d37  push    rdi
0x180003d38  push    r12
0x180003d3a  push    r13
0x180003d3c  push    r14
0x180003d3e  push    r15
0x180003d40  lea     rbp, [rsp-13C0h]
0x180003d48  mov     eax, 14C0h
0x180003d4d  call    _alloca_probe
0x180003d52  sub     rsp, rax
0x180003d55  mov     r14, r8
0x180003d58  mov     esi, edx
0x180003d5a  mov     rdi, rcx
0x180003d5d  mov     r15, [rbp+13F0h+arg_28]
0x180003d64  xor     edx, edx; Val
0x180003d66  mov     r8d, 98h; Size
0x180003d6c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003d71  call    memset_0
0x180003d76  nop
0x180003d77  xor     r13d, r13d
0x180003d7a  mov     [rbp+13F0h+OutputString], r13w
0x180003d82  mov     [rbp+13F0h+var_1430], r13b
0x180003d86  mov     rbx, [rbp+13F0h+arg_30]
0x180003d8d  mov     ecx, [rbx]; this
0x180003d8f  mov     [rsp+14F0h+var_14C8], ecx
0x180003d93  mov     eax, [rbx+4]
0x180003d96  mov     [rsp+14F0h+var_14C4], eax
0x180003d9a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003d9f  mov     r12d, eax
0x180003da2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003daa  mov     ecx, r13d
0x180003dad  lea     eax, [r13+8]
0x180003db1  cmp     dword ptr [rbx+8], 1
0x180003db5  cmovz   ecx, eax
0x180003db8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003dbc  lea     ecx, [rax-7]
0x180003dbf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003dc7  inc     ecx
0x180003dc9  mov     [rsp+14F0h+var_14C0], ecx
0x180003dcd  mov     rcx, [rbp+13F0h+arg_38]
0x180003dd4  test    rcx, rcx
0x180003dd7  jz      short loc_180003DE4
0x180003dd9  cmp     [rcx], r13w
0x180003ddd  mov     [rsp+14F0h+var_14B8], rcx
0x180003de2  jnz     short loc_180003DE9
0x180003de4  mov     [rsp+14F0h+var_14B8], r13
0x180003de9  call    cs:__imp_GetCurrentThreadId
0x180003def  mov     [rsp+14F0h+var_14B0], eax
0x180003df3  mov     [rsp+14F0h+var_1498], r14
0x180003df8  mov     [rsp+14F0h+var_1490], esi
0x180003dfc  mov     [rsp+14F0h+var_148C], r12d
0x180003e01  mov     [rsp+14F0h+var_14A8], r13
0x180003e06  mov     [rsp+14F0h+var_14A0], r13
0x180003e0b  mov     [rbp+13F0h+var_1448], r15
0x180003e0f  mov     [rbp+13F0h+var_1440], rdi
0x180003e13  mov     [rsp+14F0h+var_1488], r13
0x180003e18  xorps   xmm0, xmm0
0x180003e1b  xor     eax, eax
0x180003e1d  movups  [rbp+13F0h+var_1468], xmm0
0x180003e21  mov     [rbp+13F0h+var_1458], rax
0x180003e25  xorps   xmm1, xmm1
0x180003e28  movups  [rsp+14F0h+var_1480], xmm1
0x180003e2d  mov     [rbp+13F0h+var_1470], rax
0x180003e31  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003e38  test    rax, rax
0x180003e3b  jz      short loc_180003E48
0x180003e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e42  mov     [rbp+13F0h+var_1450], rax
0x180003e46  jmp     short loc_180003E4C
0x180003e48  mov     [rbp+13F0h+var_1450], r13
0x180003e4c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003e53  test    rax, rax
0x180003e56  jz      short loc_180003E62
0x180003e58  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e62  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003e69  test    rax, rax
0x180003e6c  jz      short loc_180003E82
0x180003e6e  mov     r8d, 400h
0x180003e74  lea     rdx, [rbp+13F0h+var_1430]
0x180003e78  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e82  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e89  test    rax, rax
0x180003e8c  jz      short loc_180003E98
0x180003e8e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e98  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e9f  test    rax, rax
0x180003ea2  jz      short loc_180003EB5
0x180003ea4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003ea9  jnz     short loc_180003EB5
0x180003eab  lea     rcx, [rsp+14F0h+var_14D0]
0x180003eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb5  cmp     [rsp+14F0h+var_14C8], r13d
0x180003eba  jl      short loc_180003ECE
0x180003ebc  mov     ecx, 8000FFFFh; this
0x180003ec1  mov     [rsp+14F0h+var_14C8], ecx
0x180003ec5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003eca  mov     [rsp+14F0h+var_14C4], eax
0x180003ece  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003ed5  jnz     short loc_180003EF6
0x180003ed7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003ede  test    rax, rax
0x180003ee1  jz      short loc_180003EEC
0x180003ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ee8  test    al, al
0x180003eea  jmp     short loc_180003EF4
0x180003eec  call    cs:__imp_IsDebuggerPresent
0x180003ef2  test    eax, eax
0x180003ef4  jz      short loc_180003EFD
0x180003ef6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003efb  jz      short loc_180003F23
0x180003efd  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f04  test    rax, rax
0x180003f07  jz      short loc_180003F7C
0x180003f09  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003f10  jnz     short loc_180003F7C
0x180003f12  xor     r8d, r8d
0x180003f15  xor     edx, edx
0x180003f17  lea     rcx, [rsp+14F0h+var_14D0]
0x180003f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f21  jmp     short loc_180003F7C
0x180003f23  mov     ebx, 800h
0x180003f28  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f2f  test    rax, rax
0x180003f32  jz      short loc_180003F51
0x180003f34  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003f3b  jnz     short loc_180003F51
0x180003f3d  mov     r8d, ebx
0x180003f40  lea     rdx, [rbp+13F0h+OutputString]
0x180003f47  lea     rcx, [rsp+14F0h+var_14D0]
0x180003f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f51  cmp     [rbp+13F0h+OutputString], r13w
0x180003f59  jnz     short loc_180003F6F
0x180003f5b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003f60  mov     rdx, rbx; unsigned __int16 *
0x180003f63  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003f6a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003f6f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003f76  call    cs:__imp_OutputDebugStringW
0x180003f7c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003f81  jnz     short loc_180003F8C
0x180003f83  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003f8a  jz      short loc_180003F9E
0x180003f8c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003f93  test    rax, rax
0x180003f96  jz      short loc_180003F9E
0x180003f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f9d  nop
0x180003f9e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003fa3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
