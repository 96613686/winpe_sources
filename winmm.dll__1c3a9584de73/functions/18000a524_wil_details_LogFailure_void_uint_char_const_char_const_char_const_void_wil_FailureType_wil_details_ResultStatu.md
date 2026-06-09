# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a524`
- end: `0x18000a819`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a430`
- `0x18001618c`
- `0x18001623c`

## callees

- `0x180009e14`
- `0x18000a524`
- `0x18000a820`
- `0x1800160e0`
- `0x180017474`
- `0x1800187a0`
- `0x1800187bc`
- `0x1800187d8`
- `0x180019718`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a647`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a7da`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a7da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a768`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a768`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18000a524  mov     [rsp+arg_10], rbx
0x18000a529  mov     [rsp+arg_8], edx
0x18000a52d  mov     [rsp+arg_0], rcx
0x18000a532  push    rbp
0x18000a533  push    rsi
0x18000a534  push    rdi
0x18000a535  push    r12
0x18000a537  push    r13
0x18000a539  push    r14
0x18000a53b  push    r15
0x18000a53d  sub     rsp, 40h
0x18000a541  mov     r12, r9
0x18000a544  mov     r13, r8
0x18000a547  mov     r10, rcx
0x18000a54a  xor     eax, eax
0x18000a54c  mov     rsi, [rsp+78h+lpOutputString]
0x18000a554  mov     [rsi], ax
0x18000a557  mov     rax, [rsp+78h+arg_60]
0x18000a55f  mov     byte ptr [rax], 0
0x18000a562  mov     r14, [rsp+78h+arg_38]
0x18000a56a  mov     edi, [r14]
0x18000a56d  mov     rbx, [rsp+78h+arg_78]
0x18000a575  mov     [rbx+8], edi
0x18000a578  mov     eax, [r14+4]
0x18000a57c  mov     [rbx+0Ch], eax
0x18000a57f  xor     ebp, ebp
0x18000a581  mov     r15d, [rsp+78h+arg_30]
0x18000a589  mov     ecx, r15d
0x18000a58c  test    r15d, r15d
0x18000a58f  jz      short loc_18000A5F7
0x18000a591  sub     ecx, 1
0x18000a594  jz      short loc_18000A5EE
0x18000a596  sub     ecx, 1
0x18000a599  jz      short loc_18000A5A9
0x18000a59b  cmp     ecx, 1
0x18000a59e  jnz     short loc_18000A600
0x18000a5a0  mov     ecx, edi; this
0x18000a5a2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a5a7  jmp     short loc_18000A5FE
0x18000a5a9  test    edi, edi
0x18000a5ab  js      short loc_18000A5E5
0x18000a5ad  mov     edi, 8007029Ch
0x18000a5b2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a5b6  mov     rax, [rsp+78h+arg_28]
0x18000a5be  mov     [rsp+78h+var_50], rax; __int64
0x18000a5c3  mov     rax, [rsp+78h+arg_20]
0x18000a5cb  mov     [rsp+78h+var_58], rax; __int64
0x18000a5d0  mov     rcx, r10; int
0x18000a5d3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a5d8  mov     [rbx+8], edi
0x18000a5db  mov     ecx, edi; this
0x18000a5dd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a5e2  mov     [rbx+0Ch], eax
0x18000a5e5  mov     ecx, edi; this
0x18000a5e7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a5ec  jmp     short loc_18000A5FE
0x18000a5ee  mov     ecx, edi; this
0x18000a5f0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a5f5  jmp     short loc_18000A5FE
0x18000a5f7  mov     ecx, edi; this
0x18000a5f9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a5fe  mov     ebp, eax
0x18000a600  mov     [rbx], r15d
0x18000a603  mov     eax, [rsp+78h+arg_70]
0x18000a60a  mov     [rbx+4], eax
0x18000a60d  cmp     dword ptr [r14+8], 1
0x18000a612  jnz     short loc_18000A61A
0x18000a614  or      eax, 8
0x18000a617  mov     [rbx+4], eax
0x18000a61a  mov     eax, 1
0x18000a61f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a627  inc     eax
0x18000a629  mov     [rbx+10h], eax
0x18000a62c  mov     rax, [rsp+78h+arg_40]
0x18000a634  xor     edi, edi
0x18000a636  test    rax, rax
0x18000a639  jz      short loc_18000A640
0x18000a63b  cmp     [rax], di
0x18000a63e  jnz     short loc_18000A643
0x18000a640  mov     rax, rdi
0x18000a643  mov     [rbx+18h], rax
0x18000a647  call    cs:__imp_GetCurrentThreadId
0x18000a64d  mov     [rbx+20h], eax
0x18000a650  mov     [rbx+38h], r13
0x18000a654  mov     eax, [rsp+78h+arg_8]
0x18000a65b  mov     [rbx+40h], eax
0x18000a65e  mov     [rbx+44h], ebp
0x18000a661  mov     rax, [rsp+78h+arg_20]
0x18000a669  mov     [rbx+28h], rax
0x18000a66d  mov     [rbx+30h], r12
0x18000a671  mov     rax, [rsp+78h+arg_28]
0x18000a679  mov     [rbx+88h], rax
0x18000a680  mov     rax, [rsp+78h+arg_0]
0x18000a688  mov     [rbx+90h], rax
0x18000a68f  mov     [rbx+48h], rdi
0x18000a693  xorps   xmm0, xmm0
0x18000a696  xor     eax, eax
0x18000a698  movups  xmmword ptr [rbx+68h], xmm0
0x18000a69c  mov     [rbx+78h], rax
0x18000a6a0  movups  xmmword ptr [rbx+50h], xmm0
0x18000a6a4  mov     [rbx+60h], rax
0x18000a6a8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a6af  test    rax, rax
0x18000a6b2  jz      short loc_18000A6BB
0x18000a6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6b9  jmp     short loc_18000A6BE
0x18000a6bb  mov     rax, rdi
0x18000a6be  mov     [rbx+80h], rax
0x18000a6c5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a6cc  test    rax, rax
0x18000a6cf  jz      short loc_18000A6D9
0x18000a6d1  mov     rcx, rbx
0x18000a6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6d9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a6e0  test    rax, rax
0x18000a6e3  jz      short loc_18000A6FB
0x18000a6e5  mov     r8d, 400h
0x18000a6eb  mov     rdx, [rsp+78h+arg_60]
0x18000a6f3  mov     rcx, rbx
0x18000a6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6fb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a702  test    rax, rax
0x18000a705  jz      short loc_18000A70F
0x18000a707  mov     rcx, rbx
0x18000a70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a70f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a716  test    rax, rax
0x18000a719  jz      short loc_18000A729
0x18000a71b  test    byte ptr [rbx+4], 2
0x18000a71f  jnz     short loc_18000A729
0x18000a721  mov     rcx, rbx
0x18000a724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a729  cmp     [rbx+8], edi
0x18000a72c  jl      short loc_18000A74A
0x18000a72e  cmp     r15d, 3
0x18000a732  jz      short loc_18000A73A
0x18000a734  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a73a  mov     ecx, 8000FFFFh; this
0x18000a73f  mov     [rbx+8], ecx
0x18000a742  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a747  mov     [rbx+0Ch], eax
0x18000a74a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a751  jnz     short loc_18000A772
0x18000a753  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a75a  test    rax, rax
0x18000a75d  jz      short loc_18000A768
0x18000a75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a764  test    al, al
0x18000a766  jmp     short loc_18000A770
0x18000a768  call    cs:__imp_IsDebuggerPresent
0x18000a76e  test    eax, eax
0x18000a770  jz      short loc_18000A778
0x18000a772  test    byte ptr [rbx+4], 2
0x18000a776  jz      short loc_18000A79C
0x18000a778  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a77f  test    rax, rax
0x18000a782  jz      short loc_18000A7E0
0x18000a784  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a78b  jnz     short loc_18000A7E0
0x18000a78d  xor     r8d, r8d
0x18000a790  xor     edx, edx
0x18000a792  mov     rcx, rbx
0x18000a795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a79a  jmp     short loc_18000A7E0
0x18000a79c  mov     ebp, 800h
0x18000a7a1  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a7a8  test    rax, rax
0x18000a7ab  jz      short loc_18000A7C4
0x18000a7ad  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a7b4  jnz     short loc_18000A7C4
0x18000a7b6  mov     r8d, ebp
0x18000a7b9  mov     rdx, rsi
0x18000a7bc  mov     rcx, rbx
0x18000a7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c4  cmp     [rsi], di
0x18000a7c7  jnz     short loc_18000A7D7
0x18000a7c9  mov     r8, rbx; unsigned __int64
0x18000a7cc  mov     rdx, rbp; unsigned __int16 *
0x18000a7cf  mov     rcx, rsi; this
0x18000a7d2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a7d7  mov     rcx, rsi; lpOutputString
0x18000a7da  call    cs:__imp_OutputDebugStringW
0x18000a7e0  test    byte ptr [rbx+4], 4
0x18000a7e4  jnz     short loc_18000A7EF
0x18000a7e6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a7ed  jz      short loc_18000A801
0x18000a7ef  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a7f6  test    rax, rax
0x18000a7f9  jz      short loc_18000A801
0x18000a7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a800  nop
0x18000a801  mov     rbx, [rsp+78h+arg_10]
0x18000a809  add     rsp, 40h
0x18000a80d  pop     r15
0x18000a80f  pop     r14
0x18000a811  pop     r13
0x18000a813  pop     r12
0x18000a815  pop     rdi
0x18000a816  pop     rsi
0x18000a817  pop     rbp
0x18000a818  retn
```
