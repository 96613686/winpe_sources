# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000c6a0`
- end: `0x18000c995`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000b248`
- `0x18000b2fc`
- `0x18000b3f0`

## callees

- `0x180009144`
- `0x18000b198`
- `0x18000bf54`
- `0x18000c6a0`
- `0x18000cc6c`
- `0x18000cc90`
- `0x18000cca4`
- `0x18000ccc0`
- `0x18000d84c`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c7c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c7c3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c956`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c956`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c8e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c8e4`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x18000c6a0  mov     [rsp+arg_10], rbx
0x18000c6a5  mov     [rsp+arg_8], edx
0x18000c6a9  mov     [rsp+arg_0], rcx
0x18000c6ae  push    rbp
0x18000c6af  push    rsi
0x18000c6b0  push    rdi
0x18000c6b1  push    r12
0x18000c6b3  push    r13
0x18000c6b5  push    r14
0x18000c6b7  push    r15
0x18000c6b9  sub     rsp, 40h
0x18000c6bd  mov     r12, r9
0x18000c6c0  mov     r13, r8
0x18000c6c3  mov     r10, rcx
0x18000c6c6  xor     eax, eax
0x18000c6c8  mov     rsi, [rsp+78h+lpOutputString]
0x18000c6d0  mov     [rsi], ax
0x18000c6d3  mov     rax, [rsp+78h+arg_60]
0x18000c6db  mov     byte ptr [rax], 0
0x18000c6de  mov     r14, [rsp+78h+arg_38]
0x18000c6e6  mov     edi, [r14]
0x18000c6e9  mov     rbx, [rsp+78h+arg_78]
0x18000c6f1  mov     [rbx+8], edi
0x18000c6f4  mov     eax, [r14+4]
0x18000c6f8  mov     [rbx+0Ch], eax
0x18000c6fb  xor     ebp, ebp
0x18000c6fd  mov     r15d, [rsp+78h+arg_30]
0x18000c705  mov     ecx, r15d
0x18000c708  test    r15d, r15d
0x18000c70b  jz      short loc_18000C773
0x18000c70d  sub     ecx, 1
0x18000c710  jz      short loc_18000C76A
0x18000c712  sub     ecx, 1
0x18000c715  jz      short loc_18000C725
0x18000c717  cmp     ecx, 1
0x18000c71a  jnz     short loc_18000C77C
0x18000c71c  mov     ecx, edi; this
0x18000c71e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000c723  jmp     short loc_18000C77A
0x18000c725  test    edi, edi
0x18000c727  js      short loc_18000C761
0x18000c729  mov     edi, 8007029Ch
0x18000c72e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000c732  mov     rax, [rsp+78h+arg_28]
0x18000c73a  mov     [rsp+78h+var_50], rax; __int64
0x18000c73f  mov     rax, [rsp+78h+arg_20]
0x18000c747  mov     [rsp+78h+var_58], rax; __int64
0x18000c74c  mov     rcx, r10; int
0x18000c74f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000c754  mov     [rbx+8], edi
0x18000c757  mov     ecx, edi; this
0x18000c759  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c75e  mov     [rbx+0Ch], eax
0x18000c761  mov     ecx, edi; this
0x18000c763  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000c768  jmp     short loc_18000C77A
0x18000c76a  mov     ecx, edi; this
0x18000c76c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000c771  jmp     short loc_18000C77A
0x18000c773  mov     ecx, edi; this
0x18000c775  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000c77a  mov     ebp, eax
0x18000c77c  mov     [rbx], r15d
0x18000c77f  mov     eax, [rsp+78h+arg_70]
0x18000c786  mov     [rbx+4], eax
0x18000c789  cmp     dword ptr [r14+8], 1
0x18000c78e  jnz     short loc_18000C796
0x18000c790  or      eax, 8
0x18000c793  mov     [rbx+4], eax
0x18000c796  mov     eax, 1
0x18000c79b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c7a3  inc     eax
0x18000c7a5  mov     [rbx+10h], eax
0x18000c7a8  mov     rax, [rsp+78h+arg_40]
0x18000c7b0  xor     edi, edi
0x18000c7b2  test    rax, rax
0x18000c7b5  jz      short loc_18000C7BC
0x18000c7b7  cmp     [rax], di
0x18000c7ba  jnz     short loc_18000C7BF
0x18000c7bc  mov     rax, rdi
0x18000c7bf  mov     [rbx+18h], rax
0x18000c7c3  call    cs:__imp_GetCurrentThreadId
0x18000c7c9  mov     [rbx+20h], eax
0x18000c7cc  mov     [rbx+38h], r13
0x18000c7d0  mov     eax, [rsp+78h+arg_8]
0x18000c7d7  mov     [rbx+40h], eax
0x18000c7da  mov     [rbx+44h], ebp
0x18000c7dd  mov     rax, [rsp+78h+arg_20]
0x18000c7e5  mov     [rbx+28h], rax
0x18000c7e9  mov     [rbx+30h], r12
0x18000c7ed  mov     rax, [rsp+78h+arg_28]
0x18000c7f5  mov     [rbx+88h], rax
0x18000c7fc  mov     rax, [rsp+78h+arg_0]
0x18000c804  mov     [rbx+90h], rax
0x18000c80b  mov     [rbx+48h], rdi
0x18000c80f  xorps   xmm0, xmm0
0x18000c812  xor     eax, eax
0x18000c814  movups  xmmword ptr [rbx+68h], xmm0
0x18000c818  mov     [rbx+78h], rax
0x18000c81c  movups  xmmword ptr [rbx+50h], xmm0
0x18000c820  mov     [rbx+60h], rax
0x18000c824  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c82b  test    rax, rax
0x18000c82e  jz      short loc_18000C837
0x18000c830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c835  jmp     short loc_18000C83A
0x18000c837  mov     rax, rdi
0x18000c83a  mov     [rbx+80h], rax
0x18000c841  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c848  test    rax, rax
0x18000c84b  jz      short loc_18000C855
0x18000c84d  mov     rcx, rbx
0x18000c850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c855  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c85c  test    rax, rax
0x18000c85f  jz      short loc_18000C877
0x18000c861  mov     r8d, 400h
0x18000c867  mov     rdx, [rsp+78h+arg_60]
0x18000c86f  mov     rcx, rbx
0x18000c872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c877  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c87e  test    rax, rax
0x18000c881  jz      short loc_18000C88B
0x18000c883  mov     rcx, rbx
0x18000c886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c88b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c892  test    rax, rax
0x18000c895  jz      short loc_18000C8A5
0x18000c897  test    byte ptr [rbx+4], 2
0x18000c89b  jnz     short loc_18000C8A5
0x18000c89d  mov     rcx, rbx
0x18000c8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8a5  cmp     [rbx+8], edi
0x18000c8a8  jl      short loc_18000C8C6
0x18000c8aa  cmp     r15d, 3
0x18000c8ae  jz      short loc_18000C8B6
0x18000c8b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000c8b6  mov     ecx, 8000FFFFh; this
0x18000c8bb  mov     [rbx+8], ecx
0x18000c8be  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c8c3  mov     [rbx+0Ch], eax
0x18000c8c6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000c8cd  jnz     short loc_18000C8EE
0x18000c8cf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c8d6  test    rax, rax
0x18000c8d9  jz      short loc_18000C8E4
0x18000c8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8e0  test    al, al
0x18000c8e2  jmp     short loc_18000C8EC
0x18000c8e4  call    cs:__imp_IsDebuggerPresent
0x18000c8ea  test    eax, eax
0x18000c8ec  jz      short loc_18000C8F4
0x18000c8ee  test    byte ptr [rbx+4], 2
0x18000c8f2  jz      short loc_18000C918
0x18000c8f4  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c8fb  test    rax, rax
0x18000c8fe  jz      short loc_18000C95C
0x18000c900  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c907  jnz     short loc_18000C95C
0x18000c909  xor     r8d, r8d
0x18000c90c  xor     edx, edx
0x18000c90e  mov     rcx, rbx
0x18000c911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c916  jmp     short loc_18000C95C
0x18000c918  mov     ebp, 800h
0x18000c91d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c924  test    rax, rax
0x18000c927  jz      short loc_18000C940
0x18000c929  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c930  jnz     short loc_18000C940
0x18000c932  mov     r8d, ebp
0x18000c935  mov     rdx, rsi
0x18000c938  mov     rcx, rbx
0x18000c93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c940  cmp     [rsi], di
0x18000c943  jnz     short loc_18000C953
0x18000c945  mov     r8, rbx; unsigned __int64
0x18000c948  mov     rdx, rbp; unsigned __int16 *
0x18000c94b  mov     rcx, rsi; this
0x18000c94e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c953  mov     rcx, rsi; lpOutputString
0x18000c956  call    cs:__imp_OutputDebugStringW
0x18000c95c  test    byte ptr [rbx+4], 4
0x18000c960  jnz     short loc_18000C96B
0x18000c962  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000c969  jz      short loc_18000C97D
0x18000c96b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c972  test    rax, rax
0x18000c975  jz      short loc_18000C97D
0x18000c977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c97c  nop
0x18000c97d  mov     rbx, [rsp+78h+arg_10]
0x18000c985  add     rsp, 40h
0x18000c989  pop     r15
0x18000c98b  pop     r14
0x18000c98d  pop     r13
0x18000c98f  pop     r12
0x18000c991  pop     rdi
0x18000c992  pop     rsi
0x18000c993  pop     rbp
0x18000c994  retn
```
