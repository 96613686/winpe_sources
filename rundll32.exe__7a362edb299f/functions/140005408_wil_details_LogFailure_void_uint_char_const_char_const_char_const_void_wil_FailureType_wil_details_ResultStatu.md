# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140005408`
- end: `0x140005700`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400036e0`

## callees

- `0x14000311c`
- `0x140004944`
- `0x140005144`
- `0x140005408`
- `0x140005a4c`
- `0x140005a70`
- `0x140005a84`
- `0x140005aa0`
- `0x140006ce8`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000552b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000552b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000564a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000564a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400056bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400056bc`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x140005408  mov     [rsp+arg_10], rbx
0x14000540d  mov     [rsp+arg_8], edx
0x140005411  mov     [rsp+arg_0], rcx
0x140005416  push    rbp
0x140005417  push    rsi
0x140005418  push    rdi
0x140005419  push    r12
0x14000541b  push    r13
0x14000541d  push    r14
0x14000541f  push    r15
0x140005421  sub     rsp, 40h
0x140005425  mov     r14, [rsp+78h+arg_38]
0x14000542d  xor     eax, eax
0x14000542f  mov     rbx, [rsp+78h+arg_78]
0x140005437  xor     ebp, ebp
0x140005439  mov     r15d, [rsp+78h+arg_30]
0x140005441  mov     r10, rcx
0x140005444  mov     rsi, [rsp+78h+lpOutputString]
0x14000544c  mov     r12, r9
0x14000544f  mov     r13, r8
0x140005452  mov     ecx, r15d
0x140005455  mov     [rsi], ax
0x140005458  mov     rax, [rsp+78h+arg_60]
0x140005460  mov     byte ptr [rax], 0
0x140005463  mov     edi, [r14]
0x140005466  mov     [rbx+8], edi
0x140005469  mov     eax, [r14+4]
0x14000546d  mov     [rbx+0Ch], eax
0x140005470  test    r15d, r15d
0x140005473  jz      short loc_1400054DB
0x140005475  sub     ecx, 1
0x140005478  jz      short loc_1400054D2
0x14000547a  sub     ecx, 1
0x14000547d  jz      short loc_14000548D
0x14000547f  cmp     ecx, 1
0x140005482  jnz     short loc_1400054E4
0x140005484  mov     ecx, edi; this
0x140005486  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000548b  jmp     short loc_1400054E2
0x14000548d  test    edi, edi
0x14000548f  js      short loc_1400054C9
0x140005491  mov     rax, [rsp+78h+arg_28]
0x140005499  mov     edi, 8007029Ch
0x14000549e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400054a2  mov     rcx, r10; int
0x1400054a5  mov     [rsp+78h+var_50], rax; __int64
0x1400054aa  mov     rax, [rsp+78h+arg_20]
0x1400054b2  mov     [rsp+78h+var_58], rax; __int64
0x1400054b7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400054bc  mov     ecx, edi; this
0x1400054be  mov     [rbx+8], edi
0x1400054c1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400054c6  mov     [rbx+0Ch], eax
0x1400054c9  mov     ecx, edi; this
0x1400054cb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400054d0  jmp     short loc_1400054E2
0x1400054d2  mov     ecx, edi; this
0x1400054d4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400054d9  jmp     short loc_1400054E2
0x1400054db  mov     ecx, edi; this
0x1400054dd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400054e2  mov     ebp, eax
0x1400054e4  mov     eax, [rsp+78h+arg_70]
0x1400054eb  mov     [rbx+4], eax
0x1400054ee  mov     [rbx], r15d
0x1400054f1  cmp     dword ptr [r14+8], 1
0x1400054f6  jnz     short loc_1400054FE
0x1400054f8  or      eax, 8
0x1400054fb  mov     [rbx+4], eax
0x1400054fe  mov     eax, 1
0x140005503  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000550b  inc     eax
0x14000550d  xor     edi, edi
0x14000550f  mov     [rbx+10h], eax
0x140005512  mov     rax, [rsp+78h+arg_40]
0x14000551a  test    rax, rax
0x14000551d  jz      short loc_140005524
0x14000551f  cmp     [rax], di
0x140005522  jnz     short loc_140005527
0x140005524  mov     rax, rdi
0x140005527  mov     [rbx+18h], rax
0x14000552b  call    cs:__imp_GetCurrentThreadId
0x140005531  mov     [rbx+38h], r13
0x140005535  xorps   xmm0, xmm0
0x140005538  mov     [rbx+20h], eax
0x14000553b  mov     eax, [rsp+78h+arg_8]
0x140005542  mov     [rbx+40h], eax
0x140005545  mov     rax, [rsp+78h+arg_20]
0x14000554d  mov     [rbx+28h], rax
0x140005551  mov     rax, [rsp+78h+arg_28]
0x140005559  mov     [rbx+88h], rax
0x140005560  mov     rax, [rsp+78h+arg_0]
0x140005568  mov     [rbx+90h], rax
0x14000556f  xor     eax, eax
0x140005571  mov     [rbx+44h], ebp
0x140005574  mov     [rbx+30h], r12
0x140005578  mov     [rbx+48h], rdi
0x14000557c  movups  xmmword ptr [rbx+68h], xmm0
0x140005580  mov     [rbx+78h], rax
0x140005584  movups  xmmword ptr [rbx+50h], xmm0
0x140005588  mov     [rbx+60h], rax
0x14000558c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005593  test    rax, rax
0x140005596  jz      short loc_14000559F
0x140005598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000559d  jmp     short loc_1400055A2
0x14000559f  mov     rax, rdi
0x1400055a2  mov     [rbx+80h], rax
0x1400055a9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400055b0  test    rax, rax
0x1400055b3  jz      short loc_1400055BD
0x1400055b5  mov     rcx, rbx
0x1400055b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055bd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400055c4  test    rax, rax
0x1400055c7  jz      short loc_1400055DF
0x1400055c9  mov     rdx, [rsp+78h+arg_60]
0x1400055d1  mov     r8d, 400h
0x1400055d7  mov     rcx, rbx
0x1400055da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055df  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400055e6  test    rax, rax
0x1400055e9  jz      short loc_1400055F3
0x1400055eb  mov     rcx, rbx
0x1400055ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055f3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400055fa  test    rax, rax
0x1400055fd  jz      short loc_14000560D
0x1400055ff  test    byte ptr [rbx+4], 2
0x140005603  jnz     short loc_14000560D
0x140005605  mov     rcx, rbx
0x140005608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000560d  cmp     [rbx+8], edi
0x140005610  jl      short loc_14000562C
0x140005612  cmp     r15d, 3
0x140005616  jnz     loc_1400056FA
0x14000561c  mov     ecx, 8000FFFFh; this
0x140005621  mov     [rbx+8], ecx
0x140005624  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005629  mov     [rbx+0Ch], eax
0x14000562c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005633  jnz     short loc_140005654
0x140005635  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000563c  test    rax, rax
0x14000563f  jz      short loc_14000564A
0x140005641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005646  test    al, al
0x140005648  jmp     short loc_140005652
0x14000564a  call    cs:__imp_IsDebuggerPresent
0x140005650  test    eax, eax
0x140005652  jz      short loc_14000565A
0x140005654  test    byte ptr [rbx+4], 2
0x140005658  jz      short loc_14000567E
0x14000565a  mov     rax, cs:g_pfnResultLoggingCallback
0x140005661  test    rax, rax
0x140005664  jz      short loc_1400056C2
0x140005666  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000566d  jnz     short loc_1400056C2
0x14000566f  xor     r8d, r8d
0x140005672  xor     edx, edx
0x140005674  mov     rcx, rbx
0x140005677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000567c  jmp     short loc_1400056C2
0x14000567e  mov     rax, cs:g_pfnResultLoggingCallback
0x140005685  mov     ebp, 800h
0x14000568a  test    rax, rax
0x14000568d  jz      short loc_1400056A6
0x14000568f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005696  jnz     short loc_1400056A6
0x140005698  mov     r8d, ebp
0x14000569b  mov     rdx, rsi
0x14000569e  mov     rcx, rbx
0x1400056a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056a6  cmp     [rsi], di
0x1400056a9  jnz     short loc_1400056B9
0x1400056ab  mov     r8, rbx; unsigned __int64
0x1400056ae  mov     rdx, rbp; unsigned __int16 *
0x1400056b1  mov     rcx, rsi; this
0x1400056b4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400056b9  mov     rcx, rsi; lpOutputString
0x1400056bc  call    cs:__imp_OutputDebugStringW
0x1400056c2  test    byte ptr [rbx+4], 4
0x1400056c6  jnz     short loc_1400056D1
0x1400056c8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400056cf  jz      short loc_1400056E2
0x1400056d1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400056d8  test    rax, rax
0x1400056db  jz      short loc_1400056E2
0x1400056dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056e2  mov     rbx, [rsp+78h+arg_10]
0x1400056ea  add     rsp, 40h
0x1400056ee  pop     r15
0x1400056f0  pop     r14
0x1400056f2  pop     r13
0x1400056f4  pop     r12
0x1400056f6  pop     rdi
0x1400056f7  pop     rsi
0x1400056f8  pop     rbp
0x1400056f9  retn
0x1400056fa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
