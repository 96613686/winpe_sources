# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000c750`
- end: `0x18000ca49`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180007cc8`
- `0x180007d88`
- `0x1800081cc`

## callees

- `0x180007b94`
- `0x18000ba8c`
- `0x18000c3e4`
- `0x18000c750`
- `0x18000d54c`
- `0x18000d570`
- `0x18000d584`
- `0x18000d5a0`
- `0x18000ff18`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c873`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c873`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ca04`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ca04`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c992`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c992`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      wil::details::in1diag3::FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x18000c750  mov     [rsp+arg_10], rbx
0x18000c755  mov     [rsp+arg_8], edx
0x18000c759  mov     [rsp+arg_0], rcx
0x18000c75e  push    rbp
0x18000c75f  push    rsi
0x18000c760  push    rdi
0x18000c761  push    r12
0x18000c763  push    r13
0x18000c765  push    r14
0x18000c767  push    r15
0x18000c769  sub     rsp, 40h
0x18000c76d  mov     r12, r9
0x18000c770  mov     r13, r8
0x18000c773  mov     r10, rcx
0x18000c776  xor     eax, eax
0x18000c778  mov     rsi, [rsp+78h+lpOutputString]
0x18000c780  mov     [rsi], ax
0x18000c783  mov     rax, [rsp+78h+arg_60]
0x18000c78b  mov     byte ptr [rax], 0
0x18000c78e  mov     r14, [rsp+78h+arg_38]
0x18000c796  mov     edi, [r14]
0x18000c799  mov     rbx, [rsp+78h+arg_78]
0x18000c7a1  mov     [rbx+8], edi
0x18000c7a4  mov     eax, [r14+4]
0x18000c7a8  mov     [rbx+0Ch], eax
0x18000c7ab  xor     ebp, ebp
0x18000c7ad  mov     r15d, [rsp+78h+arg_30]
0x18000c7b5  mov     ecx, r15d
0x18000c7b8  test    r15d, r15d
0x18000c7bb  jz      short loc_18000C823
0x18000c7bd  sub     ecx, 1
0x18000c7c0  jz      short loc_18000C81A
0x18000c7c2  sub     ecx, 1
0x18000c7c5  jz      short loc_18000C7D5
0x18000c7c7  cmp     ecx, 1
0x18000c7ca  jnz     short loc_18000C82C
0x18000c7cc  mov     ecx, edi; this
0x18000c7ce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000c7d3  jmp     short loc_18000C82A
0x18000c7d5  test    edi, edi
0x18000c7d7  js      short loc_18000C811
0x18000c7d9  mov     edi, 8007029Ch
0x18000c7de  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000c7e2  mov     rax, [rsp+78h+arg_28]
0x18000c7ea  mov     [rsp+78h+var_50], rax; __int64
0x18000c7ef  mov     rax, [rsp+78h+arg_20]
0x18000c7f7  mov     [rsp+78h+var_58], rax; __int64
0x18000c7fc  mov     rcx, r10; int
0x18000c7ff  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000c804  mov     [rbx+8], edi
0x18000c807  mov     ecx, edi; this
0x18000c809  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c80e  mov     [rbx+0Ch], eax
0x18000c811  mov     ecx, edi; this
0x18000c813  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000c818  jmp     short loc_18000C82A
0x18000c81a  mov     ecx, edi; this
0x18000c81c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000c821  jmp     short loc_18000C82A
0x18000c823  mov     ecx, edi; this
0x18000c825  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000c82a  mov     ebp, eax
0x18000c82c  mov     [rbx], r15d
0x18000c82f  mov     eax, [rsp+78h+arg_70]
0x18000c836  mov     [rbx+4], eax
0x18000c839  cmp     dword ptr [r14+8], 1
0x18000c83e  jnz     short loc_18000C846
0x18000c840  or      eax, 8
0x18000c843  mov     [rbx+4], eax
0x18000c846  mov     eax, 1
0x18000c84b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c853  inc     eax
0x18000c855  mov     [rbx+10h], eax
0x18000c858  mov     rax, [rsp+78h+arg_40]
0x18000c860  xor     edi, edi
0x18000c862  test    rax, rax
0x18000c865  jz      short loc_18000C86C
0x18000c867  cmp     [rax], di
0x18000c86a  jnz     short loc_18000C86F
0x18000c86c  mov     rax, rdi
0x18000c86f  mov     [rbx+18h], rax
0x18000c873  call    cs:__imp_GetCurrentThreadId
0x18000c879  mov     [rbx+20h], eax
0x18000c87c  mov     [rbx+38h], r13
0x18000c880  mov     eax, [rsp+78h+arg_8]
0x18000c887  mov     [rbx+40h], eax
0x18000c88a  mov     [rbx+44h], ebp
0x18000c88d  mov     rax, [rsp+78h+arg_20]
0x18000c895  mov     [rbx+28h], rax
0x18000c899  mov     [rbx+30h], r12
0x18000c89d  mov     rax, [rsp+78h+arg_28]
0x18000c8a5  mov     [rbx+88h], rax
0x18000c8ac  mov     rax, [rsp+78h+arg_0]
0x18000c8b4  mov     [rbx+90h], rax
0x18000c8bb  mov     [rbx+48h], rdi
0x18000c8bf  xorps   xmm0, xmm0
0x18000c8c2  xor     eax, eax
0x18000c8c4  movups  xmmword ptr [rbx+68h], xmm0
0x18000c8c8  mov     [rbx+78h], rax
0x18000c8cc  movups  xmmword ptr [rbx+50h], xmm0
0x18000c8d0  mov     [rbx+60h], rax
0x18000c8d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c8db  test    rax, rax
0x18000c8de  jz      short loc_18000C8E7
0x18000c8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8e5  jmp     short loc_18000C8EA
0x18000c8e7  mov     rax, rdi
0x18000c8ea  mov     [rbx+80h], rax
0x18000c8f1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c8f8  test    rax, rax
0x18000c8fb  jz      short loc_18000C905
0x18000c8fd  mov     rcx, rbx
0x18000c900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c905  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c90c  test    rax, rax
0x18000c90f  jz      short loc_18000C927
0x18000c911  mov     r8d, 400h
0x18000c917  mov     rdx, [rsp+78h+arg_60]
0x18000c91f  mov     rcx, rbx
0x18000c922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c927  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c92e  test    rax, rax
0x18000c931  jz      short loc_18000C93B
0x18000c933  mov     rcx, rbx
0x18000c936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c93b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c942  test    rax, rax
0x18000c945  jz      short loc_18000C955
0x18000c947  test    byte ptr [rbx+4], 2
0x18000c94b  jnz     short loc_18000C955
0x18000c94d  mov     rcx, rbx
0x18000c950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c955  cmp     [rbx+8], edi
0x18000c958  jl      short loc_18000C974
0x18000c95a  cmp     r15d, 3
0x18000c95e  jnz     loc_18000CA43
0x18000c964  mov     ecx, 8000FFFFh; this
0x18000c969  mov     [rbx+8], ecx
0x18000c96c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c971  mov     [rbx+0Ch], eax
0x18000c974  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000c97b  jnz     short loc_18000C99C
0x18000c97d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c984  test    rax, rax
0x18000c987  jz      short loc_18000C992
0x18000c989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c98e  test    al, al
0x18000c990  jmp     short loc_18000C99A
0x18000c992  call    cs:__imp_IsDebuggerPresent
0x18000c998  test    eax, eax
0x18000c99a  jz      short loc_18000C9A2
0x18000c99c  test    byte ptr [rbx+4], 2
0x18000c9a0  jz      short loc_18000C9C6
0x18000c9a2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c9a9  test    rax, rax
0x18000c9ac  jz      short loc_18000CA0A
0x18000c9ae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c9b5  jnz     short loc_18000CA0A
0x18000c9b7  xor     r8d, r8d
0x18000c9ba  xor     edx, edx
0x18000c9bc  mov     rcx, rbx
0x18000c9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9c4  jmp     short loc_18000CA0A
0x18000c9c6  mov     ebp, 800h
0x18000c9cb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c9d2  test    rax, rax
0x18000c9d5  jz      short loc_18000C9EE
0x18000c9d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c9de  jnz     short loc_18000C9EE
0x18000c9e0  mov     r8d, ebp
0x18000c9e3  mov     rdx, rsi
0x18000c9e6  mov     rcx, rbx
0x18000c9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9ee  cmp     [rsi], di
0x18000c9f1  jnz     short loc_18000CA01
0x18000c9f3  mov     r8, rbx; unsigned __int64
0x18000c9f6  mov     rdx, rbp; unsigned __int16 *
0x18000c9f9  mov     rcx, rsi; this
0x18000c9fc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ca01  mov     rcx, rsi; lpOutputString
0x18000ca04  call    cs:__imp_OutputDebugStringW
0x18000ca0a  test    byte ptr [rbx+4], 4
0x18000ca0e  jnz     short loc_18000CA19
0x18000ca10  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000ca17  jz      short loc_18000CA2B
0x18000ca19  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ca20  test    rax, rax
0x18000ca23  jz      short loc_18000CA2B
0x18000ca25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca2a  nop
0x18000ca2b  mov     rbx, [rsp+78h+arg_10]
0x18000ca33  add     rsp, 40h
0x18000ca37  pop     r15
0x18000ca39  pop     r14
0x18000ca3b  pop     r13
0x18000ca3d  pop     r12
0x18000ca3f  pop     rdi
0x18000ca40  pop     rsi
0x18000ca41  pop     rbp
0x18000ca42  retn
0x18000ca43  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
