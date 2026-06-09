# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180016380`
- end: `0x180016674`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18001628c`
- `0x18001dc2c`
- `0x18001dcdc`

## callees

- `0x1800155b4`
- `0x180016380`
- `0x180016680`
- `0x18001db80`
- `0x18001e4f4`
- `0x18001f01c`
- `0x18001f0e0`
- `0x18001f0fc`
- `0x18001f8ac`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800164a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800164a3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800165c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800165c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016636`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016636`

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
0x180016380  mov     [rsp+arg_10], rbx
0x180016385  mov     [rsp+arg_8], edx
0x180016389  mov     [rsp+arg_0], rcx
0x18001638e  push    rbp
0x18001638f  push    rsi
0x180016390  push    rdi
0x180016391  push    r12
0x180016393  push    r13
0x180016395  push    r14
0x180016397  push    r15
0x180016399  sub     rsp, 40h
0x18001639d  mov     r14, [rsp+78h+arg_38]
0x1800163a5  xor     eax, eax
0x1800163a7  mov     rbx, [rsp+78h+arg_78]
0x1800163af  xor     ebp, ebp
0x1800163b1  mov     r15d, [rsp+78h+arg_30]
0x1800163b9  mov     r10, rcx
0x1800163bc  mov     rsi, [rsp+78h+lpOutputString]
0x1800163c4  mov     r12, r9
0x1800163c7  mov     r13, r8
0x1800163ca  mov     ecx, r15d
0x1800163cd  mov     [rsi], ax
0x1800163d0  mov     rax, [rsp+78h+arg_60]
0x1800163d8  mov     byte ptr [rax], 0
0x1800163db  mov     edi, [r14]
0x1800163de  mov     [rbx+8], edi
0x1800163e1  mov     eax, [r14+4]
0x1800163e5  mov     [rbx+0Ch], eax
0x1800163e8  test    r15d, r15d
0x1800163eb  jz      short loc_180016453
0x1800163ed  sub     ecx, 1
0x1800163f0  jz      short loc_18001644A
0x1800163f2  sub     ecx, 1
0x1800163f5  jz      short loc_180016405
0x1800163f7  cmp     ecx, 1
0x1800163fa  jnz     short loc_18001645C
0x1800163fc  mov     ecx, edi; this
0x1800163fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180016403  jmp     short loc_18001645A
0x180016405  test    edi, edi
0x180016407  js      short loc_180016441
0x180016409  mov     rax, [rsp+78h+arg_28]
0x180016411  mov     edi, 8007029Ch
0x180016416  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001641a  mov     rcx, r10; int
0x18001641d  mov     [rsp+78h+var_50], rax; __int64
0x180016422  mov     rax, [rsp+78h+arg_20]
0x18001642a  mov     [rsp+78h+var_58], rax; __int64
0x18001642f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180016434  mov     ecx, edi; this
0x180016436  mov     [rbx+8], edi
0x180016439  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001643e  mov     [rbx+0Ch], eax
0x180016441  mov     ecx, edi; this
0x180016443  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180016448  jmp     short loc_18001645A
0x18001644a  mov     ecx, edi; this
0x18001644c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180016451  jmp     short loc_18001645A
0x180016453  mov     ecx, edi; this
0x180016455  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001645a  mov     ebp, eax
0x18001645c  mov     eax, [rsp+78h+arg_70]
0x180016463  mov     [rbx+4], eax
0x180016466  mov     [rbx], r15d
0x180016469  cmp     dword ptr [r14+8], 1
0x18001646e  jnz     short loc_180016476
0x180016470  or      eax, 8
0x180016473  mov     [rbx+4], eax
0x180016476  mov     eax, 1
0x18001647b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016483  inc     eax
0x180016485  xor     edi, edi
0x180016487  mov     [rbx+10h], eax
0x18001648a  mov     rax, [rsp+78h+arg_40]
0x180016492  test    rax, rax
0x180016495  jz      short loc_18001649C
0x180016497  cmp     [rax], di
0x18001649a  jnz     short loc_18001649F
0x18001649c  mov     rax, rdi
0x18001649f  mov     [rbx+18h], rax
0x1800164a3  call    cs:__imp_GetCurrentThreadId
0x1800164a9  mov     [rbx+38h], r13
0x1800164ad  xorps   xmm0, xmm0
0x1800164b0  mov     [rbx+20h], eax
0x1800164b3  mov     eax, [rsp+78h+arg_8]
0x1800164ba  mov     [rbx+40h], eax
0x1800164bd  mov     rax, [rsp+78h+arg_20]
0x1800164c5  mov     [rbx+28h], rax
0x1800164c9  mov     rax, [rsp+78h+arg_28]
0x1800164d1  mov     [rbx+88h], rax
0x1800164d8  mov     rax, [rsp+78h+arg_0]
0x1800164e0  mov     [rbx+90h], rax
0x1800164e7  xor     eax, eax
0x1800164e9  mov     [rbx+44h], ebp
0x1800164ec  mov     [rbx+30h], r12
0x1800164f0  mov     [rbx+48h], rdi
0x1800164f4  movups  xmmword ptr [rbx+68h], xmm0
0x1800164f8  mov     [rbx+78h], rax
0x1800164fc  movups  xmmword ptr [rbx+50h], xmm0
0x180016500  mov     [rbx+60h], rax
0x180016504  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001650b  test    rax, rax
0x18001650e  jz      short loc_180016517
0x180016510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016515  jmp     short loc_18001651A
0x180016517  mov     rax, rdi
0x18001651a  mov     [rbx+80h], rax
0x180016521  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180016528  test    rax, rax
0x18001652b  jz      short loc_180016535
0x18001652d  mov     rcx, rbx
0x180016530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016535  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001653c  test    rax, rax
0x18001653f  jz      short loc_180016557
0x180016541  mov     rdx, [rsp+78h+arg_60]
0x180016549  mov     r8d, 400h
0x18001654f  mov     rcx, rbx
0x180016552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016557  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001655e  test    rax, rax
0x180016561  jz      short loc_18001656B
0x180016563  mov     rcx, rbx
0x180016566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001656b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016572  test    rax, rax
0x180016575  jz      short loc_180016585
0x180016577  test    byte ptr [rbx+4], 2
0x18001657b  jnz     short loc_180016585
0x18001657d  mov     rcx, rbx
0x180016580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016585  cmp     [rbx+8], edi
0x180016588  jl      short loc_1800165A6
0x18001658a  cmp     r15d, 3
0x18001658e  jz      short loc_180016596
0x180016590  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180016596  mov     ecx, 8000FFFFh; this
0x18001659b  mov     [rbx+8], ecx
0x18001659e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800165a3  mov     [rbx+0Ch], eax
0x1800165a6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800165ad  jnz     short loc_1800165CE
0x1800165af  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800165b6  test    rax, rax
0x1800165b9  jz      short loc_1800165C4
0x1800165bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165c0  test    al, al
0x1800165c2  jmp     short loc_1800165CC
0x1800165c4  call    cs:__imp_IsDebuggerPresent
0x1800165ca  test    eax, eax
0x1800165cc  jz      short loc_1800165D4
0x1800165ce  test    byte ptr [rbx+4], 2
0x1800165d2  jz      short loc_1800165F8
0x1800165d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800165db  test    rax, rax
0x1800165de  jz      short loc_18001663C
0x1800165e0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800165e7  jnz     short loc_18001663C
0x1800165e9  xor     r8d, r8d
0x1800165ec  xor     edx, edx
0x1800165ee  mov     rcx, rbx
0x1800165f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165f6  jmp     short loc_18001663C
0x1800165f8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800165ff  mov     ebp, 800h
0x180016604  test    rax, rax
0x180016607  jz      short loc_180016620
0x180016609  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180016610  jnz     short loc_180016620
0x180016612  mov     r8d, ebp
0x180016615  mov     rdx, rsi
0x180016618  mov     rcx, rbx
0x18001661b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016620  cmp     [rsi], di
0x180016623  jnz     short loc_180016633
0x180016625  mov     r8, rbx; unsigned __int64
0x180016628  mov     rdx, rbp; unsigned __int16 *
0x18001662b  mov     rcx, rsi; this
0x18001662e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180016633  mov     rcx, rsi; lpOutputString
0x180016636  call    cs:__imp_OutputDebugStringW
0x18001663c  test    byte ptr [rbx+4], 4
0x180016640  jnz     short loc_18001664B
0x180016642  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180016649  jz      short loc_18001665C
0x18001664b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180016652  test    rax, rax
0x180016655  jz      short loc_18001665C
0x180016657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001665c  mov     rbx, [rsp+78h+arg_10]
0x180016664  add     rsp, 40h
0x180016668  pop     r15
0x18001666a  pop     r14
0x18001666c  pop     r13
0x18001666e  pop     r12
0x180016670  pop     rdi
0x180016671  pop     rsi
0x180016672  pop     rbp
0x180016673  retn
```
