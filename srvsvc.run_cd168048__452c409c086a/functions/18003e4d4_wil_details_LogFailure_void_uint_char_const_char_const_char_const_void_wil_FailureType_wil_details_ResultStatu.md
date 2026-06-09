# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003e4d4`
- end: `0x18003e7cc`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18003c4e0`

## callees

- `0x18003bf1c`
- `0x18003d884`
- `0x18003e0f0`
- `0x18003e4d4`
- `0x18003f114`
- `0x18003f130`
- `0x18003f2b4`
- `0x18003f2d0`
- `0x180040988`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e5f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e5f7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003e788`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003e788`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003e716`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003e716`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x18003e4d4  mov     [rsp+arg_10], rbx
0x18003e4d9  mov     [rsp+arg_8], edx
0x18003e4dd  mov     [rsp+arg_0], rcx
0x18003e4e2  push    rbp
0x18003e4e3  push    rsi
0x18003e4e4  push    rdi
0x18003e4e5  push    r12
0x18003e4e7  push    r13
0x18003e4e9  push    r14
0x18003e4eb  push    r15
0x18003e4ed  sub     rsp, 40h
0x18003e4f1  mov     r14, [rsp+78h+arg_38]
0x18003e4f9  xor     eax, eax
0x18003e4fb  mov     rbx, [rsp+78h+arg_78]
0x18003e503  xor     ebp, ebp
0x18003e505  mov     r15d, [rsp+78h+arg_30]
0x18003e50d  mov     r10, rcx
0x18003e510  mov     rsi, [rsp+78h+lpOutputString]
0x18003e518  mov     r12, r9
0x18003e51b  mov     r13, r8
0x18003e51e  mov     ecx, r15d
0x18003e521  mov     [rsi], ax
0x18003e524  mov     rax, [rsp+78h+arg_60]
0x18003e52c  mov     byte ptr [rax], 0
0x18003e52f  mov     edi, [r14]
0x18003e532  mov     [rbx+8], edi
0x18003e535  mov     eax, [r14+4]
0x18003e539  mov     [rbx+0Ch], eax
0x18003e53c  test    r15d, r15d
0x18003e53f  jz      short loc_18003E5A7
0x18003e541  sub     ecx, 1
0x18003e544  jz      short loc_18003E59E
0x18003e546  sub     ecx, 1
0x18003e549  jz      short loc_18003E559
0x18003e54b  cmp     ecx, 1
0x18003e54e  jnz     short loc_18003E5B0
0x18003e550  mov     ecx, edi; this
0x18003e552  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003e557  jmp     short loc_18003E5AE
0x18003e559  test    edi, edi
0x18003e55b  js      short loc_18003E595
0x18003e55d  mov     rax, [rsp+78h+arg_28]
0x18003e565  mov     edi, 8007029Ch
0x18003e56a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003e56e  mov     rcx, r10; int
0x18003e571  mov     [rsp+78h+var_50], rax; __int64
0x18003e576  mov     rax, [rsp+78h+arg_20]
0x18003e57e  mov     [rsp+78h+var_58], rax; __int64
0x18003e583  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003e588  mov     ecx, edi; this
0x18003e58a  mov     [rbx+8], edi
0x18003e58d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003e592  mov     [rbx+0Ch], eax
0x18003e595  mov     ecx, edi; this
0x18003e597  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003e59c  jmp     short loc_18003E5AE
0x18003e59e  mov     ecx, edi; this
0x18003e5a0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003e5a5  jmp     short loc_18003E5AE
0x18003e5a7  mov     ecx, edi; this
0x18003e5a9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003e5ae  mov     ebp, eax
0x18003e5b0  mov     eax, [rsp+78h+arg_70]
0x18003e5b7  mov     [rbx+4], eax
0x18003e5ba  mov     [rbx], r15d
0x18003e5bd  cmp     dword ptr [r14+8], 1
0x18003e5c2  jnz     short loc_18003E5CA
0x18003e5c4  or      eax, 8
0x18003e5c7  mov     [rbx+4], eax
0x18003e5ca  mov     eax, 1
0x18003e5cf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003e5d7  inc     eax
0x18003e5d9  xor     edi, edi
0x18003e5db  mov     [rbx+10h], eax
0x18003e5de  mov     rax, [rsp+78h+arg_40]
0x18003e5e6  test    rax, rax
0x18003e5e9  jz      short loc_18003E5F0
0x18003e5eb  cmp     [rax], di
0x18003e5ee  jnz     short loc_18003E5F3
0x18003e5f0  mov     rax, rdi
0x18003e5f3  mov     [rbx+18h], rax
0x18003e5f7  call    cs:__imp_GetCurrentThreadId
0x18003e5fd  mov     [rbx+38h], r13
0x18003e601  xorps   xmm0, xmm0
0x18003e604  mov     [rbx+20h], eax
0x18003e607  mov     eax, [rsp+78h+arg_8]
0x18003e60e  mov     [rbx+40h], eax
0x18003e611  mov     rax, [rsp+78h+arg_20]
0x18003e619  mov     [rbx+28h], rax
0x18003e61d  mov     rax, [rsp+78h+arg_28]
0x18003e625  mov     [rbx+88h], rax
0x18003e62c  mov     rax, [rsp+78h+arg_0]
0x18003e634  mov     [rbx+90h], rax
0x18003e63b  xor     eax, eax
0x18003e63d  mov     [rbx+44h], ebp
0x18003e640  mov     [rbx+30h], r12
0x18003e644  mov     [rbx+48h], rdi
0x18003e648  movups  xmmword ptr [rbx+68h], xmm0
0x18003e64c  mov     [rbx+78h], rax
0x18003e650  movups  xmmword ptr [rbx+50h], xmm0
0x18003e654  mov     [rbx+60h], rax
0x18003e658  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003e65f  test    rax, rax
0x18003e662  jz      short loc_18003E66B
0x18003e664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e669  jmp     short loc_18003E66E
0x18003e66b  mov     rax, rdi
0x18003e66e  mov     [rbx+80h], rax
0x18003e675  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003e67c  test    rax, rax
0x18003e67f  jz      short loc_18003E689
0x18003e681  mov     rcx, rbx
0x18003e684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e689  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003e690  test    rax, rax
0x18003e693  jz      short loc_18003E6AB
0x18003e695  mov     rdx, [rsp+78h+arg_60]
0x18003e69d  mov     r8d, 400h
0x18003e6a3  mov     rcx, rbx
0x18003e6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6ab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003e6b2  test    rax, rax
0x18003e6b5  jz      short loc_18003E6BF
0x18003e6b7  mov     rcx, rbx
0x18003e6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6bf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003e6c6  test    rax, rax
0x18003e6c9  jz      short loc_18003E6D9
0x18003e6cb  test    byte ptr [rbx+4], 2
0x18003e6cf  jnz     short loc_18003E6D9
0x18003e6d1  mov     rcx, rbx
0x18003e6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6d9  cmp     [rbx+8], edi
0x18003e6dc  jl      short loc_18003E6F8
0x18003e6de  cmp     r15d, 3
0x18003e6e2  jnz     loc_18003E7C6
0x18003e6e8  mov     ecx, 8000FFFFh; this
0x18003e6ed  mov     [rbx+8], ecx
0x18003e6f0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003e6f5  mov     [rbx+0Ch], eax
0x18003e6f8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18003e6ff  jnz     short loc_18003E720
0x18003e701  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003e708  test    rax, rax
0x18003e70b  jz      short loc_18003E716
0x18003e70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e712  test    al, al
0x18003e714  jmp     short loc_18003E71E
0x18003e716  call    cs:__imp_IsDebuggerPresent
0x18003e71c  test    eax, eax
0x18003e71e  jz      short loc_18003E726
0x18003e720  test    byte ptr [rbx+4], 2
0x18003e724  jz      short loc_18003E74A
0x18003e726  mov     rax, cs:g_pfnResultLoggingCallback
0x18003e72d  test    rax, rax
0x18003e730  jz      short loc_18003E78E
0x18003e732  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003e739  jnz     short loc_18003E78E
0x18003e73b  xor     r8d, r8d
0x18003e73e  xor     edx, edx
0x18003e740  mov     rcx, rbx
0x18003e743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e748  jmp     short loc_18003E78E
0x18003e74a  mov     rax, cs:g_pfnResultLoggingCallback
0x18003e751  mov     ebp, 800h
0x18003e756  test    rax, rax
0x18003e759  jz      short loc_18003E772
0x18003e75b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003e762  jnz     short loc_18003E772
0x18003e764  mov     r8d, ebp
0x18003e767  mov     rdx, rsi
0x18003e76a  mov     rcx, rbx
0x18003e76d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e772  cmp     [rsi], di
0x18003e775  jnz     short loc_18003E785
0x18003e777  mov     r8, rbx; unsigned __int64
0x18003e77a  mov     rdx, rbp; unsigned __int16 *
0x18003e77d  mov     rcx, rsi; this
0x18003e780  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003e785  mov     rcx, rsi; lpOutputString
0x18003e788  call    cs:__imp_OutputDebugStringW
0x18003e78e  test    byte ptr [rbx+4], 4
0x18003e792  jnz     short loc_18003E79D
0x18003e794  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003e79b  jz      short loc_18003E7AE
0x18003e79d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003e7a4  test    rax, rax
0x18003e7a7  jz      short loc_18003E7AE
0x18003e7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7ae  mov     rbx, [rsp+78h+arg_10]
0x18003e7b6  add     rsp, 40h
0x18003e7ba  pop     r15
0x18003e7bc  pop     r14
0x18003e7be  pop     r13
0x18003e7c0  pop     r12
0x18003e7c2  pop     rdi
0x18003e7c3  pop     rsi
0x18003e7c4  pop     rbp
0x18003e7c5  retn
0x18003e7c6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
