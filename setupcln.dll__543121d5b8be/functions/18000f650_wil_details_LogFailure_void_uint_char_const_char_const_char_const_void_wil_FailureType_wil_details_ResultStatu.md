# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000f650`
- end: `0x18000f949`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000d130`

## callees

- `0x18000cb6c`
- `0x18000e894`
- `0x18000f350`
- `0x18000f650`
- `0x1800102b0`
- `0x1800102d0`
- `0x180010454`
- `0x180010470`
- `0x180011dcc`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f773`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f904`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f904`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f892`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f892`

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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x18000f650  mov     [rsp+arg_10], rbx
0x18000f655  mov     [rsp+arg_8], edx
0x18000f659  mov     [rsp+arg_0], rcx
0x18000f65e  push    rbp
0x18000f65f  push    rsi
0x18000f660  push    rdi
0x18000f661  push    r12
0x18000f663  push    r13
0x18000f665  push    r14
0x18000f667  push    r15
0x18000f669  sub     rsp, 40h
0x18000f66d  mov     r12, r9
0x18000f670  mov     r13, r8
0x18000f673  mov     r10, rcx
0x18000f676  xor     eax, eax
0x18000f678  mov     rsi, [rsp+78h+lpOutputString]
0x18000f680  mov     [rsi], ax
0x18000f683  mov     rax, [rsp+78h+arg_60]
0x18000f68b  mov     byte ptr [rax], 0
0x18000f68e  mov     r14, [rsp+78h+arg_38]
0x18000f696  mov     edi, [r14]
0x18000f699  mov     rbx, [rsp+78h+arg_78]
0x18000f6a1  mov     [rbx+8], edi
0x18000f6a4  mov     eax, [r14+4]
0x18000f6a8  mov     [rbx+0Ch], eax
0x18000f6ab  xor     ebp, ebp
0x18000f6ad  mov     r15d, [rsp+78h+arg_30]
0x18000f6b5  mov     ecx, r15d
0x18000f6b8  test    r15d, r15d
0x18000f6bb  jz      short loc_18000F723
0x18000f6bd  sub     ecx, 1
0x18000f6c0  jz      short loc_18000F71A
0x18000f6c2  sub     ecx, 1
0x18000f6c5  jz      short loc_18000F6D5
0x18000f6c7  cmp     ecx, 1
0x18000f6ca  jnz     short loc_18000F72C
0x18000f6cc  mov     ecx, edi; this
0x18000f6ce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000f6d3  jmp     short loc_18000F72A
0x18000f6d5  test    edi, edi
0x18000f6d7  js      short loc_18000F711
0x18000f6d9  mov     edi, 8007029Ch
0x18000f6de  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000f6e2  mov     rax, [rsp+78h+arg_28]
0x18000f6ea  mov     [rsp+78h+var_50], rax; __int64
0x18000f6ef  mov     rax, [rsp+78h+arg_20]
0x18000f6f7  mov     [rsp+78h+var_58], rax; __int64
0x18000f6fc  mov     rcx, r10; int
0x18000f6ff  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000f704  mov     [rbx+8], edi
0x18000f707  mov     ecx, edi; this
0x18000f709  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000f70e  mov     [rbx+0Ch], eax
0x18000f711  mov     ecx, edi; this
0x18000f713  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000f718  jmp     short loc_18000F72A
0x18000f71a  mov     ecx, edi; this
0x18000f71c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000f721  jmp     short loc_18000F72A
0x18000f723  mov     ecx, edi; this
0x18000f725  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000f72a  mov     ebp, eax
0x18000f72c  mov     [rbx], r15d
0x18000f72f  mov     eax, [rsp+78h+arg_70]
0x18000f736  mov     [rbx+4], eax
0x18000f739  cmp     dword ptr [r14+8], 1
0x18000f73e  jnz     short loc_18000F746
0x18000f740  or      eax, 8
0x18000f743  mov     [rbx+4], eax
0x18000f746  mov     eax, 1
0x18000f74b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000f753  inc     eax
0x18000f755  mov     [rbx+10h], eax
0x18000f758  mov     rax, [rsp+78h+arg_40]
0x18000f760  xor     edi, edi
0x18000f762  test    rax, rax
0x18000f765  jz      short loc_18000F76C
0x18000f767  cmp     [rax], di
0x18000f76a  jnz     short loc_18000F76F
0x18000f76c  mov     rax, rdi
0x18000f76f  mov     [rbx+18h], rax
0x18000f773  call    cs:__imp_GetCurrentThreadId
0x18000f779  mov     [rbx+20h], eax
0x18000f77c  mov     [rbx+38h], r13
0x18000f780  mov     eax, [rsp+78h+arg_8]
0x18000f787  mov     [rbx+40h], eax
0x18000f78a  mov     [rbx+44h], ebp
0x18000f78d  mov     rax, [rsp+78h+arg_20]
0x18000f795  mov     [rbx+28h], rax
0x18000f799  mov     [rbx+30h], r12
0x18000f79d  mov     rax, [rsp+78h+arg_28]
0x18000f7a5  mov     [rbx+88h], rax
0x18000f7ac  mov     rax, [rsp+78h+arg_0]
0x18000f7b4  mov     [rbx+90h], rax
0x18000f7bb  mov     [rbx+48h], rdi
0x18000f7bf  xorps   xmm0, xmm0
0x18000f7c2  xor     eax, eax
0x18000f7c4  movups  xmmword ptr [rbx+68h], xmm0
0x18000f7c8  mov     [rbx+78h], rax
0x18000f7cc  movups  xmmword ptr [rbx+50h], xmm0
0x18000f7d0  mov     [rbx+60h], rax
0x18000f7d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000f7db  test    rax, rax
0x18000f7de  jz      short loc_18000F7E7
0x18000f7e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7e5  jmp     short loc_18000F7EA
0x18000f7e7  mov     rax, rdi
0x18000f7ea  mov     [rbx+80h], rax
0x18000f7f1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000f7f8  test    rax, rax
0x18000f7fb  jz      short loc_18000F805
0x18000f7fd  mov     rcx, rbx
0x18000f800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f805  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000f80c  test    rax, rax
0x18000f80f  jz      short loc_18000F827
0x18000f811  mov     r8d, 400h
0x18000f817  mov     rdx, [rsp+78h+arg_60]
0x18000f81f  mov     rcx, rbx
0x18000f822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f827  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f82e  test    rax, rax
0x18000f831  jz      short loc_18000F83B
0x18000f833  mov     rcx, rbx
0x18000f836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f83b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f842  test    rax, rax
0x18000f845  jz      short loc_18000F855
0x18000f847  test    byte ptr [rbx+4], 2
0x18000f84b  jnz     short loc_18000F855
0x18000f84d  mov     rcx, rbx
0x18000f850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f855  cmp     [rbx+8], edi
0x18000f858  jl      short loc_18000F874
0x18000f85a  cmp     r15d, 3
0x18000f85e  jnz     loc_18000F943
0x18000f864  mov     ecx, 8000FFFFh; this
0x18000f869  mov     [rbx+8], ecx
0x18000f86c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000f871  mov     [rbx+0Ch], eax
0x18000f874  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000f87b  jnz     short loc_18000F89C
0x18000f87d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000f884  test    rax, rax
0x18000f887  jz      short loc_18000F892
0x18000f889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f88e  test    al, al
0x18000f890  jmp     short loc_18000F89A
0x18000f892  call    cs:__imp_IsDebuggerPresent
0x18000f898  test    eax, eax
0x18000f89a  jz      short loc_18000F8A2
0x18000f89c  test    byte ptr [rbx+4], 2
0x18000f8a0  jz      short loc_18000F8C6
0x18000f8a2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f8a9  test    rax, rax
0x18000f8ac  jz      short loc_18000F90A
0x18000f8ae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000f8b5  jnz     short loc_18000F90A
0x18000f8b7  xor     r8d, r8d
0x18000f8ba  xor     edx, edx
0x18000f8bc  mov     rcx, rbx
0x18000f8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8c4  jmp     short loc_18000F90A
0x18000f8c6  mov     ebp, 800h
0x18000f8cb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f8d2  test    rax, rax
0x18000f8d5  jz      short loc_18000F8EE
0x18000f8d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000f8de  jnz     short loc_18000F8EE
0x18000f8e0  mov     r8d, ebp
0x18000f8e3  mov     rdx, rsi
0x18000f8e6  mov     rcx, rbx
0x18000f8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ee  cmp     [rsi], di
0x18000f8f1  jnz     short loc_18000F901
0x18000f8f3  mov     r8, rbx; unsigned __int64
0x18000f8f6  mov     rdx, rbp; unsigned __int16 *
0x18000f8f9  mov     rcx, rsi; this
0x18000f8fc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000f901  mov     rcx, rsi; lpOutputString
0x18000f904  call    cs:__imp_OutputDebugStringW
0x18000f90a  test    byte ptr [rbx+4], 4
0x18000f90e  jnz     short loc_18000F919
0x18000f910  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000f917  jz      short loc_18000F92B
0x18000f919  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000f920  test    rax, rax
0x18000f923  jz      short loc_18000F92B
0x18000f925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f92a  nop
0x18000f92b  mov     rbx, [rsp+78h+arg_10]
0x18000f933  add     rsp, 40h
0x18000f937  pop     r15
0x18000f939  pop     r14
0x18000f93b  pop     r13
0x18000f93d  pop     r12
0x18000f93f  pop     rdi
0x18000f940  pop     rsi
0x18000f941  pop     rbp
0x18000f942  retn
0x18000f943  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
