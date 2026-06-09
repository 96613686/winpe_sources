# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004538`
- end: `0x18000482d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180002e2c`
- `0x180002eec`
- `0x180002fe8`
- `0x180008118`

## callees

- `0x180002d74`
- `0x180003bd4`
- `0x180004374`
- `0x180004538`
- `0x180004c90`
- `0x180004cb0`
- `0x180004cc4`
- `0x180004ce0`
- `0x1800059ac`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000465b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000465b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800047ee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800047ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000477c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000477c`

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
0x180004538  mov     [rsp+arg_10], rbx
0x18000453d  mov     [rsp+arg_8], edx
0x180004541  mov     [rsp+arg_0], rcx
0x180004546  push    rbp
0x180004547  push    rsi
0x180004548  push    rdi
0x180004549  push    r12
0x18000454b  push    r13
0x18000454d  push    r14
0x18000454f  push    r15
0x180004551  sub     rsp, 40h
0x180004555  mov     r12, r9
0x180004558  mov     r13, r8
0x18000455b  mov     r10, rcx
0x18000455e  xor     eax, eax
0x180004560  mov     rsi, [rsp+78h+lpOutputString]
0x180004568  mov     [rsi], ax
0x18000456b  mov     rax, [rsp+78h+arg_60]
0x180004573  mov     byte ptr [rax], 0
0x180004576  mov     r14, [rsp+78h+arg_38]
0x18000457e  mov     edi, [r14]
0x180004581  mov     rbx, [rsp+78h+arg_78]
0x180004589  mov     [rbx+8], edi
0x18000458c  mov     eax, [r14+4]
0x180004590  mov     [rbx+0Ch], eax
0x180004593  xor     ebp, ebp
0x180004595  mov     r15d, [rsp+78h+arg_30]
0x18000459d  mov     ecx, r15d
0x1800045a0  test    r15d, r15d
0x1800045a3  jz      short loc_18000460B
0x1800045a5  sub     ecx, 1
0x1800045a8  jz      short loc_180004602
0x1800045aa  sub     ecx, 1
0x1800045ad  jz      short loc_1800045BD
0x1800045af  cmp     ecx, 1
0x1800045b2  jnz     short loc_180004614
0x1800045b4  mov     ecx, edi; this
0x1800045b6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800045bb  jmp     short loc_180004612
0x1800045bd  test    edi, edi
0x1800045bf  js      short loc_1800045F9
0x1800045c1  mov     edi, 8007029Ch
0x1800045c6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800045ca  mov     rax, [rsp+78h+arg_28]
0x1800045d2  mov     [rsp+78h+var_50], rax; __int64
0x1800045d7  mov     rax, [rsp+78h+arg_20]
0x1800045df  mov     [rsp+78h+var_58], rax; __int64
0x1800045e4  mov     rcx, r10; int
0x1800045e7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800045ec  mov     [rbx+8], edi
0x1800045ef  mov     ecx, edi; this
0x1800045f1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800045f6  mov     [rbx+0Ch], eax
0x1800045f9  mov     ecx, edi; this
0x1800045fb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004600  jmp     short loc_180004612
0x180004602  mov     ecx, edi; this
0x180004604  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004609  jmp     short loc_180004612
0x18000460b  mov     ecx, edi; this
0x18000460d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004612  mov     ebp, eax
0x180004614  mov     [rbx], r15d
0x180004617  mov     eax, [rsp+78h+arg_70]
0x18000461e  mov     [rbx+4], eax
0x180004621  cmp     dword ptr [r14+8], 1
0x180004626  jnz     short loc_18000462E
0x180004628  or      eax, 8
0x18000462b  mov     [rbx+4], eax
0x18000462e  mov     eax, 1
0x180004633  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000463b  inc     eax
0x18000463d  mov     [rbx+10h], eax
0x180004640  mov     rax, [rsp+78h+arg_40]
0x180004648  xor     edi, edi
0x18000464a  test    rax, rax
0x18000464d  jz      short loc_180004654
0x18000464f  cmp     [rax], di
0x180004652  jnz     short loc_180004657
0x180004654  mov     rax, rdi
0x180004657  mov     [rbx+18h], rax
0x18000465b  call    cs:__imp_GetCurrentThreadId
0x180004661  mov     [rbx+20h], eax
0x180004664  mov     [rbx+38h], r13
0x180004668  mov     eax, [rsp+78h+arg_8]
0x18000466f  mov     [rbx+40h], eax
0x180004672  mov     [rbx+44h], ebp
0x180004675  mov     rax, [rsp+78h+arg_20]
0x18000467d  mov     [rbx+28h], rax
0x180004681  mov     [rbx+30h], r12
0x180004685  mov     rax, [rsp+78h+arg_28]
0x18000468d  mov     [rbx+88h], rax
0x180004694  mov     rax, [rsp+78h+arg_0]
0x18000469c  mov     [rbx+90h], rax
0x1800046a3  mov     [rbx+48h], rdi
0x1800046a7  xorps   xmm0, xmm0
0x1800046aa  xor     eax, eax
0x1800046ac  movups  xmmword ptr [rbx+68h], xmm0
0x1800046b0  mov     [rbx+78h], rax
0x1800046b4  movups  xmmword ptr [rbx+50h], xmm0
0x1800046b8  mov     [rbx+60h], rax
0x1800046bc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800046c3  test    rax, rax
0x1800046c6  jz      short loc_1800046CF
0x1800046c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046cd  jmp     short loc_1800046D2
0x1800046cf  mov     rax, rdi
0x1800046d2  mov     [rbx+80h], rax
0x1800046d9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800046e0  test    rax, rax
0x1800046e3  jz      short loc_1800046ED
0x1800046e5  mov     rcx, rbx
0x1800046e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800046f4  test    rax, rax
0x1800046f7  jz      short loc_18000470F
0x1800046f9  mov     r8d, 400h
0x1800046ff  mov     rdx, [rsp+78h+arg_60]
0x180004707  mov     rcx, rbx
0x18000470a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000470f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004716  test    rax, rax
0x180004719  jz      short loc_180004723
0x18000471b  mov     rcx, rbx
0x18000471e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004723  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000472a  test    rax, rax
0x18000472d  jz      short loc_18000473D
0x18000472f  test    byte ptr [rbx+4], 2
0x180004733  jnz     short loc_18000473D
0x180004735  mov     rcx, rbx
0x180004738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473d  cmp     [rbx+8], edi
0x180004740  jl      short loc_18000475E
0x180004742  cmp     r15d, 3
0x180004746  jz      short loc_18000474E
0x180004748  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000474e  mov     ecx, 8000FFFFh; this
0x180004753  mov     [rbx+8], ecx
0x180004756  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000475b  mov     [rbx+0Ch], eax
0x18000475e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004765  jnz     short loc_180004786
0x180004767  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000476e  test    rax, rax
0x180004771  jz      short loc_18000477C
0x180004773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004778  test    al, al
0x18000477a  jmp     short loc_180004784
0x18000477c  call    cs:__imp_IsDebuggerPresent
0x180004782  test    eax, eax
0x180004784  jz      short loc_18000478C
0x180004786  test    byte ptr [rbx+4], 2
0x18000478a  jz      short loc_1800047B0
0x18000478c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004793  test    rax, rax
0x180004796  jz      short loc_1800047F4
0x180004798  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000479f  jnz     short loc_1800047F4
0x1800047a1  xor     r8d, r8d
0x1800047a4  xor     edx, edx
0x1800047a6  mov     rcx, rbx
0x1800047a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ae  jmp     short loc_1800047F4
0x1800047b0  mov     ebp, 800h
0x1800047b5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800047bc  test    rax, rax
0x1800047bf  jz      short loc_1800047D8
0x1800047c1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800047c8  jnz     short loc_1800047D8
0x1800047ca  mov     r8d, ebp
0x1800047cd  mov     rdx, rsi
0x1800047d0  mov     rcx, rbx
0x1800047d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047d8  cmp     [rsi], di
0x1800047db  jnz     short loc_1800047EB
0x1800047dd  mov     r8, rbx; unsigned __int64
0x1800047e0  mov     rdx, rbp; unsigned __int16 *
0x1800047e3  mov     rcx, rsi; this
0x1800047e6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800047eb  mov     rcx, rsi; lpOutputString
0x1800047ee  call    cs:__imp_OutputDebugStringW
0x1800047f4  test    byte ptr [rbx+4], 4
0x1800047f8  jnz     short loc_180004803
0x1800047fa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004801  jz      short loc_180004815
0x180004803  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000480a  test    rax, rax
0x18000480d  jz      short loc_180004815
0x18000480f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004814  nop
0x180004815  mov     rbx, [rsp+78h+arg_10]
0x18000481d  add     rsp, 40h
0x180004821  pop     r15
0x180004823  pop     r14
0x180004825  pop     r13
0x180004827  pop     r12
0x180004829  pop     rdi
0x18000482a  pop     rsi
0x18000482b  pop     rbp
0x18000482c  retn
```
