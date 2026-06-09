# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000cc2c`
- end: `0x18000ce8e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000c9f8`

## callees

- `0x18000cc2c`
- `0x18000e894`
- `0x18000f350`
- `0x1800102d0`
- `0x180011c10`
- `0x1800131a2`
- `0x1800132a0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ce5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ce5b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cdd1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cdd1`

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
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x18000cc2c  mov     [rsp-8+arg_18], rbx
0x18000cc31  push    rbp
0x18000cc32  push    rsi
0x18000cc33  push    rdi
0x18000cc34  push    r12
0x18000cc36  push    r13
0x18000cc38  push    r14
0x18000cc3a  push    r15
0x18000cc3c  lea     rbp, [rsp-13C0h]
0x18000cc44  mov     eax, 14C0h
0x18000cc49  call    _alloca_probe
0x18000cc4e  sub     rsp, rax
0x18000cc51  mov     r15, r8
0x18000cc54  mov     r14d, edx
0x18000cc57  mov     r12, rcx
0x18000cc5a  mov     rsi, [rbp+13F0h+arg_28]
0x18000cc61  xor     edx, edx; Val
0x18000cc63  mov     r8d, 98h; Size
0x18000cc69  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000cc6e  call    memset_0
0x18000cc73  nop
0x18000cc74  xor     r13d, r13d
0x18000cc77  mov     [rbp+13F0h+OutputString], r13w
0x18000cc7f  mov     [rbp+13F0h+var_1430], r13b
0x18000cc83  mov     rbx, [rbp+13F0h+arg_30]
0x18000cc8a  mov     ecx, [rbx]; this
0x18000cc8c  mov     [rsp+14F0h+var_14C8], ecx
0x18000cc90  mov     eax, [rbx+4]
0x18000cc93  mov     [rsp+14F0h+var_14C4], eax
0x18000cc97  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000cc9c  mov     edi, eax
0x18000cc9e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000cca6  mov     ecx, r13d
0x18000cca9  lea     eax, [r13+8]
0x18000ccad  cmp     dword ptr [rbx+8], 1
0x18000ccb1  cmovz   ecx, eax
0x18000ccb4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000ccb8  lea     ecx, [rax-7]
0x18000ccbb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ccc3  inc     ecx
0x18000ccc5  mov     [rsp+14F0h+var_14C0], ecx
0x18000ccc9  mov     [rsp+14F0h+var_14B8], r13
0x18000ccce  call    cs:__imp_GetCurrentThreadId
0x18000ccd4  mov     [rsp+14F0h+var_14B0], eax
0x18000ccd8  mov     [rsp+14F0h+var_1498], r15
0x18000ccdd  mov     [rsp+14F0h+var_1490], r14d
0x18000cce2  mov     [rsp+14F0h+var_148C], edi
0x18000cce6  mov     [rsp+14F0h+var_14A8], r13
0x18000cceb  mov     [rsp+14F0h+var_14A0], r13
0x18000ccf0  mov     [rbp+13F0h+var_1448], rsi
0x18000ccf4  mov     [rbp+13F0h+var_1440], r12
0x18000ccf8  mov     [rsp+14F0h+var_1488], r13
0x18000ccfd  xorps   xmm0, xmm0
0x18000cd00  xor     eax, eax
0x18000cd02  movups  [rbp+13F0h+var_1468], xmm0
0x18000cd06  mov     [rbp+13F0h+var_1458], rax
0x18000cd0a  xorps   xmm1, xmm1
0x18000cd0d  movups  [rsp+14F0h+var_1480], xmm1
0x18000cd12  mov     [rbp+13F0h+var_1470], rax
0x18000cd16  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cd1d  test    rax, rax
0x18000cd20  jz      short loc_18000CD2D
0x18000cd22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd27  mov     [rbp+13F0h+var_1450], rax
0x18000cd2b  jmp     short loc_18000CD31
0x18000cd2d  mov     [rbp+13F0h+var_1450], r13
0x18000cd31  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000cd38  test    rax, rax
0x18000cd3b  jz      short loc_18000CD47
0x18000cd3d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cd42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd47  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000cd4e  test    rax, rax
0x18000cd51  jz      short loc_18000CD67
0x18000cd53  mov     r8d, 400h
0x18000cd59  lea     rdx, [rbp+13F0h+var_1430]
0x18000cd5d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd67  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cd6e  test    rax, rax
0x18000cd71  jz      short loc_18000CD7D
0x18000cd73  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd7d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cd84  test    rax, rax
0x18000cd87  jz      short loc_18000CD9A
0x18000cd89  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000cd8e  jnz     short loc_18000CD9A
0x18000cd90  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd9a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000cd9f  jl      short loc_18000CDB3
0x18000cda1  mov     ecx, 8000FFFFh; this
0x18000cda6  mov     [rsp+14F0h+var_14C8], ecx
0x18000cdaa  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cdaf  mov     [rsp+14F0h+var_14C4], eax
0x18000cdb3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000cdba  jnz     short loc_18000CDDB
0x18000cdbc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cdc3  test    rax, rax
0x18000cdc6  jz      short loc_18000CDD1
0x18000cdc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdcd  test    al, al
0x18000cdcf  jmp     short loc_18000CDD9
0x18000cdd1  call    cs:__imp_IsDebuggerPresent
0x18000cdd7  test    eax, eax
0x18000cdd9  jz      short loc_18000CDE2
0x18000cddb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000cde0  jz      short loc_18000CE08
0x18000cde2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cde9  test    rax, rax
0x18000cdec  jz      short loc_18000CE61
0x18000cdee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000cdf5  jnz     short loc_18000CE61
0x18000cdf7  xor     r8d, r8d
0x18000cdfa  xor     edx, edx
0x18000cdfc  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ce01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce06  jmp     short loc_18000CE61
0x18000ce08  mov     ebx, 800h
0x18000ce0d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ce14  test    rax, rax
0x18000ce17  jz      short loc_18000CE36
0x18000ce19  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000ce20  jnz     short loc_18000CE36
0x18000ce22  mov     r8d, ebx
0x18000ce25  lea     rdx, [rbp+13F0h+OutputString]
0x18000ce2c  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ce31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce36  cmp     [rbp+13F0h+OutputString], r13w
0x18000ce3e  jnz     short loc_18000CE54
0x18000ce40  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000ce45  mov     rdx, rbx; unsigned __int16 *
0x18000ce48  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000ce4f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ce54  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000ce5b  call    cs:__imp_OutputDebugStringW
0x18000ce61  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000ce66  jnz     short loc_18000CE71
0x18000ce68  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000ce6f  jz      short loc_18000CE83
0x18000ce71  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ce78  test    rax, rax
0x18000ce7b  jz      short loc_18000CE83
0x18000ce7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce82  nop
0x18000ce83  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ce88  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
