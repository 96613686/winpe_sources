# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140006aec`
- end: `0x140006db1`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400068dc`

## callees

- `0x140002c38`
- `0x140004354`
- `0x1400051fc`
- `0x140005e4c`
- `0x1400061a0`
- `0x14000627c`
- `0x140006aec`
- `0x14000ac20`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006bad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006bad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006d45`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006d45`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006ca9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006ca9`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x140006aec  mov     [rsp-8+arg_18], rbx
0x140006af1  push    rbp
0x140006af2  push    rsi
0x140006af3  push    rdi
0x140006af4  push    r12
0x140006af6  push    r13
0x140006af8  push    r14
0x140006afa  push    r15
0x140006afc  lea     rbp, [rsp-13C0h]
0x140006b04  mov     eax, 14C0h
0x140006b09  call    _alloca_probe
0x140006b0e  sub     rsp, rax
0x140006b11  mov     r14, r8
0x140006b14  mov     esi, edx
0x140006b16  mov     rbx, rcx
0x140006b19  mov     r15, [rbp+13F0h+arg_28]
0x140006b20  xor     r13d, r13d
0x140006b23  cmp     cs:g_pfnThrowPlatformException, r13
0x140006b2a  setnz   dil
0x140006b2e  xor     edx, edx; Val
0x140006b30  mov     r8d, 98h; Size
0x140006b36  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140006b3b  call    memset_0
0x140006b40  nop
0x140006b41  mov     [rbp+13F0h+OutputString], r13w
0x140006b49  mov     [rbp+13F0h+var_1430], r13b
0x140006b4d  mov     rdx, [rbp+13F0h+arg_30]; int
0x140006b54  mov     ecx, [rdx]; this
0x140006b56  mov     [rsp+14F0h+var_14C8], ecx
0x140006b5a  mov     eax, [rdx+4]
0x140006b5d  mov     [rsp+14F0h+var_14C4], eax
0x140006b61  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140006b66  mov     r12d, eax
0x140006b69  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x140006b6e  mov     ecx, r13d
0x140006b71  lea     eax, [r13+8]
0x140006b75  cmp     dword ptr [rdx+8], 1
0x140006b79  cmovz   ecx, eax
0x140006b7c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140006b80  lea     ecx, [rax-7]
0x140006b83  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006b8b  inc     ecx
0x140006b8d  mov     [rsp+14F0h+var_14C0], ecx
0x140006b91  mov     rcx, [rbp+13F0h+arg_38]
0x140006b98  test    rcx, rcx
0x140006b9b  jz      short loc_140006BA8
0x140006b9d  cmp     [rcx], r13w
0x140006ba1  mov     [rsp+14F0h+var_14B8], rcx
0x140006ba6  jnz     short loc_140006BAD
0x140006ba8  mov     [rsp+14F0h+var_14B8], r13
0x140006bad  call    cs:__imp_GetCurrentThreadId
0x140006bb3  mov     [rsp+14F0h+var_14B0], eax
0x140006bb7  mov     [rsp+14F0h+var_1498], r14
0x140006bbc  mov     [rsp+14F0h+var_1490], esi
0x140006bc0  mov     [rsp+14F0h+var_148C], r12d
0x140006bc5  mov     [rsp+14F0h+var_14A8], r13
0x140006bca  mov     [rsp+14F0h+var_14A0], r13
0x140006bcf  mov     [rbp+13F0h+var_1448], r15
0x140006bd3  mov     [rbp+13F0h+var_1440], rbx
0x140006bd7  mov     [rsp+14F0h+var_1488], r13
0x140006bdc  xorps   xmm0, xmm0
0x140006bdf  xor     eax, eax
0x140006be1  movups  [rbp+13F0h+var_1468], xmm0
0x140006be5  mov     [rbp+13F0h+var_1458], rax
0x140006be9  xorps   xmm1, xmm1
0x140006bec  movups  [rsp+14F0h+var_1480], xmm1
0x140006bf1  mov     [rbp+13F0h+var_1470], rax
0x140006bf5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006bfc  test    rax, rax
0x140006bff  jz      short loc_140006C0C
0x140006c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c06  mov     [rbp+13F0h+var_1450], rax
0x140006c0a  jmp     short loc_140006C10
0x140006c0c  mov     [rbp+13F0h+var_1450], r13
0x140006c10  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006c17  test    rax, rax
0x140006c1a  jz      short loc_140006C26
0x140006c1c  lea     rcx, [rsp+14F0h+var_14D0]
0x140006c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c26  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006c2d  test    rax, rax
0x140006c30  jz      short loc_140006C46
0x140006c32  mov     r8d, 400h
0x140006c38  lea     rdx, [rbp+13F0h+var_1430]
0x140006c3c  lea     rcx, [rsp+14F0h+var_14D0]
0x140006c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c46  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006c4d  test    rax, rax
0x140006c50  jz      short loc_140006C5C
0x140006c52  lea     rcx, [rsp+14F0h+var_14D0]
0x140006c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c5c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006c63  test    rax, rax
0x140006c66  jz      short loc_140006C7E
0x140006c68  test    dil, dil
0x140006c6b  jnz     short loc_140006C7E
0x140006c6d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006c72  jnz     short loc_140006C7E
0x140006c74  lea     rcx, [rsp+14F0h+var_14D0]
0x140006c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c7e  cmp     [rsp+14F0h+var_14C8], r13d
0x140006c83  jl      short loc_140006C8B
0x140006c85  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140006c8b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140006c92  jnz     short loc_140006CB3
0x140006c94  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006c9b  test    rax, rax
0x140006c9e  jz      short loc_140006CA9
0x140006ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ca5  test    al, al
0x140006ca7  jmp     short loc_140006CB1
0x140006ca9  call    cs:__imp_IsDebuggerPresent
0x140006caf  test    eax, eax
0x140006cb1  jz      short loc_140006CBC
0x140006cb3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006cb8  mov     bl, 1
0x140006cba  jz      short loc_140006CBF
0x140006cbc  mov     bl, r13b
0x140006cbf  test    dil, dil
0x140006cc2  jnz     short loc_140006CEE
0x140006cc4  test    bl, bl
0x140006cc6  jnz     short loc_140006CEE
0x140006cc8  mov     rax, cs:g_pfnResultLoggingCallback
0x140006ccf  test    rax, rax
0x140006cd2  jz      short loc_140006D4B
0x140006cd4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006cdb  jnz     short loc_140006D4B
0x140006cdd  xor     r8d, r8d
0x140006ce0  xor     edx, edx
0x140006ce2  lea     rcx, [rsp+14F0h+var_14D0]
0x140006ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cec  jmp     short loc_140006D4B
0x140006cee  mov     esi, 800h
0x140006cf3  mov     rax, cs:g_pfnResultLoggingCallback
0x140006cfa  test    rax, rax
0x140006cfd  jz      short loc_140006D1C
0x140006cff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006d06  jnz     short loc_140006D1C
0x140006d08  mov     r8d, esi
0x140006d0b  lea     rdx, [rbp+13F0h+OutputString]
0x140006d12  lea     rcx, [rsp+14F0h+var_14D0]
0x140006d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d1c  cmp     [rbp+13F0h+OutputString], r13w
0x140006d24  jnz     short loc_140006D3A
0x140006d26  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140006d2b  mov     rdx, rsi; unsigned __int16 *
0x140006d2e  lea     rcx, [rbp+13F0h+OutputString]; this
0x140006d35  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006d3a  test    bl, bl
0x140006d3c  jz      short loc_140006D4B
0x140006d3e  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140006d45  call    cs:__imp_OutputDebugStringW
0x140006d4b  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140006d50  jnz     short loc_140006D5B
0x140006d52  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140006d59  jz      short loc_140006D6D
0x140006d5b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006d62  test    rax, rax
0x140006d65  jz      short loc_140006D6D
0x140006d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d6c  nop
0x140006d6d  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140006d72  jz      short loc_140006D7F
0x140006d74  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140006d79  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140006d7f  test    dil, dil
0x140006d82  jz      short loc_140006D9C
0x140006d84  lea     rdx, [rbp+13F0h+OutputString]
0x140006d8b  lea     rcx, [rsp+14F0h+var_14D0]
0x140006d90  mov     rax, cs:g_pfnThrowPlatformException
0x140006d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d9c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140006da1  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140006da6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140006dab  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
