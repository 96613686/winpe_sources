# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180017be4`
- end: `0x180017e56`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800179b0`

## callees

- `0x180017be4`
- `0x180019614`
- `0x180019ef0`
- `0x18001aeb0`
- `0x18001c53c`
- `0x18001d1da`
- `0x18001d2a0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017c85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017c85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180017e1e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180017e1e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180017d8e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180017d8e`

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
0x180017be4  mov     [rsp-8+arg_18], rbx
0x180017be9  push    rbp
0x180017bea  push    rsi
0x180017beb  push    rdi
0x180017bec  push    r12
0x180017bee  push    r13
0x180017bf0  push    r14
0x180017bf2  push    r15
0x180017bf4  lea     rbp, [rsp-13C0h]
0x180017bfc  mov     eax, 14C0h
0x180017c01  call    _alloca_probe
0x180017c06  sub     rsp, rax
0x180017c09  mov     rsi, [rbp+13F0h+arg_28]
0x180017c10  mov     r15, r8
0x180017c13  mov     r14d, edx
0x180017c16  mov     r12, rcx
0x180017c19  xor     edx, edx; Val
0x180017c1b  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180017c20  mov     r8d, 98h; Size
0x180017c26  call    memset_0
0x180017c2b  mov     rbx, [rbp+13F0h+arg_30]
0x180017c32  xor     r13d, r13d
0x180017c35  mov     [rbp+13F0h+OutputString], r13w
0x180017c3d  mov     [rbp+13F0h+var_1430], r13b
0x180017c41  mov     ecx, [rbx]; this
0x180017c43  mov     eax, [rbx+4]
0x180017c46  mov     [rsp+14F0h+var_14C8], ecx
0x180017c4a  mov     [rsp+14F0h+var_14C4], eax
0x180017c4e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180017c53  cmp     dword ptr [rbx+8], 1
0x180017c57  mov     edi, eax
0x180017c59  lea     eax, [r13+8]
0x180017c5d  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180017c65  mov     ecx, r13d
0x180017c68  cmovz   ecx, eax
0x180017c6b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180017c6f  lea     ecx, [rax-7]
0x180017c72  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180017c7a  inc     ecx
0x180017c7c  mov     [rsp+14F0h+var_14B8], r13
0x180017c81  mov     [rsp+14F0h+var_14C0], ecx
0x180017c85  call    cs:__imp_GetCurrentThreadId
0x180017c8c  nop     dword ptr [rax+rax+00h]
0x180017c91  xorps   xmm0, xmm0
0x180017c94  mov     [rsp+14F0h+var_1498], r15
0x180017c99  mov     [rsp+14F0h+var_14B0], eax
0x180017c9d  xorps   xmm1, xmm1
0x180017ca0  xor     eax, eax
0x180017ca2  mov     [rsp+14F0h+var_1490], r14d
0x180017ca7  mov     [rbp+13F0h+var_1458], rax
0x180017cab  mov     [rbp+13F0h+var_1470], rax
0x180017caf  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180017cb6  mov     [rsp+14F0h+var_148C], edi
0x180017cba  mov     [rsp+14F0h+var_14A8], r13
0x180017cbf  mov     [rsp+14F0h+var_14A0], r13
0x180017cc4  mov     [rbp+13F0h+var_1448], rsi
0x180017cc8  mov     [rbp+13F0h+var_1440], r12
0x180017ccc  mov     [rsp+14F0h+var_1488], r13
0x180017cd1  movups  [rbp+13F0h+var_1468], xmm0
0x180017cd5  movups  [rsp+14F0h+var_1480], xmm1
0x180017cda  test    rax, rax
0x180017cdd  jz      short loc_180017CEA
0x180017cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ce4  mov     [rbp+13F0h+var_1450], rax
0x180017ce8  jmp     short loc_180017CEE
0x180017cea  mov     [rbp+13F0h+var_1450], r13
0x180017cee  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180017cf5  test    rax, rax
0x180017cf8  jz      short loc_180017D04
0x180017cfa  lea     rcx, [rsp+14F0h+var_14D0]
0x180017cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d04  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180017d0b  test    rax, rax
0x180017d0e  jz      short loc_180017D24
0x180017d10  mov     r8d, 400h
0x180017d16  lea     rdx, [rbp+13F0h+var_1430]
0x180017d1a  lea     rcx, [rsp+14F0h+var_14D0]
0x180017d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d24  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017d2b  test    rax, rax
0x180017d2e  jz      short loc_180017D3A
0x180017d30  lea     rcx, [rsp+14F0h+var_14D0]
0x180017d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d3a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017d41  test    rax, rax
0x180017d44  jz      short loc_180017D57
0x180017d46  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180017d4b  jnz     short loc_180017D57
0x180017d4d  lea     rcx, [rsp+14F0h+var_14D0]
0x180017d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d57  cmp     [rsp+14F0h+var_14C8], r13d
0x180017d5c  jl      short loc_180017D70
0x180017d5e  mov     ecx, 8000FFFFh; this
0x180017d63  mov     [rsp+14F0h+var_14C8], ecx
0x180017d67  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180017d6c  mov     [rsp+14F0h+var_14C4], eax
0x180017d70  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180017d77  jnz     short loc_180017D9E
0x180017d79  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180017d80  test    rax, rax
0x180017d83  jz      short loc_180017D8E
0x180017d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d8a  test    al, al
0x180017d8c  jmp     short loc_180017D9C
0x180017d8e  call    cs:__imp_IsDebuggerPresent
0x180017d95  nop     dword ptr [rax+rax+00h]
0x180017d9a  test    eax, eax
0x180017d9c  jz      short loc_180017DA5
0x180017d9e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180017da3  jz      short loc_180017DCB
0x180017da5  mov     rax, cs:g_pfnResultLoggingCallback
0x180017dac  test    rax, rax
0x180017daf  jz      short loc_180017E2A
0x180017db1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180017db8  jnz     short loc_180017E2A
0x180017dba  xor     r8d, r8d
0x180017dbd  lea     rcx, [rsp+14F0h+var_14D0]
0x180017dc2  xor     edx, edx
0x180017dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dc9  jmp     short loc_180017E2A
0x180017dcb  mov     rax, cs:g_pfnResultLoggingCallback
0x180017dd2  mov     ebx, 800h
0x180017dd7  test    rax, rax
0x180017dda  jz      short loc_180017DF9
0x180017ddc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180017de3  jnz     short loc_180017DF9
0x180017de5  mov     r8d, ebx
0x180017de8  lea     rdx, [rbp+13F0h+OutputString]
0x180017def  lea     rcx, [rsp+14F0h+var_14D0]
0x180017df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017df9  cmp     [rbp+13F0h+OutputString], r13w
0x180017e01  jnz     short loc_180017E17
0x180017e03  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180017e08  mov     rdx, rbx; unsigned __int16 *
0x180017e0b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180017e12  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180017e17  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180017e1e  call    cs:__imp_OutputDebugStringW
0x180017e25  nop     dword ptr [rax+rax+00h]
0x180017e2a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180017e2f  jnz     short loc_180017E3A
0x180017e31  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180017e38  jz      short loc_180017E4B
0x180017e3a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180017e41  test    rax, rax
0x180017e44  jz      short loc_180017E4B
0x180017e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e4b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180017e50  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
