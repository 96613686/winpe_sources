# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800862d8`
- end: `0x1800865d0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180084924`
- `0x180084c74`

## callees

- `0x180077c68`
- `0x180078160`
- `0x180078b10`
- `0x18008486c`
- `0x1800862d8`
- `0x1800867c4`
- `0x1800867e0`
- `0x1800867fc`
- `0x1800877f8`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800863fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800863fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18008658c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18008658c`
- `KERNEL32!IsDebuggerPresent` at `0x18008651a`
- `KERNEL32!IsDebuggerPresent` at `0x18008651a`

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
0x1800862d8  mov     [rsp+arg_10], rbx
0x1800862dd  mov     [rsp+arg_8], edx
0x1800862e1  mov     [rsp+arg_0], rcx
0x1800862e6  push    rbp
0x1800862e7  push    rsi
0x1800862e8  push    rdi
0x1800862e9  push    r12
0x1800862eb  push    r13
0x1800862ed  push    r14
0x1800862ef  push    r15
0x1800862f1  sub     rsp, 40h
0x1800862f5  mov     r14, [rsp+78h+arg_38]
0x1800862fd  xor     eax, eax
0x1800862ff  mov     rbx, [rsp+78h+arg_78]
0x180086307  xor     ebp, ebp
0x180086309  mov     r15d, [rsp+78h+arg_30]
0x180086311  mov     r10, rcx
0x180086314  mov     rsi, [rsp+78h+lpOutputString]
0x18008631c  mov     r12, r9
0x18008631f  mov     r13, r8
0x180086322  mov     ecx, r15d
0x180086325  mov     [rsi], ax
0x180086328  mov     rax, [rsp+78h+arg_60]
0x180086330  mov     byte ptr [rax], 0
0x180086333  mov     edi, [r14]
0x180086336  mov     [rbx+8], edi
0x180086339  mov     eax, [r14+4]
0x18008633d  mov     [rbx+0Ch], eax
0x180086340  test    r15d, r15d
0x180086343  jz      short loc_1800863AB
0x180086345  sub     ecx, 1
0x180086348  jz      short loc_1800863A2
0x18008634a  sub     ecx, 1
0x18008634d  jz      short loc_18008635D
0x18008634f  cmp     ecx, 1
0x180086352  jnz     short loc_1800863B4
0x180086354  mov     ecx, edi; this
0x180086356  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18008635b  jmp     short loc_1800863B2
0x18008635d  test    edi, edi
0x18008635f  js      short loc_180086399
0x180086361  mov     rax, [rsp+78h+arg_28]
0x180086369  mov     edi, 8007029Ch
0x18008636e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180086372  mov     rcx, r10; int
0x180086375  mov     [rsp+78h+var_50], rax; __int64
0x18008637a  mov     rax, [rsp+78h+arg_20]
0x180086382  mov     [rsp+78h+var_58], rax; __int64
0x180086387  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18008638c  mov     ecx, edi; this
0x18008638e  mov     [rbx+8], edi
0x180086391  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180086396  mov     [rbx+0Ch], eax
0x180086399  mov     ecx, edi; this
0x18008639b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800863a0  jmp     short loc_1800863B2
0x1800863a2  mov     ecx, edi; this
0x1800863a4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800863a9  jmp     short loc_1800863B2
0x1800863ab  mov     ecx, edi; this
0x1800863ad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800863b2  mov     ebp, eax
0x1800863b4  mov     eax, [rsp+78h+arg_70]
0x1800863bb  mov     [rbx+4], eax
0x1800863be  mov     [rbx], r15d
0x1800863c1  cmp     dword ptr [r14+8], 1
0x1800863c6  jnz     short loc_1800863CE
0x1800863c8  or      eax, 8
0x1800863cb  mov     [rbx+4], eax
0x1800863ce  mov     eax, 1
0x1800863d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800863db  inc     eax
0x1800863dd  xor     edi, edi
0x1800863df  mov     [rbx+10h], eax
0x1800863e2  mov     rax, [rsp+78h+arg_40]
0x1800863ea  test    rax, rax
0x1800863ed  jz      short loc_1800863F4
0x1800863ef  cmp     [rax], di
0x1800863f2  jnz     short loc_1800863F7
0x1800863f4  mov     rax, rdi
0x1800863f7  mov     [rbx+18h], rax
0x1800863fb  call    cs:__imp_GetCurrentThreadId
0x180086401  mov     [rbx+38h], r13
0x180086405  xorps   xmm0, xmm0
0x180086408  mov     [rbx+20h], eax
0x18008640b  mov     eax, [rsp+78h+arg_8]
0x180086412  mov     [rbx+40h], eax
0x180086415  mov     rax, [rsp+78h+arg_20]
0x18008641d  mov     [rbx+28h], rax
0x180086421  mov     rax, [rsp+78h+arg_28]
0x180086429  mov     [rbx+88h], rax
0x180086430  mov     rax, [rsp+78h+arg_0]
0x180086438  mov     [rbx+90h], rax
0x18008643f  xor     eax, eax
0x180086441  mov     [rbx+44h], ebp
0x180086444  mov     [rbx+30h], r12
0x180086448  mov     [rbx+48h], rdi
0x18008644c  movups  xmmword ptr [rbx+68h], xmm0
0x180086450  mov     [rbx+78h], rax
0x180086454  movups  xmmword ptr [rbx+50h], xmm0
0x180086458  mov     [rbx+60h], rax
0x18008645c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180086463  test    rax, rax
0x180086466  jz      short loc_18008646F
0x180086468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008646d  jmp     short loc_180086472
0x18008646f  mov     rax, rdi
0x180086472  mov     [rbx+80h], rax
0x180086479  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180086480  test    rax, rax
0x180086483  jz      short loc_18008648D
0x180086485  mov     rcx, rbx
0x180086488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008648d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180086494  test    rax, rax
0x180086497  jz      short loc_1800864AF
0x180086499  mov     rdx, [rsp+78h+arg_60]
0x1800864a1  mov     r8d, 400h
0x1800864a7  mov     rcx, rbx
0x1800864aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800864af  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800864b6  test    rax, rax
0x1800864b9  jz      short loc_1800864C3
0x1800864bb  mov     rcx, rbx
0x1800864be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800864c3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800864ca  test    rax, rax
0x1800864cd  jz      short loc_1800864DD
0x1800864cf  test    byte ptr [rbx+4], 2
0x1800864d3  jnz     short loc_1800864DD
0x1800864d5  mov     rcx, rbx
0x1800864d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800864dd  cmp     [rbx+8], edi
0x1800864e0  jl      short loc_1800864FC
0x1800864e2  cmp     r15d, 3
0x1800864e6  jnz     loc_1800865CA
0x1800864ec  mov     ecx, 8000FFFFh; this
0x1800864f1  mov     [rbx+8], ecx
0x1800864f4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800864f9  mov     [rbx+0Ch], eax
0x1800864fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180086503  jnz     short loc_180086524
0x180086505  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18008650c  test    rax, rax
0x18008650f  jz      short loc_18008651A
0x180086511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086516  test    al, al
0x180086518  jmp     short loc_180086522
0x18008651a  call    cs:__imp_IsDebuggerPresent
0x180086520  test    eax, eax
0x180086522  jz      short loc_18008652A
0x180086524  test    byte ptr [rbx+4], 2
0x180086528  jz      short loc_18008654E
0x18008652a  mov     rax, cs:g_pfnResultLoggingCallback
0x180086531  test    rax, rax
0x180086534  jz      short loc_180086592
0x180086536  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18008653d  jnz     short loc_180086592
0x18008653f  xor     r8d, r8d
0x180086542  xor     edx, edx
0x180086544  mov     rcx, rbx
0x180086547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008654c  jmp     short loc_180086592
0x18008654e  mov     rax, cs:g_pfnResultLoggingCallback
0x180086555  mov     ebp, 800h
0x18008655a  test    rax, rax
0x18008655d  jz      short loc_180086576
0x18008655f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180086566  jnz     short loc_180086576
0x180086568  mov     r8d, ebp
0x18008656b  mov     rdx, rsi
0x18008656e  mov     rcx, rbx
0x180086571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086576  cmp     [rsi], di
0x180086579  jnz     short loc_180086589
0x18008657b  mov     r8, rbx; unsigned __int64
0x18008657e  mov     rdx, rbp; unsigned __int16 *
0x180086581  mov     rcx, rsi; this
0x180086584  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180086589  mov     rcx, rsi; lpOutputString
0x18008658c  call    cs:__imp_OutputDebugStringW
0x180086592  test    byte ptr [rbx+4], 4
0x180086596  jnz     short loc_1800865A1
0x180086598  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18008659f  jz      short loc_1800865B2
0x1800865a1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800865a8  test    rax, rax
0x1800865ab  jz      short loc_1800865B2
0x1800865ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800865b2  mov     rbx, [rsp+78h+arg_10]
0x1800865ba  add     rsp, 40h
0x1800865be  pop     r15
0x1800865c0  pop     r14
0x1800865c2  pop     r13
0x1800865c4  pop     r12
0x1800865c6  pop     rdi
0x1800865c7  pop     rsi
0x1800865c8  pop     rbp
0x1800865c9  retn
0x1800865ca  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
