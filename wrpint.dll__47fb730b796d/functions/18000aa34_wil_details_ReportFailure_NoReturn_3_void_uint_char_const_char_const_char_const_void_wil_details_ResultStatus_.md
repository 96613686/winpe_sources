# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000aa34`
- end: `0x18000ac94`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000a7d0`

## callees

- `0x18000aa34`
- `0x18000caf4`
- `0x18000d2ac`
- `0x18000dee0`
- `0x18000fd40`
- `0x18001b77a`
- `0x18001b840`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aad5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aad5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ac62`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ac62`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000abd8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000abd8`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v20, v18);
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
0x18000aa34  mov     [rsp-8+arg_18], rbx
0x18000aa39  push    rbp
0x18000aa3a  push    rsi
0x18000aa3b  push    rdi
0x18000aa3c  push    r12
0x18000aa3e  push    r13
0x18000aa40  push    r14
0x18000aa42  push    r15
0x18000aa44  lea     rbp, [rsp-13C0h]
0x18000aa4c  mov     eax, 14C0h
0x18000aa51  call    _alloca_probe
0x18000aa56  sub     rsp, rax
0x18000aa59  mov     rsi, [rbp+13F0h+arg_28]
0x18000aa60  mov     r15, r8
0x18000aa63  mov     r14d, edx
0x18000aa66  mov     r12, rcx
0x18000aa69  xor     edx, edx; Val
0x18000aa6b  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000aa70  mov     r8d, 98h; Size
0x18000aa76  call    memset_0
0x18000aa7b  mov     rbx, [rbp+13F0h+arg_30]
0x18000aa82  xor     r13d, r13d
0x18000aa85  mov     [rbp+13F0h+OutputString], r13w
0x18000aa8d  mov     [rbp+13F0h+var_1430], r13b
0x18000aa91  mov     ecx, [rbx]; this
0x18000aa93  mov     eax, [rbx+4]
0x18000aa96  mov     [rsp+14F0h+var_14C8], ecx
0x18000aa9a  mov     [rsp+14F0h+var_14C4], eax
0x18000aa9e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000aaa3  cmp     dword ptr [rbx+8], 1
0x18000aaa7  mov     edi, eax
0x18000aaa9  lea     eax, [r13+8]
0x18000aaad  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000aab5  mov     ecx, r13d
0x18000aab8  cmovz   ecx, eax
0x18000aabb  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000aabf  lea     ecx, [rax-7]
0x18000aac2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000aaca  inc     ecx
0x18000aacc  mov     [rsp+14F0h+var_14B8], r13
0x18000aad1  mov     [rsp+14F0h+var_14C0], ecx
0x18000aad5  call    cs:__imp_GetCurrentThreadId
0x18000aadb  xorps   xmm0, xmm0
0x18000aade  mov     [rsp+14F0h+var_1498], r15
0x18000aae3  mov     [rsp+14F0h+var_14B0], eax
0x18000aae7  xorps   xmm1, xmm1
0x18000aaea  xor     eax, eax
0x18000aaec  mov     [rsp+14F0h+var_1490], r14d
0x18000aaf1  mov     [rbp+13F0h+var_1458], rax
0x18000aaf5  mov     [rbp+13F0h+var_1470], rax
0x18000aaf9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ab00  mov     [rsp+14F0h+var_148C], edi
0x18000ab04  mov     [rsp+14F0h+var_14A8], r13
0x18000ab09  mov     [rsp+14F0h+var_14A0], r13
0x18000ab0e  mov     [rbp+13F0h+var_1448], rsi
0x18000ab12  mov     [rbp+13F0h+var_1440], r12
0x18000ab16  mov     [rsp+14F0h+var_1488], r13
0x18000ab1b  movups  [rbp+13F0h+var_1468], xmm0
0x18000ab1f  movups  [rsp+14F0h+var_1480], xmm1
0x18000ab24  test    rax, rax
0x18000ab27  jz      short loc_18000AB34
0x18000ab29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab2e  mov     [rbp+13F0h+var_1450], rax
0x18000ab32  jmp     short loc_18000AB38
0x18000ab34  mov     [rbp+13F0h+var_1450], r13
0x18000ab38  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ab3f  test    rax, rax
0x18000ab42  jz      short loc_18000AB4E
0x18000ab44  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ab49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab4e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ab55  test    rax, rax
0x18000ab58  jz      short loc_18000AB6E
0x18000ab5a  mov     r8d, 400h
0x18000ab60  lea     rdx, [rbp+13F0h+var_1430]
0x18000ab64  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ab69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab6e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ab75  test    rax, rax
0x18000ab78  jz      short loc_18000AB84
0x18000ab7a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ab7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab84  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ab8b  test    rax, rax
0x18000ab8e  jz      short loc_18000ABA1
0x18000ab90  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000ab95  jnz     short loc_18000ABA1
0x18000ab97  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ab9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aba1  cmp     [rsp+14F0h+var_14C8], r13d
0x18000aba6  jl      short loc_18000ABBA
0x18000aba8  mov     ecx, 8000FFFFh; this
0x18000abad  mov     [rsp+14F0h+var_14C8], ecx
0x18000abb1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000abb6  mov     [rsp+14F0h+var_14C4], eax
0x18000abba  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000abc1  jnz     short loc_18000ABE2
0x18000abc3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000abca  test    rax, rax
0x18000abcd  jz      short loc_18000ABD8
0x18000abcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abd4  test    al, al
0x18000abd6  jmp     short loc_18000ABE0
0x18000abd8  call    cs:__imp_IsDebuggerPresent
0x18000abde  test    eax, eax
0x18000abe0  jz      short loc_18000ABE9
0x18000abe2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000abe7  jz      short loc_18000AC0F
0x18000abe9  mov     rax, cs:g_pfnResultLoggingCallback
0x18000abf0  test    rax, rax
0x18000abf3  jz      short loc_18000AC68
0x18000abf5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000abfc  jnz     short loc_18000AC68
0x18000abfe  xor     r8d, r8d
0x18000ac01  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ac06  xor     edx, edx
0x18000ac08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac0d  jmp     short loc_18000AC68
0x18000ac0f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ac16  mov     ebx, 800h
0x18000ac1b  test    rax, rax
0x18000ac1e  jz      short loc_18000AC3D
0x18000ac20  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000ac27  jnz     short loc_18000AC3D
0x18000ac29  mov     r8d, ebx
0x18000ac2c  lea     rdx, [rbp+13F0h+OutputString]
0x18000ac33  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ac38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac3d  cmp     [rbp+13F0h+OutputString], r13w
0x18000ac45  jnz     short loc_18000AC5B
0x18000ac47  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000ac4c  mov     rdx, rbx; wchar_t *
0x18000ac4f  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000ac56  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000ac5b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000ac62  call    cs:__imp_OutputDebugStringW
0x18000ac68  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000ac6d  jnz     short loc_18000AC78
0x18000ac6f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000ac76  jz      short loc_18000AC89
0x18000ac78  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ac7f  test    rax, rax
0x18000ac82  jz      short loc_18000AC89
0x18000ac84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac89  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ac8e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
