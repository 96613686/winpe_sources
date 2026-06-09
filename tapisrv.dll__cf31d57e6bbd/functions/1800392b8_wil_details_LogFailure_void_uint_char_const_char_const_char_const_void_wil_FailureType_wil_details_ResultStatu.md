# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800392b8`
- end: `0x1800395b0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180035c70`

## callees

- `0x1800356ac`
- `0x1800380e4`
- `0x180038ebc`
- `0x1800392b8`
- `0x18003a028`
- `0x18003a050`
- `0x18003a1d4`
- `0x18003a1f0`
- `0x18003c408`
- `0x180040010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800394fa`
- `KERNEL32!IsDebuggerPresent` at `0x1800394fa`
- `KERNEL32!OutputDebugStringW` at `0x18003956c`
- `KERNEL32!OutputDebugStringW` at `0x18003956c`
- `KERNEL32!GetCurrentThreadId` at `0x1800393db`
- `KERNEL32!GetCurrentThreadId` at `0x1800393db`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x1800392b8  mov     [rsp+arg_10], rbx
0x1800392bd  mov     [rsp+arg_8], edx
0x1800392c1  mov     [rsp+arg_0], rcx
0x1800392c6  push    rbp
0x1800392c7  push    rsi
0x1800392c8  push    rdi
0x1800392c9  push    r12
0x1800392cb  push    r13
0x1800392cd  push    r14
0x1800392cf  push    r15
0x1800392d1  sub     rsp, 40h
0x1800392d5  mov     r14, [rsp+78h+arg_38]
0x1800392dd  xor     eax, eax
0x1800392df  mov     rbx, [rsp+78h+arg_78]
0x1800392e7  xor     ebp, ebp
0x1800392e9  mov     r15d, [rsp+78h+arg_30]
0x1800392f1  mov     r10, rcx
0x1800392f4  mov     rsi, [rsp+78h+lpOutputString]
0x1800392fc  mov     r12, r9
0x1800392ff  mov     r13, r8
0x180039302  mov     ecx, r15d
0x180039305  mov     [rsi], ax
0x180039308  mov     rax, [rsp+78h+arg_60]
0x180039310  mov     byte ptr [rax], 0
0x180039313  mov     edi, [r14]
0x180039316  mov     [rbx+8], edi
0x180039319  mov     eax, [r14+4]
0x18003931d  mov     [rbx+0Ch], eax
0x180039320  test    r15d, r15d
0x180039323  jz      short loc_18003938B
0x180039325  sub     ecx, 1
0x180039328  jz      short loc_180039382
0x18003932a  sub     ecx, 1
0x18003932d  jz      short loc_18003933D
0x18003932f  cmp     ecx, 1
0x180039332  jnz     short loc_180039394
0x180039334  mov     ecx, edi; this
0x180039336  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003933b  jmp     short loc_180039392
0x18003933d  test    edi, edi
0x18003933f  js      short loc_180039379
0x180039341  mov     rax, [rsp+78h+arg_28]
0x180039349  mov     edi, 8007029Ch
0x18003934e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180039352  mov     rcx, r10; int
0x180039355  mov     [rsp+78h+var_50], rax; __int64
0x18003935a  mov     rax, [rsp+78h+arg_20]
0x180039362  mov     [rsp+78h+var_58], rax; __int64
0x180039367  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003936c  mov     ecx, edi; this
0x18003936e  mov     [rbx+8], edi
0x180039371  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180039376  mov     [rbx+0Ch], eax
0x180039379  mov     ecx, edi; this
0x18003937b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180039380  jmp     short loc_180039392
0x180039382  mov     ecx, edi; this
0x180039384  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180039389  jmp     short loc_180039392
0x18003938b  mov     ecx, edi; this
0x18003938d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180039392  mov     ebp, eax
0x180039394  mov     eax, [rsp+78h+arg_70]
0x18003939b  mov     [rbx+4], eax
0x18003939e  mov     [rbx], r15d
0x1800393a1  cmp     dword ptr [r14+8], 1
0x1800393a6  jnz     short loc_1800393AE
0x1800393a8  or      eax, 8
0x1800393ab  mov     [rbx+4], eax
0x1800393ae  mov     eax, 1
0x1800393b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800393bb  inc     eax
0x1800393bd  xor     edi, edi
0x1800393bf  mov     [rbx+10h], eax
0x1800393c2  mov     rax, [rsp+78h+arg_40]
0x1800393ca  test    rax, rax
0x1800393cd  jz      short loc_1800393D4
0x1800393cf  cmp     [rax], di
0x1800393d2  jnz     short loc_1800393D7
0x1800393d4  mov     rax, rdi
0x1800393d7  mov     [rbx+18h], rax
0x1800393db  call    cs:__imp_GetCurrentThreadId
0x1800393e1  mov     [rbx+38h], r13
0x1800393e5  xorps   xmm0, xmm0
0x1800393e8  mov     [rbx+20h], eax
0x1800393eb  mov     eax, [rsp+78h+arg_8]
0x1800393f2  mov     [rbx+40h], eax
0x1800393f5  mov     rax, [rsp+78h+arg_20]
0x1800393fd  mov     [rbx+28h], rax
0x180039401  mov     rax, [rsp+78h+arg_28]
0x180039409  mov     [rbx+88h], rax
0x180039410  mov     rax, [rsp+78h+arg_0]
0x180039418  mov     [rbx+90h], rax
0x18003941f  xor     eax, eax
0x180039421  mov     [rbx+44h], ebp
0x180039424  mov     [rbx+30h], r12
0x180039428  mov     [rbx+48h], rdi
0x18003942c  movups  xmmword ptr [rbx+68h], xmm0
0x180039430  mov     [rbx+78h], rax
0x180039434  movups  xmmword ptr [rbx+50h], xmm0
0x180039438  mov     [rbx+60h], rax
0x18003943c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180039443  test    rax, rax
0x180039446  jz      short loc_18003944F
0x180039448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003944d  jmp     short loc_180039452
0x18003944f  mov     rax, rdi
0x180039452  mov     [rbx+80h], rax
0x180039459  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180039460  test    rax, rax
0x180039463  jz      short loc_18003946D
0x180039465  mov     rcx, rbx
0x180039468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003946d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180039474  test    rax, rax
0x180039477  jz      short loc_18003948F
0x180039479  mov     rdx, [rsp+78h+arg_60]
0x180039481  mov     r8d, 400h
0x180039487  mov     rcx, rbx
0x18003948a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003948f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180039496  test    rax, rax
0x180039499  jz      short loc_1800394A3
0x18003949b  mov     rcx, rbx
0x18003949e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800394aa  test    rax, rax
0x1800394ad  jz      short loc_1800394BD
0x1800394af  test    byte ptr [rbx+4], 2
0x1800394b3  jnz     short loc_1800394BD
0x1800394b5  mov     rcx, rbx
0x1800394b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394bd  cmp     [rbx+8], edi
0x1800394c0  jl      short loc_1800394DC
0x1800394c2  cmp     r15d, 3
0x1800394c6  jnz     loc_1800395AA
0x1800394cc  mov     ecx, 8000FFFFh; this
0x1800394d1  mov     [rbx+8], ecx
0x1800394d4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800394d9  mov     [rbx+0Ch], eax
0x1800394dc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800394e3  jnz     short loc_180039504
0x1800394e5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800394ec  test    rax, rax
0x1800394ef  jz      short loc_1800394FA
0x1800394f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394f6  test    al, al
0x1800394f8  jmp     short loc_180039502
0x1800394fa  call    cs:__imp_IsDebuggerPresent
0x180039500  test    eax, eax
0x180039502  jz      short loc_18003950A
0x180039504  test    byte ptr [rbx+4], 2
0x180039508  jz      short loc_18003952E
0x18003950a  mov     rax, cs:g_pfnResultLoggingCallback
0x180039511  test    rax, rax
0x180039514  jz      short loc_180039572
0x180039516  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003951d  jnz     short loc_180039572
0x18003951f  xor     r8d, r8d
0x180039522  xor     edx, edx
0x180039524  mov     rcx, rbx
0x180039527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003952c  jmp     short loc_180039572
0x18003952e  mov     rax, cs:g_pfnResultLoggingCallback
0x180039535  mov     ebp, 800h
0x18003953a  test    rax, rax
0x18003953d  jz      short loc_180039556
0x18003953f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180039546  jnz     short loc_180039556
0x180039548  mov     r8d, ebp
0x18003954b  mov     rdx, rsi
0x18003954e  mov     rcx, rbx
0x180039551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039556  cmp     [rsi], di
0x180039559  jnz     short loc_180039569
0x18003955b  mov     r8, rbx; unsigned __int64
0x18003955e  mov     rdx, rbp; unsigned __int16 *
0x180039561  mov     rcx, rsi; this
0x180039564  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180039569  mov     rcx, rsi; lpOutputString
0x18003956c  call    cs:__imp_OutputDebugStringW
0x180039572  test    byte ptr [rbx+4], 4
0x180039576  jnz     short loc_180039581
0x180039578  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003957f  jz      short loc_180039592
0x180039581  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180039588  test    rax, rax
0x18003958b  jz      short loc_180039592
0x18003958d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039592  mov     rbx, [rsp+78h+arg_10]
0x18003959a  add     rsp, 40h
0x18003959e  pop     r15
0x1800395a0  pop     r14
0x1800395a2  pop     r13
0x1800395a4  pop     r12
0x1800395a6  pop     rdi
0x1800395a7  pop     rsi
0x1800395a8  pop     rbp
0x1800395a9  retn
0x1800395aa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
