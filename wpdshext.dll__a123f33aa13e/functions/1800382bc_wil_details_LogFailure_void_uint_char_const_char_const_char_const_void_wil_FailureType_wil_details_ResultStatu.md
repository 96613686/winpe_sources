# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800382bc`
- end: `0x1800385b5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180037038`
- `0x18003737c`

## callees

- `0x1800299e8`
- `0x180036f78`
- `0x180037bd4`
- `0x1800382bc`
- `0x180038658`
- `0x180038680`
- `0x180038694`
- `0x1800386b0`
- `0x180038e64`
- `0x180078010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180038570`
- `KERNEL32!OutputDebugStringW` at `0x180038570`
- `KERNEL32!IsDebuggerPresent` at `0x1800384fe`
- `KERNEL32!IsDebuggerPresent` at `0x1800384fe`
- `KERNEL32!GetCurrentThreadId` at `0x1800383df`
- `KERNEL32!GetCurrentThreadId` at `0x1800383df`

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
0x1800382bc  mov     [rsp+arg_10], rbx
0x1800382c1  mov     [rsp+arg_8], edx
0x1800382c5  mov     [rsp+arg_0], rcx
0x1800382ca  push    rbp
0x1800382cb  push    rsi
0x1800382cc  push    rdi
0x1800382cd  push    r12
0x1800382cf  push    r13
0x1800382d1  push    r14
0x1800382d3  push    r15
0x1800382d5  sub     rsp, 40h
0x1800382d9  mov     r12, r9
0x1800382dc  mov     r13, r8
0x1800382df  mov     r10, rcx
0x1800382e2  xor     eax, eax
0x1800382e4  mov     rsi, [rsp+78h+lpOutputString]
0x1800382ec  mov     [rsi], ax
0x1800382ef  mov     rax, [rsp+78h+arg_60]
0x1800382f7  mov     byte ptr [rax], 0
0x1800382fa  mov     r14, [rsp+78h+arg_38]
0x180038302  mov     edi, [r14]
0x180038305  mov     rbx, [rsp+78h+arg_78]
0x18003830d  mov     [rbx+8], edi
0x180038310  mov     eax, [r14+4]
0x180038314  mov     [rbx+0Ch], eax
0x180038317  xor     ebp, ebp
0x180038319  mov     r15d, [rsp+78h+arg_30]
0x180038321  mov     ecx, r15d
0x180038324  test    r15d, r15d
0x180038327  jz      short loc_18003838F
0x180038329  sub     ecx, 1
0x18003832c  jz      short loc_180038386
0x18003832e  sub     ecx, 1
0x180038331  jz      short loc_180038341
0x180038333  cmp     ecx, 1
0x180038336  jnz     short loc_180038398
0x180038338  mov     ecx, edi; this
0x18003833a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003833f  jmp     short loc_180038396
0x180038341  test    edi, edi
0x180038343  js      short loc_18003837D
0x180038345  mov     edi, 8007029Ch
0x18003834a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003834e  mov     rax, [rsp+78h+arg_28]
0x180038356  mov     [rsp+78h+var_50], rax; __int64
0x18003835b  mov     rax, [rsp+78h+arg_20]
0x180038363  mov     [rsp+78h+var_58], rax; __int64
0x180038368  mov     rcx, r10; int
0x18003836b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180038370  mov     [rbx+8], edi
0x180038373  mov     ecx, edi; this
0x180038375  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003837a  mov     [rbx+0Ch], eax
0x18003837d  mov     ecx, edi; this
0x18003837f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180038384  jmp     short loc_180038396
0x180038386  mov     ecx, edi; this
0x180038388  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003838d  jmp     short loc_180038396
0x18003838f  mov     ecx, edi; this
0x180038391  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180038396  mov     ebp, eax
0x180038398  mov     [rbx], r15d
0x18003839b  mov     eax, [rsp+78h+arg_70]
0x1800383a2  mov     [rbx+4], eax
0x1800383a5  cmp     dword ptr [r14+8], 1
0x1800383aa  jnz     short loc_1800383B2
0x1800383ac  or      eax, 8
0x1800383af  mov     [rbx+4], eax
0x1800383b2  mov     eax, 1
0x1800383b7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800383bf  inc     eax
0x1800383c1  mov     [rbx+10h], eax
0x1800383c4  mov     rax, [rsp+78h+arg_40]
0x1800383cc  xor     edi, edi
0x1800383ce  test    rax, rax
0x1800383d1  jz      short loc_1800383D8
0x1800383d3  cmp     [rax], di
0x1800383d6  jnz     short loc_1800383DB
0x1800383d8  mov     rax, rdi
0x1800383db  mov     [rbx+18h], rax
0x1800383df  call    cs:__imp_GetCurrentThreadId
0x1800383e5  mov     [rbx+20h], eax
0x1800383e8  mov     [rbx+38h], r13
0x1800383ec  mov     eax, [rsp+78h+arg_8]
0x1800383f3  mov     [rbx+40h], eax
0x1800383f6  mov     [rbx+44h], ebp
0x1800383f9  mov     rax, [rsp+78h+arg_20]
0x180038401  mov     [rbx+28h], rax
0x180038405  mov     [rbx+30h], r12
0x180038409  mov     rax, [rsp+78h+arg_28]
0x180038411  mov     [rbx+88h], rax
0x180038418  mov     rax, [rsp+78h+arg_0]
0x180038420  mov     [rbx+90h], rax
0x180038427  mov     [rbx+48h], rdi
0x18003842b  xorps   xmm0, xmm0
0x18003842e  xor     eax, eax
0x180038430  movups  xmmword ptr [rbx+68h], xmm0
0x180038434  mov     [rbx+78h], rax
0x180038438  movups  xmmword ptr [rbx+50h], xmm0
0x18003843c  mov     [rbx+60h], rax
0x180038440  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180038447  test    rax, rax
0x18003844a  jz      short loc_180038453
0x18003844c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038451  jmp     short loc_180038456
0x180038453  mov     rax, rdi
0x180038456  mov     [rbx+80h], rax
0x18003845d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180038464  test    rax, rax
0x180038467  jz      short loc_180038471
0x180038469  mov     rcx, rbx
0x18003846c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038471  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180038478  test    rax, rax
0x18003847b  jz      short loc_180038493
0x18003847d  mov     r8d, 400h
0x180038483  mov     rdx, [rsp+78h+arg_60]
0x18003848b  mov     rcx, rbx
0x18003848e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038493  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003849a  test    rax, rax
0x18003849d  jz      short loc_1800384A7
0x18003849f  mov     rcx, rbx
0x1800384a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384a7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800384ae  test    rax, rax
0x1800384b1  jz      short loc_1800384C1
0x1800384b3  test    byte ptr [rbx+4], 2
0x1800384b7  jnz     short loc_1800384C1
0x1800384b9  mov     rcx, rbx
0x1800384bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384c1  cmp     [rbx+8], edi
0x1800384c4  jl      short loc_1800384E0
0x1800384c6  cmp     r15d, 3
0x1800384ca  jnz     loc_1800385AF
0x1800384d0  mov     ecx, 8000FFFFh; this
0x1800384d5  mov     [rbx+8], ecx
0x1800384d8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800384dd  mov     [rbx+0Ch], eax
0x1800384e0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800384e7  jnz     short loc_180038508
0x1800384e9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800384f0  test    rax, rax
0x1800384f3  jz      short loc_1800384FE
0x1800384f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384fa  test    al, al
0x1800384fc  jmp     short loc_180038506
0x1800384fe  call    cs:__imp_IsDebuggerPresent
0x180038504  test    eax, eax
0x180038506  jz      short loc_18003850E
0x180038508  test    byte ptr [rbx+4], 2
0x18003850c  jz      short loc_180038532
0x18003850e  mov     rax, cs:g_pfnResultLoggingCallback
0x180038515  test    rax, rax
0x180038518  jz      short loc_180038576
0x18003851a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180038521  jnz     short loc_180038576
0x180038523  xor     r8d, r8d
0x180038526  xor     edx, edx
0x180038528  mov     rcx, rbx
0x18003852b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038530  jmp     short loc_180038576
0x180038532  mov     ebp, 800h
0x180038537  mov     rax, cs:g_pfnResultLoggingCallback
0x18003853e  test    rax, rax
0x180038541  jz      short loc_18003855A
0x180038543  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003854a  jnz     short loc_18003855A
0x18003854c  mov     r8d, ebp
0x18003854f  mov     rdx, rsi
0x180038552  mov     rcx, rbx
0x180038555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003855a  cmp     [rsi], di
0x18003855d  jnz     short loc_18003856D
0x18003855f  mov     r8, rbx; unsigned __int64
0x180038562  mov     rdx, rbp; unsigned __int16 *
0x180038565  mov     rcx, rsi; this
0x180038568  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003856d  mov     rcx, rsi; lpOutputString
0x180038570  call    cs:__imp_OutputDebugStringW
0x180038576  test    byte ptr [rbx+4], 4
0x18003857a  jnz     short loc_180038585
0x18003857c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180038583  jz      short loc_180038597
0x180038585  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003858c  test    rax, rax
0x18003858f  jz      short loc_180038597
0x180038591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038596  nop
0x180038597  mov     rbx, [rsp+78h+arg_10]
0x18003859f  add     rsp, 40h
0x1800385a3  pop     r15
0x1800385a5  pop     r14
0x1800385a7  pop     r13
0x1800385a9  pop     r12
0x1800385ab  pop     rdi
0x1800385ac  pop     rsi
0x1800385ad  pop     rbp
0x1800385ae  retn
0x1800385af  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
