# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18007832c`
- end: `0x180078624`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180076320`
- `0x180076668`

## callees

- `0x1800148a4`
- `0x180014acc`
- `0x180076268`
- `0x180077a80`
- `0x18007832c`
- `0x180078a44`
- `0x180078a60`
- `0x180078a74`
- `0x1800798f0`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007844f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007844f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007856e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007856e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800785e0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800785e0`

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
0x18007832c  mov     [rsp+arg_10], rbx
0x180078331  mov     [rsp+arg_8], edx
0x180078335  mov     [rsp+arg_0], rcx
0x18007833a  push    rbp
0x18007833b  push    rsi
0x18007833c  push    rdi
0x18007833d  push    r12
0x18007833f  push    r13
0x180078341  push    r14
0x180078343  push    r15
0x180078345  sub     rsp, 40h
0x180078349  mov     r14, [rsp+78h+arg_38]
0x180078351  xor     eax, eax
0x180078353  mov     rbx, [rsp+78h+arg_78]
0x18007835b  xor     ebp, ebp
0x18007835d  mov     r15d, [rsp+78h+arg_30]
0x180078365  mov     r10, rcx
0x180078368  mov     rsi, [rsp+78h+lpOutputString]
0x180078370  mov     r12, r9
0x180078373  mov     r13, r8
0x180078376  mov     ecx, r15d
0x180078379  mov     [rsi], ax
0x18007837c  mov     rax, [rsp+78h+arg_60]
0x180078384  mov     byte ptr [rax], 0
0x180078387  mov     edi, [r14]
0x18007838a  mov     [rbx+8], edi
0x18007838d  mov     eax, [r14+4]
0x180078391  mov     [rbx+0Ch], eax
0x180078394  test    r15d, r15d
0x180078397  jz      short loc_1800783FF
0x180078399  sub     ecx, 1
0x18007839c  jz      short loc_1800783F6
0x18007839e  sub     ecx, 1
0x1800783a1  jz      short loc_1800783B1
0x1800783a3  cmp     ecx, 1
0x1800783a6  jnz     short loc_180078408
0x1800783a8  mov     ecx, edi; this
0x1800783aa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800783af  jmp     short loc_180078406
0x1800783b1  test    edi, edi
0x1800783b3  js      short loc_1800783ED
0x1800783b5  mov     rax, [rsp+78h+arg_28]
0x1800783bd  mov     edi, 8007029Ch
0x1800783c2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800783c6  mov     rcx, r10; int
0x1800783c9  mov     [rsp+78h+var_50], rax; __int64
0x1800783ce  mov     rax, [rsp+78h+arg_20]
0x1800783d6  mov     [rsp+78h+var_58], rax; __int64
0x1800783db  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800783e0  mov     ecx, edi; this
0x1800783e2  mov     [rbx+8], edi
0x1800783e5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800783ea  mov     [rbx+0Ch], eax
0x1800783ed  mov     ecx, edi; this
0x1800783ef  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800783f4  jmp     short loc_180078406
0x1800783f6  mov     ecx, edi; this
0x1800783f8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800783fd  jmp     short loc_180078406
0x1800783ff  mov     ecx, edi; this
0x180078401  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180078406  mov     ebp, eax
0x180078408  mov     eax, [rsp+78h+arg_70]
0x18007840f  mov     [rbx+4], eax
0x180078412  mov     [rbx], r15d
0x180078415  cmp     dword ptr [r14+8], 1
0x18007841a  jnz     short loc_180078422
0x18007841c  or      eax, 8
0x18007841f  mov     [rbx+4], eax
0x180078422  mov     eax, 1
0x180078427  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18007842f  inc     eax
0x180078431  xor     edi, edi
0x180078433  mov     [rbx+10h], eax
0x180078436  mov     rax, [rsp+78h+arg_40]
0x18007843e  test    rax, rax
0x180078441  jz      short loc_180078448
0x180078443  cmp     [rax], di
0x180078446  jnz     short loc_18007844B
0x180078448  mov     rax, rdi
0x18007844b  mov     [rbx+18h], rax
0x18007844f  call    cs:__imp_GetCurrentThreadId
0x180078455  mov     [rbx+38h], r13
0x180078459  xorps   xmm0, xmm0
0x18007845c  mov     [rbx+20h], eax
0x18007845f  mov     eax, [rsp+78h+arg_8]
0x180078466  mov     [rbx+40h], eax
0x180078469  mov     rax, [rsp+78h+arg_20]
0x180078471  mov     [rbx+28h], rax
0x180078475  mov     rax, [rsp+78h+arg_28]
0x18007847d  mov     [rbx+88h], rax
0x180078484  mov     rax, [rsp+78h+arg_0]
0x18007848c  mov     [rbx+90h], rax
0x180078493  xor     eax, eax
0x180078495  mov     [rbx+44h], ebp
0x180078498  mov     [rbx+30h], r12
0x18007849c  mov     [rbx+48h], rdi
0x1800784a0  movups  xmmword ptr [rbx+68h], xmm0
0x1800784a4  mov     [rbx+78h], rax
0x1800784a8  movups  xmmword ptr [rbx+50h], xmm0
0x1800784ac  mov     [rbx+60h], rax
0x1800784b0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800784b7  test    rax, rax
0x1800784ba  jz      short loc_1800784C3
0x1800784bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784c1  jmp     short loc_1800784C6
0x1800784c3  mov     rax, rdi
0x1800784c6  mov     [rbx+80h], rax
0x1800784cd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800784d4  test    rax, rax
0x1800784d7  jz      short loc_1800784E1
0x1800784d9  mov     rcx, rbx
0x1800784dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784e1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800784e8  test    rax, rax
0x1800784eb  jz      short loc_180078503
0x1800784ed  mov     rdx, [rsp+78h+arg_60]
0x1800784f5  mov     r8d, 400h
0x1800784fb  mov     rcx, rbx
0x1800784fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078503  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007850a  test    rax, rax
0x18007850d  jz      short loc_180078517
0x18007850f  mov     rcx, rbx
0x180078512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078517  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007851e  test    rax, rax
0x180078521  jz      short loc_180078531
0x180078523  test    byte ptr [rbx+4], 2
0x180078527  jnz     short loc_180078531
0x180078529  mov     rcx, rbx
0x18007852c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078531  cmp     [rbx+8], edi
0x180078534  jl      short loc_180078550
0x180078536  cmp     r15d, 3
0x18007853a  jnz     loc_18007861E
0x180078540  mov     ecx, 8000FFFFh; this
0x180078545  mov     [rbx+8], ecx
0x180078548  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18007854d  mov     [rbx+0Ch], eax
0x180078550  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180078557  jnz     short loc_180078578
0x180078559  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180078560  test    rax, rax
0x180078563  jz      short loc_18007856E
0x180078565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007856a  test    al, al
0x18007856c  jmp     short loc_180078576
0x18007856e  call    cs:__imp_IsDebuggerPresent
0x180078574  test    eax, eax
0x180078576  jz      short loc_18007857E
0x180078578  test    byte ptr [rbx+4], 2
0x18007857c  jz      short loc_1800785A2
0x18007857e  mov     rax, cs:g_pfnResultLoggingCallback
0x180078585  test    rax, rax
0x180078588  jz      short loc_1800785E6
0x18007858a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180078591  jnz     short loc_1800785E6
0x180078593  xor     r8d, r8d
0x180078596  xor     edx, edx
0x180078598  mov     rcx, rbx
0x18007859b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800785a0  jmp     short loc_1800785E6
0x1800785a2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800785a9  mov     ebp, 800h
0x1800785ae  test    rax, rax
0x1800785b1  jz      short loc_1800785CA
0x1800785b3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800785ba  jnz     short loc_1800785CA
0x1800785bc  mov     r8d, ebp
0x1800785bf  mov     rdx, rsi
0x1800785c2  mov     rcx, rbx
0x1800785c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800785ca  cmp     [rsi], di
0x1800785cd  jnz     short loc_1800785DD
0x1800785cf  mov     r8, rbx; unsigned __int64
0x1800785d2  mov     rdx, rbp; unsigned __int16 *
0x1800785d5  mov     rcx, rsi; this
0x1800785d8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800785dd  mov     rcx, rsi; lpOutputString
0x1800785e0  call    cs:__imp_OutputDebugStringW
0x1800785e6  test    byte ptr [rbx+4], 4
0x1800785ea  jnz     short loc_1800785F5
0x1800785ec  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800785f3  jz      short loc_180078606
0x1800785f5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800785fc  test    rax, rax
0x1800785ff  jz      short loc_180078606
0x180078601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078606  mov     rbx, [rsp+78h+arg_10]
0x18007860e  add     rsp, 40h
0x180078612  pop     r15
0x180078614  pop     r14
0x180078616  pop     r13
0x180078618  pop     r12
0x18007861a  pop     rdi
0x18007861b  pop     rsi
0x18007861c  pop     rbp
0x18007861d  retn
0x18007861e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
