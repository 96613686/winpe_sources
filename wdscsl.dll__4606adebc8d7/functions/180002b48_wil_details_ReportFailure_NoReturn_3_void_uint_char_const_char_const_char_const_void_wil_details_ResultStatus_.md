# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002b48`
- end: `0x180002dba`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800028d4`

## callees

- `0x180002b48`
- `0x1800062d4`
- `0x180006bdc`
- `0x180008a20`
- `0x18000b62c`
- `0x18000d6d2`
- `0x18000d7c0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180002cf2`
- `KERNEL32!IsDebuggerPresent` at `0x180002cf2`
- `KERNEL32!GetCurrentThreadId` at `0x180002be9`
- `KERNEL32!GetCurrentThreadId` at `0x180002be9`
- `KERNEL32!OutputDebugStringW` at `0x180002d82`
- `KERNEL32!OutputDebugStringW` at `0x180002d82`

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
0x180002b48  mov     [rsp-8+arg_18], rbx
0x180002b4d  push    rbp
0x180002b4e  push    rsi
0x180002b4f  push    rdi
0x180002b50  push    r12
0x180002b52  push    r13
0x180002b54  push    r14
0x180002b56  push    r15
0x180002b58  lea     rbp, [rsp-13C0h]
0x180002b60  mov     eax, 14C0h
0x180002b65  call    _alloca_probe
0x180002b6a  sub     rsp, rax
0x180002b6d  mov     rsi, [rbp+13F0h+arg_28]
0x180002b74  mov     r15, r8
0x180002b77  mov     r14d, edx
0x180002b7a  mov     r12, rcx
0x180002b7d  xor     edx, edx; Val
0x180002b7f  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002b84  mov     r8d, 98h; Size
0x180002b8a  call    memset_0
0x180002b8f  mov     rbx, [rbp+13F0h+arg_30]
0x180002b96  xor     r13d, r13d
0x180002b99  mov     [rbp+13F0h+OutputString], r13w
0x180002ba1  mov     [rbp+13F0h+var_1430], r13b
0x180002ba5  mov     ecx, [rbx]; this
0x180002ba7  mov     eax, [rbx+4]
0x180002baa  mov     [rsp+14F0h+var_14C8], ecx
0x180002bae  mov     [rsp+14F0h+var_14C4], eax
0x180002bb2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002bb7  cmp     dword ptr [rbx+8], 1
0x180002bbb  mov     edi, eax
0x180002bbd  lea     eax, [r13+8]
0x180002bc1  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002bc9  mov     ecx, r13d
0x180002bcc  cmovz   ecx, eax
0x180002bcf  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002bd3  lea     ecx, [rax-7]
0x180002bd6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180002bde  inc     ecx
0x180002be0  mov     [rsp+14F0h+var_14B8], r13
0x180002be5  mov     [rsp+14F0h+var_14C0], ecx
0x180002be9  call    cs:__imp_GetCurrentThreadId
0x180002bf0  nop     dword ptr [rax+rax+00h]
0x180002bf5  xorps   xmm0, xmm0
0x180002bf8  mov     [rsp+14F0h+var_1498], r15
0x180002bfd  mov     [rsp+14F0h+var_14B0], eax
0x180002c01  xorps   xmm1, xmm1
0x180002c04  xor     eax, eax
0x180002c06  mov     [rsp+14F0h+var_1490], r14d
0x180002c0b  mov     [rbp+13F0h+var_1458], rax
0x180002c0f  mov     [rbp+13F0h+var_1470], rax
0x180002c13  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002c1a  mov     [rsp+14F0h+var_148C], edi
0x180002c1e  mov     [rsp+14F0h+var_14A8], r13
0x180002c23  mov     [rsp+14F0h+var_14A0], r13
0x180002c28  mov     [rbp+13F0h+var_1448], rsi
0x180002c2c  mov     [rbp+13F0h+var_1440], r12
0x180002c30  mov     [rsp+14F0h+var_1488], r13
0x180002c35  movups  [rbp+13F0h+var_1468], xmm0
0x180002c39  movups  [rsp+14F0h+var_1480], xmm1
0x180002c3e  test    rax, rax
0x180002c41  jz      short loc_180002C4E
0x180002c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c48  mov     [rbp+13F0h+var_1450], rax
0x180002c4c  jmp     short loc_180002C52
0x180002c4e  mov     [rbp+13F0h+var_1450], r13
0x180002c52  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002c59  test    rax, rax
0x180002c5c  jz      short loc_180002C68
0x180002c5e  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c68  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002c6f  test    rax, rax
0x180002c72  jz      short loc_180002C88
0x180002c74  mov     r8d, 400h
0x180002c7a  lea     rdx, [rbp+13F0h+var_1430]
0x180002c7e  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c88  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c8f  test    rax, rax
0x180002c92  jz      short loc_180002C9E
0x180002c94  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c9e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ca5  test    rax, rax
0x180002ca8  jz      short loc_180002CBB
0x180002caa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002caf  jnz     short loc_180002CBB
0x180002cb1  lea     rcx, [rsp+14F0h+var_14D0]
0x180002cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cbb  cmp     [rsp+14F0h+var_14C8], r13d
0x180002cc0  jl      short loc_180002CD4
0x180002cc2  mov     ecx, 8000FFFFh; this
0x180002cc7  mov     [rsp+14F0h+var_14C8], ecx
0x180002ccb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002cd0  mov     [rsp+14F0h+var_14C4], eax
0x180002cd4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002cdb  jnz     short loc_180002D02
0x180002cdd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ce4  test    rax, rax
0x180002ce7  jz      short loc_180002CF2
0x180002ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cee  test    al, al
0x180002cf0  jmp     short loc_180002D00
0x180002cf2  call    cs:__imp_IsDebuggerPresent
0x180002cf9  nop     dword ptr [rax+rax+00h]
0x180002cfe  test    eax, eax
0x180002d00  jz      short loc_180002D09
0x180002d02  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002d07  jz      short loc_180002D2F
0x180002d09  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d10  test    rax, rax
0x180002d13  jz      short loc_180002D8E
0x180002d15  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002d1c  jnz     short loc_180002D8E
0x180002d1e  xor     r8d, r8d
0x180002d21  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d26  xor     edx, edx
0x180002d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d2d  jmp     short loc_180002D8E
0x180002d2f  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d36  mov     ebx, 800h
0x180002d3b  test    rax, rax
0x180002d3e  jz      short loc_180002D5D
0x180002d40  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002d47  jnz     short loc_180002D5D
0x180002d49  mov     r8d, ebx
0x180002d4c  lea     rdx, [rbp+13F0h+OutputString]
0x180002d53  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d5d  cmp     [rbp+13F0h+OutputString], r13w
0x180002d65  jnz     short loc_180002D7B
0x180002d67  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002d6c  mov     rdx, rbx; unsigned __int16 *
0x180002d6f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002d76  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002d7b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002d82  call    cs:__imp_OutputDebugStringW
0x180002d89  nop     dword ptr [rax+rax+00h]
0x180002d8e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002d93  jnz     short loc_180002D9E
0x180002d95  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002d9c  jz      short loc_180002DAF
0x180002d9e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002da5  test    rax, rax
0x180002da8  jz      short loc_180002DAF
0x180002daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002daf  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002db4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
