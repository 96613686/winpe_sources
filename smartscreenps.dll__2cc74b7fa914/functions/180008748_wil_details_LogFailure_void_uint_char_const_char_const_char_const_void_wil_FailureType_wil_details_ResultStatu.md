# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008748`
- end: `0x180008a41`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180006ebc`
- `0x180007200`
- `0x18000a058`

## callees

- `0x180006dfc`
- `0x180007d64`
- `0x180008558`
- `0x180008748`
- `0x180008d5c`
- `0x180008d80`
- `0x180008d94`
- `0x180008db0`
- `0x180009a84`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000886b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000886b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000898a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000898a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800089fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800089fc`

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
0x180008748  mov     [rsp+arg_10], rbx
0x18000874d  mov     [rsp+arg_8], edx
0x180008751  mov     [rsp+arg_0], rcx
0x180008756  push    rbp
0x180008757  push    rsi
0x180008758  push    rdi
0x180008759  push    r12
0x18000875b  push    r13
0x18000875d  push    r14
0x18000875f  push    r15
0x180008761  sub     rsp, 40h
0x180008765  mov     r12, r9
0x180008768  mov     r13, r8
0x18000876b  mov     r10, rcx
0x18000876e  xor     eax, eax
0x180008770  mov     rsi, [rsp+78h+lpOutputString]
0x180008778  mov     [rsi], ax
0x18000877b  mov     rax, [rsp+78h+arg_60]
0x180008783  mov     byte ptr [rax], 0
0x180008786  mov     r14, [rsp+78h+arg_38]
0x18000878e  mov     edi, [r14]
0x180008791  mov     rbx, [rsp+78h+arg_78]
0x180008799  mov     [rbx+8], edi
0x18000879c  mov     eax, [r14+4]
0x1800087a0  mov     [rbx+0Ch], eax
0x1800087a3  xor     ebp, ebp
0x1800087a5  mov     r15d, [rsp+78h+arg_30]
0x1800087ad  mov     ecx, r15d
0x1800087b0  test    r15d, r15d
0x1800087b3  jz      short loc_18000881B
0x1800087b5  sub     ecx, 1
0x1800087b8  jz      short loc_180008812
0x1800087ba  sub     ecx, 1
0x1800087bd  jz      short loc_1800087CD
0x1800087bf  cmp     ecx, 1
0x1800087c2  jnz     short loc_180008824
0x1800087c4  mov     ecx, edi; this
0x1800087c6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800087cb  jmp     short loc_180008822
0x1800087cd  test    edi, edi
0x1800087cf  js      short loc_180008809
0x1800087d1  mov     edi, 8007029Ch
0x1800087d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800087da  mov     rax, [rsp+78h+arg_28]
0x1800087e2  mov     [rsp+78h+var_50], rax; __int64
0x1800087e7  mov     rax, [rsp+78h+arg_20]
0x1800087ef  mov     [rsp+78h+var_58], rax; __int64
0x1800087f4  mov     rcx, r10; int
0x1800087f7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800087fc  mov     [rbx+8], edi
0x1800087ff  mov     ecx, edi; this
0x180008801  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008806  mov     [rbx+0Ch], eax
0x180008809  mov     ecx, edi; this
0x18000880b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008810  jmp     short loc_180008822
0x180008812  mov     ecx, edi; this
0x180008814  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008819  jmp     short loc_180008822
0x18000881b  mov     ecx, edi; this
0x18000881d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008822  mov     ebp, eax
0x180008824  mov     [rbx], r15d
0x180008827  mov     eax, [rsp+78h+arg_70]
0x18000882e  mov     [rbx+4], eax
0x180008831  cmp     dword ptr [r14+8], 1
0x180008836  jnz     short loc_18000883E
0x180008838  or      eax, 8
0x18000883b  mov     [rbx+4], eax
0x18000883e  mov     eax, 1
0x180008843  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000884b  inc     eax
0x18000884d  mov     [rbx+10h], eax
0x180008850  mov     rax, [rsp+78h+arg_40]
0x180008858  xor     edi, edi
0x18000885a  test    rax, rax
0x18000885d  jz      short loc_180008864
0x18000885f  cmp     [rax], di
0x180008862  jnz     short loc_180008867
0x180008864  mov     rax, rdi
0x180008867  mov     [rbx+18h], rax
0x18000886b  call    cs:__imp_GetCurrentThreadId
0x180008871  mov     [rbx+20h], eax
0x180008874  mov     [rbx+38h], r13
0x180008878  mov     eax, [rsp+78h+arg_8]
0x18000887f  mov     [rbx+40h], eax
0x180008882  mov     [rbx+44h], ebp
0x180008885  mov     rax, [rsp+78h+arg_20]
0x18000888d  mov     [rbx+28h], rax
0x180008891  mov     [rbx+30h], r12
0x180008895  mov     rax, [rsp+78h+arg_28]
0x18000889d  mov     [rbx+88h], rax
0x1800088a4  mov     rax, [rsp+78h+arg_0]
0x1800088ac  mov     [rbx+90h], rax
0x1800088b3  mov     [rbx+48h], rdi
0x1800088b7  xorps   xmm0, xmm0
0x1800088ba  xor     eax, eax
0x1800088bc  movups  xmmword ptr [rbx+68h], xmm0
0x1800088c0  mov     [rbx+78h], rax
0x1800088c4  movups  xmmword ptr [rbx+50h], xmm0
0x1800088c8  mov     [rbx+60h], rax
0x1800088cc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800088d3  test    rax, rax
0x1800088d6  jz      short loc_1800088DF
0x1800088d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088dd  jmp     short loc_1800088E2
0x1800088df  mov     rax, rdi
0x1800088e2  mov     [rbx+80h], rax
0x1800088e9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800088f0  test    rax, rax
0x1800088f3  jz      short loc_1800088FD
0x1800088f5  mov     rcx, rbx
0x1800088f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088fd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008904  test    rax, rax
0x180008907  jz      short loc_18000891F
0x180008909  mov     r8d, 400h
0x18000890f  mov     rdx, [rsp+78h+arg_60]
0x180008917  mov     rcx, rbx
0x18000891a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000891f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008926  test    rax, rax
0x180008929  jz      short loc_180008933
0x18000892b  mov     rcx, rbx
0x18000892e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008933  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000893a  test    rax, rax
0x18000893d  jz      short loc_18000894D
0x18000893f  test    byte ptr [rbx+4], 2
0x180008943  jnz     short loc_18000894D
0x180008945  mov     rcx, rbx
0x180008948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000894d  cmp     [rbx+8], edi
0x180008950  jl      short loc_18000896C
0x180008952  cmp     r15d, 3
0x180008956  jnz     loc_180008A3B
0x18000895c  mov     ecx, 8000FFFFh; this
0x180008961  mov     [rbx+8], ecx
0x180008964  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008969  mov     [rbx+0Ch], eax
0x18000896c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008973  jnz     short loc_180008994
0x180008975  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000897c  test    rax, rax
0x18000897f  jz      short loc_18000898A
0x180008981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008986  test    al, al
0x180008988  jmp     short loc_180008992
0x18000898a  call    cs:__imp_IsDebuggerPresent
0x180008990  test    eax, eax
0x180008992  jz      short loc_18000899A
0x180008994  test    byte ptr [rbx+4], 2
0x180008998  jz      short loc_1800089BE
0x18000899a  mov     rax, cs:g_pfnResultLoggingCallback
0x1800089a1  test    rax, rax
0x1800089a4  jz      short loc_180008A02
0x1800089a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800089ad  jnz     short loc_180008A02
0x1800089af  xor     r8d, r8d
0x1800089b2  xor     edx, edx
0x1800089b4  mov     rcx, rbx
0x1800089b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089bc  jmp     short loc_180008A02
0x1800089be  mov     ebp, 800h
0x1800089c3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800089ca  test    rax, rax
0x1800089cd  jz      short loc_1800089E6
0x1800089cf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800089d6  jnz     short loc_1800089E6
0x1800089d8  mov     r8d, ebp
0x1800089db  mov     rdx, rsi
0x1800089de  mov     rcx, rbx
0x1800089e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089e6  cmp     [rsi], di
0x1800089e9  jnz     short loc_1800089F9
0x1800089eb  mov     r8, rbx; unsigned __int64
0x1800089ee  mov     rdx, rbp; unsigned __int16 *
0x1800089f1  mov     rcx, rsi; this
0x1800089f4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800089f9  mov     rcx, rsi; lpOutputString
0x1800089fc  call    cs:__imp_OutputDebugStringW
0x180008a02  test    byte ptr [rbx+4], 4
0x180008a06  jnz     short loc_180008A11
0x180008a08  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008a0f  jz      short loc_180008A23
0x180008a11  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008a18  test    rax, rax
0x180008a1b  jz      short loc_180008A23
0x180008a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a22  nop
0x180008a23  mov     rbx, [rsp+78h+arg_10]
0x180008a2b  add     rsp, 40h
0x180008a2f  pop     r15
0x180008a31  pop     r14
0x180008a33  pop     r13
0x180008a35  pop     r12
0x180008a37  pop     rdi
0x180008a38  pop     rsi
0x180008a39  pop     rbp
0x180008a3a  retn
0x180008a3b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
