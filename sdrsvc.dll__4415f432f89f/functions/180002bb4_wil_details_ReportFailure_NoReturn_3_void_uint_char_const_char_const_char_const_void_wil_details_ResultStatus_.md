# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002bb4`
- end: `0x180002e14`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002958`

## callees

- `0x180002bb4`
- `0x180004ce4`
- `0x18000547c`
- `0x180006390`
- `0x180008230`
- `0x18002170a`
- `0x1800217d0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002de2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002de2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002d58`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002d58`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
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

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180002bb4  mov     [rsp-8+arg_18], rbx
0x180002bb9  push    rbp
0x180002bba  push    rsi
0x180002bbb  push    rdi
0x180002bbc  push    r12
0x180002bbe  push    r13
0x180002bc0  push    r14
0x180002bc2  push    r15
0x180002bc4  lea     rbp, [rsp-13C0h]
0x180002bcc  mov     eax, 14C0h
0x180002bd1  call    _alloca_probe
0x180002bd6  sub     rsp, rax
0x180002bd9  mov     rsi, [rbp+13F0h+arg_28]
0x180002be0  mov     r15, r8
0x180002be3  mov     r14d, edx
0x180002be6  mov     r12, rcx
0x180002be9  xor     edx, edx; Val
0x180002beb  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002bf0  mov     r8d, 98h; Size
0x180002bf6  call    memset_0
0x180002bfb  mov     rbx, [rbp+13F0h+arg_30]
0x180002c02  xor     r13d, r13d
0x180002c05  mov     [rbp+13F0h+OutputString], r13w
0x180002c0d  mov     [rbp+13F0h+var_1430], r13b
0x180002c11  mov     ecx, [rbx]; this
0x180002c13  mov     eax, [rbx+4]
0x180002c16  mov     [rsp+14F0h+var_14C8], ecx
0x180002c1a  mov     [rsp+14F0h+var_14C4], eax
0x180002c1e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002c23  cmp     dword ptr [rbx+8], 1
0x180002c27  mov     edi, eax
0x180002c29  lea     eax, [r13+8]
0x180002c2d  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002c35  mov     ecx, r13d
0x180002c38  cmovz   ecx, eax
0x180002c3b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002c3f  lea     ecx, [rax-7]
0x180002c42  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002c4a  inc     ecx
0x180002c4c  mov     [rsp+14F0h+var_14B8], r13
0x180002c51  mov     [rsp+14F0h+var_14C0], ecx
0x180002c55  call    cs:__imp_GetCurrentThreadId
0x180002c5b  xorps   xmm0, xmm0
0x180002c5e  mov     [rsp+14F0h+var_1498], r15
0x180002c63  mov     [rsp+14F0h+var_14B0], eax
0x180002c67  xorps   xmm1, xmm1
0x180002c6a  xor     eax, eax
0x180002c6c  mov     [rsp+14F0h+var_1490], r14d
0x180002c71  mov     [rbp+13F0h+var_1458], rax
0x180002c75  mov     [rbp+13F0h+var_1470], rax
0x180002c79  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002c80  mov     [rsp+14F0h+var_148C], edi
0x180002c84  mov     [rsp+14F0h+var_14A8], r13
0x180002c89  mov     [rsp+14F0h+var_14A0], r13
0x180002c8e  mov     [rbp+13F0h+var_1448], rsi
0x180002c92  mov     [rbp+13F0h+var_1440], r12
0x180002c96  mov     [rsp+14F0h+var_1488], r13
0x180002c9b  movups  [rbp+13F0h+var_1468], xmm0
0x180002c9f  movups  [rsp+14F0h+var_1480], xmm1
0x180002ca4  test    rax, rax
0x180002ca7  jz      short loc_180002CB4
0x180002ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cae  mov     [rbp+13F0h+var_1450], rax
0x180002cb2  jmp     short loc_180002CB8
0x180002cb4  mov     [rbp+13F0h+var_1450], r13
0x180002cb8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002cbf  test    rax, rax
0x180002cc2  jz      short loc_180002CCE
0x180002cc4  lea     rcx, [rsp+14F0h+var_14D0]
0x180002cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cce  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002cd5  test    rax, rax
0x180002cd8  jz      short loc_180002CEE
0x180002cda  mov     r8d, 400h
0x180002ce0  lea     rdx, [rbp+13F0h+var_1430]
0x180002ce4  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cee  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002cf5  test    rax, rax
0x180002cf8  jz      short loc_180002D04
0x180002cfa  lea     rcx, [rsp+14F0h+var_14D0]
0x180002cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d04  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002d0b  test    rax, rax
0x180002d0e  jz      short loc_180002D21
0x180002d10  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002d15  jnz     short loc_180002D21
0x180002d17  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d21  cmp     [rsp+14F0h+var_14C8], r13d
0x180002d26  jl      short loc_180002D3A
0x180002d28  mov     ecx, 8000FFFFh; this
0x180002d2d  mov     [rsp+14F0h+var_14C8], ecx
0x180002d31  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002d36  mov     [rsp+14F0h+var_14C4], eax
0x180002d3a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002d41  jnz     short loc_180002D62
0x180002d43  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002d4a  test    rax, rax
0x180002d4d  jz      short loc_180002D58
0x180002d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d54  test    al, al
0x180002d56  jmp     short loc_180002D60
0x180002d58  call    cs:__imp_IsDebuggerPresent
0x180002d5e  test    eax, eax
0x180002d60  jz      short loc_180002D69
0x180002d62  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002d67  jz      short loc_180002D8F
0x180002d69  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d70  test    rax, rax
0x180002d73  jz      short loc_180002DE8
0x180002d75  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002d7c  jnz     short loc_180002DE8
0x180002d7e  xor     r8d, r8d
0x180002d81  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d86  xor     edx, edx
0x180002d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d8d  jmp     short loc_180002DE8
0x180002d8f  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d96  mov     ebx, 800h
0x180002d9b  test    rax, rax
0x180002d9e  jz      short loc_180002DBD
0x180002da0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002da7  jnz     short loc_180002DBD
0x180002da9  mov     r8d, ebx
0x180002dac  lea     rdx, [rbp+13F0h+OutputString]
0x180002db3  lea     rcx, [rsp+14F0h+var_14D0]
0x180002db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dbd  cmp     [rbp+13F0h+OutputString], r13w
0x180002dc5  jnz     short loc_180002DDB
0x180002dc7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002dcc  mov     rdx, rbx; unsigned __int16 *
0x180002dcf  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002dd6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002ddb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002de2  call    cs:__imp_OutputDebugStringW
0x180002de8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002ded  jnz     short loc_180002DF8
0x180002def  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002df6  jz      short loc_180002E09
0x180002df8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002dff  test    rax, rax
0x180002e02  jz      short loc_180002E09
0x180002e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e09  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002e0e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
