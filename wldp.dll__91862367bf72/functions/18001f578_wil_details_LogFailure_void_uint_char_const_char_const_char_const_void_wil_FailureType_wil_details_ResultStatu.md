# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001f578`
- end: `0x18001f86d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001f47c`
- `0x180024948`
- `0x180024a08`
- `0x18002e060`

## callees

- `0x18001b884`
- `0x18001f578`
- `0x18001f880`
- `0x180024894`
- `0x180025424`
- `0x180025dfc`
- `0x180025e18`
- `0x180025e34`
- `0x1800267cc`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f69b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f69b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f82e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f82e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f7bc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f7bc`

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
0x18001f578  mov     [rsp+arg_10], rbx
0x18001f57d  mov     [rsp+arg_8], edx
0x18001f581  mov     [rsp+arg_0], rcx
0x18001f586  push    rbp
0x18001f587  push    rsi
0x18001f588  push    rdi
0x18001f589  push    r12
0x18001f58b  push    r13
0x18001f58d  push    r14
0x18001f58f  push    r15
0x18001f591  sub     rsp, 40h
0x18001f595  mov     r12, r9
0x18001f598  mov     r13, r8
0x18001f59b  mov     r10, rcx
0x18001f59e  xor     eax, eax
0x18001f5a0  mov     rsi, [rsp+78h+lpOutputString]
0x18001f5a8  mov     [rsi], ax
0x18001f5ab  mov     rax, [rsp+78h+arg_60]
0x18001f5b3  mov     byte ptr [rax], 0
0x18001f5b6  mov     r14, [rsp+78h+arg_38]
0x18001f5be  mov     edi, [r14]
0x18001f5c1  mov     rbx, [rsp+78h+arg_78]
0x18001f5c9  mov     [rbx+8], edi
0x18001f5cc  mov     eax, [r14+4]
0x18001f5d0  mov     [rbx+0Ch], eax
0x18001f5d3  xor     ebp, ebp
0x18001f5d5  mov     r15d, [rsp+78h+arg_30]
0x18001f5dd  mov     ecx, r15d
0x18001f5e0  test    r15d, r15d
0x18001f5e3  jz      short loc_18001F64B
0x18001f5e5  sub     ecx, 1
0x18001f5e8  jz      short loc_18001F642
0x18001f5ea  sub     ecx, 1
0x18001f5ed  jz      short loc_18001F5FD
0x18001f5ef  cmp     ecx, 1
0x18001f5f2  jnz     short loc_18001F654
0x18001f5f4  mov     ecx, edi; this
0x18001f5f6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001f5fb  jmp     short loc_18001F652
0x18001f5fd  test    edi, edi
0x18001f5ff  js      short loc_18001F639
0x18001f601  mov     edi, 8007029Ch
0x18001f606  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001f60a  mov     rax, [rsp+78h+arg_28]
0x18001f612  mov     [rsp+78h+var_50], rax; __int64
0x18001f617  mov     rax, [rsp+78h+arg_20]
0x18001f61f  mov     [rsp+78h+var_58], rax; __int64
0x18001f624  mov     rcx, r10; int
0x18001f627  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001f62c  mov     [rbx+8], edi
0x18001f62f  mov     ecx, edi; this
0x18001f631  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001f636  mov     [rbx+0Ch], eax
0x18001f639  mov     ecx, edi; this
0x18001f63b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001f640  jmp     short loc_18001F652
0x18001f642  mov     ecx, edi; this
0x18001f644  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001f649  jmp     short loc_18001F652
0x18001f64b  mov     ecx, edi; this
0x18001f64d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001f652  mov     ebp, eax
0x18001f654  mov     [rbx], r15d
0x18001f657  mov     eax, [rsp+78h+arg_70]
0x18001f65e  mov     [rbx+4], eax
0x18001f661  cmp     dword ptr [r14+8], 1
0x18001f666  jnz     short loc_18001F66E
0x18001f668  or      eax, 8
0x18001f66b  mov     [rbx+4], eax
0x18001f66e  mov     eax, 1
0x18001f673  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001f67b  inc     eax
0x18001f67d  mov     [rbx+10h], eax
0x18001f680  mov     rax, [rsp+78h+arg_40]
0x18001f688  xor     edi, edi
0x18001f68a  test    rax, rax
0x18001f68d  jz      short loc_18001F694
0x18001f68f  cmp     [rax], di
0x18001f692  jnz     short loc_18001F697
0x18001f694  mov     rax, rdi
0x18001f697  mov     [rbx+18h], rax
0x18001f69b  call    cs:__imp_GetCurrentThreadId
0x18001f6a1  mov     [rbx+20h], eax
0x18001f6a4  mov     [rbx+38h], r13
0x18001f6a8  mov     eax, [rsp+78h+arg_8]
0x18001f6af  mov     [rbx+40h], eax
0x18001f6b2  mov     [rbx+44h], ebp
0x18001f6b5  mov     rax, [rsp+78h+arg_20]
0x18001f6bd  mov     [rbx+28h], rax
0x18001f6c1  mov     [rbx+30h], r12
0x18001f6c5  mov     rax, [rsp+78h+arg_28]
0x18001f6cd  mov     [rbx+88h], rax
0x18001f6d4  mov     rax, [rsp+78h+arg_0]
0x18001f6dc  mov     [rbx+90h], rax
0x18001f6e3  mov     [rbx+48h], rdi
0x18001f6e7  xorps   xmm0, xmm0
0x18001f6ea  xor     eax, eax
0x18001f6ec  movups  xmmword ptr [rbx+68h], xmm0
0x18001f6f0  mov     [rbx+78h], rax
0x18001f6f4  movups  xmmword ptr [rbx+50h], xmm0
0x18001f6f8  mov     [rbx+60h], rax
0x18001f6fc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001f703  test    rax, rax
0x18001f706  jz      short loc_18001F70F
0x18001f708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f70d  jmp     short loc_18001F712
0x18001f70f  mov     rax, rdi
0x18001f712  mov     [rbx+80h], rax
0x18001f719  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001f720  test    rax, rax
0x18001f723  jz      short loc_18001F72D
0x18001f725  mov     rcx, rbx
0x18001f728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f72d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001f734  test    rax, rax
0x18001f737  jz      short loc_18001F74F
0x18001f739  mov     r8d, 400h
0x18001f73f  mov     rdx, [rsp+78h+arg_60]
0x18001f747  mov     rcx, rbx
0x18001f74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f74f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f756  test    rax, rax
0x18001f759  jz      short loc_18001F763
0x18001f75b  mov     rcx, rbx
0x18001f75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f763  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f76a  test    rax, rax
0x18001f76d  jz      short loc_18001F77D
0x18001f76f  test    byte ptr [rbx+4], 2
0x18001f773  jnz     short loc_18001F77D
0x18001f775  mov     rcx, rbx
0x18001f778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f77d  cmp     [rbx+8], edi
0x18001f780  jl      short loc_18001F79E
0x18001f782  cmp     r15d, 3
0x18001f786  jz      short loc_18001F78E
0x18001f788  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001f78e  mov     ecx, 8000FFFFh; this
0x18001f793  mov     [rbx+8], ecx
0x18001f796  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001f79b  mov     [rbx+0Ch], eax
0x18001f79e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001f7a5  jnz     short loc_18001F7C6
0x18001f7a7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001f7ae  test    rax, rax
0x18001f7b1  jz      short loc_18001F7BC
0x18001f7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7b8  test    al, al
0x18001f7ba  jmp     short loc_18001F7C4
0x18001f7bc  call    cs:__imp_IsDebuggerPresent
0x18001f7c2  test    eax, eax
0x18001f7c4  jz      short loc_18001F7CC
0x18001f7c6  test    byte ptr [rbx+4], 2
0x18001f7ca  jz      short loc_18001F7F0
0x18001f7cc  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f7d3  test    rax, rax
0x18001f7d6  jz      short loc_18001F834
0x18001f7d8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001f7df  jnz     short loc_18001F834
0x18001f7e1  xor     r8d, r8d
0x18001f7e4  xor     edx, edx
0x18001f7e6  mov     rcx, rbx
0x18001f7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7ee  jmp     short loc_18001F834
0x18001f7f0  mov     ebp, 800h
0x18001f7f5  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f7fc  test    rax, rax
0x18001f7ff  jz      short loc_18001F818
0x18001f801  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001f808  jnz     short loc_18001F818
0x18001f80a  mov     r8d, ebp
0x18001f80d  mov     rdx, rsi
0x18001f810  mov     rcx, rbx
0x18001f813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f818  cmp     [rsi], di
0x18001f81b  jnz     short loc_18001F82B
0x18001f81d  mov     r8, rbx; unsigned __int64
0x18001f820  mov     rdx, rbp; unsigned __int16 *
0x18001f823  mov     rcx, rsi; this
0x18001f826  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001f82b  mov     rcx, rsi; lpOutputString
0x18001f82e  call    cs:__imp_OutputDebugStringW
0x18001f834  test    byte ptr [rbx+4], 4
0x18001f838  jnz     short loc_18001F843
0x18001f83a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001f841  jz      short loc_18001F855
0x18001f843  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001f84a  test    rax, rax
0x18001f84d  jz      short loc_18001F855
0x18001f84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f854  nop
0x18001f855  mov     rbx, [rsp+78h+arg_10]
0x18001f85d  add     rsp, 40h
0x18001f861  pop     r15
0x18001f863  pop     r14
0x18001f865  pop     r13
0x18001f867  pop     r12
0x18001f869  pop     rdi
0x18001f86a  pop     rsi
0x18001f86b  pop     rbp
0x18001f86c  retn
```
