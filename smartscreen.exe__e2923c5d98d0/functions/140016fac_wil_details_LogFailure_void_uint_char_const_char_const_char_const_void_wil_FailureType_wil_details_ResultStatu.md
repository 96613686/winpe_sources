# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140016fac`
- end: `0x1400172a1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x14000e890`
- `0x140016ebc`
- `0x14002d9e8`
- `0x14002da98`

## callees

- `0x14000d430`
- `0x140011784`
- `0x140016fac`
- `0x1400172b0`
- `0x14001d2bc`
- `0x14001ede8`
- `0x14002d91c`
- `0x14002e0ec`
- `0x14002e5c0`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400170cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400170cf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400171f0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400171f0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140017262`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140017262`

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
0x140016fac  mov     [rsp+arg_10], rbx
0x140016fb1  mov     [rsp+arg_8], edx
0x140016fb5  mov     [rsp+arg_0], rcx
0x140016fba  push    rbp
0x140016fbb  push    rsi
0x140016fbc  push    rdi
0x140016fbd  push    r12
0x140016fbf  push    r13
0x140016fc1  push    r14
0x140016fc3  push    r15
0x140016fc5  sub     rsp, 40h
0x140016fc9  mov     r12, r9
0x140016fcc  mov     r13, r8
0x140016fcf  mov     r10, rcx
0x140016fd2  xor     eax, eax
0x140016fd4  mov     rsi, [rsp+78h+lpOutputString]
0x140016fdc  mov     [rsi], ax
0x140016fdf  mov     rax, [rsp+78h+arg_60]
0x140016fe7  mov     byte ptr [rax], 0
0x140016fea  mov     r14, [rsp+78h+arg_38]
0x140016ff2  mov     edi, [r14]
0x140016ff5  mov     rbx, [rsp+78h+arg_78]
0x140016ffd  mov     [rbx+8], edi
0x140017000  mov     eax, [r14+4]
0x140017004  mov     [rbx+0Ch], eax
0x140017007  xor     ebp, ebp
0x140017009  mov     r15d, [rsp+78h+arg_30]
0x140017011  mov     ecx, r15d
0x140017014  test    r15d, r15d
0x140017017  jz      short loc_14001707F
0x140017019  sub     ecx, 1
0x14001701c  jz      short loc_140017076
0x14001701e  sub     ecx, 1
0x140017021  jz      short loc_140017031
0x140017023  cmp     ecx, 1
0x140017026  jnz     short loc_140017088
0x140017028  mov     ecx, edi; this
0x14001702a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14001702f  jmp     short loc_140017086
0x140017031  test    edi, edi
0x140017033  js      short loc_14001706D
0x140017035  mov     edi, 8007029Ch
0x14001703a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14001703e  mov     rax, [rsp+78h+arg_28]
0x140017046  mov     [rsp+78h+var_50], rax; __int64
0x14001704b  mov     rax, [rsp+78h+arg_20]
0x140017053  mov     [rsp+78h+var_58], rax; __int64
0x140017058  mov     rcx, r10; int
0x14001705b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140017060  mov     [rbx+8], edi
0x140017063  mov     ecx, edi; this
0x140017065  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14001706a  mov     [rbx+0Ch], eax
0x14001706d  mov     ecx, edi; this
0x14001706f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140017074  jmp     short loc_140017086
0x140017076  mov     ecx, edi; this
0x140017078  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14001707d  jmp     short loc_140017086
0x14001707f  mov     ecx, edi; this
0x140017081  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140017086  mov     ebp, eax
0x140017088  mov     [rbx], r15d
0x14001708b  mov     eax, [rsp+78h+arg_70]
0x140017092  mov     [rbx+4], eax
0x140017095  cmp     dword ptr [r14+8], 1
0x14001709a  jnz     short loc_1400170A2
0x14001709c  or      eax, 8
0x14001709f  mov     [rbx+4], eax
0x1400170a2  mov     eax, 1
0x1400170a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400170af  inc     eax
0x1400170b1  mov     [rbx+10h], eax
0x1400170b4  mov     rax, [rsp+78h+arg_40]
0x1400170bc  xor     edi, edi
0x1400170be  test    rax, rax
0x1400170c1  jz      short loc_1400170C8
0x1400170c3  cmp     [rax], di
0x1400170c6  jnz     short loc_1400170CB
0x1400170c8  mov     rax, rdi
0x1400170cb  mov     [rbx+18h], rax
0x1400170cf  call    cs:__imp_GetCurrentThreadId
0x1400170d5  mov     [rbx+20h], eax
0x1400170d8  mov     [rbx+38h], r13
0x1400170dc  mov     eax, [rsp+78h+arg_8]
0x1400170e3  mov     [rbx+40h], eax
0x1400170e6  mov     [rbx+44h], ebp
0x1400170e9  mov     rax, [rsp+78h+arg_20]
0x1400170f1  mov     [rbx+28h], rax
0x1400170f5  mov     [rbx+30h], r12
0x1400170f9  mov     rax, [rsp+78h+arg_28]
0x140017101  mov     [rbx+88h], rax
0x140017108  mov     rax, [rsp+78h+arg_0]
0x140017110  mov     [rbx+90h], rax
0x140017117  mov     [rbx+48h], rdi
0x14001711b  xorps   xmm0, xmm0
0x14001711e  xor     eax, eax
0x140017120  movups  xmmword ptr [rbx+68h], xmm0
0x140017124  mov     [rbx+78h], rax
0x140017128  movups  xmmword ptr [rbx+50h], xmm0
0x14001712c  mov     [rbx+60h], rax
0x140017130  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140017137  test    rax, rax
0x14001713a  jz      short loc_140017143
0x14001713c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017141  jmp     short loc_140017146
0x140017143  mov     rax, rdi
0x140017146  mov     [rbx+80h], rax
0x14001714d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140017154  test    rax, rax
0x140017157  jz      short loc_140017161
0x140017159  mov     rcx, rbx
0x14001715c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017161  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140017168  test    rax, rax
0x14001716b  jz      short loc_140017183
0x14001716d  mov     r8d, 400h
0x140017173  mov     rdx, [rsp+78h+arg_60]
0x14001717b  mov     rcx, rbx
0x14001717e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017183  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001718a  test    rax, rax
0x14001718d  jz      short loc_140017197
0x14001718f  mov     rcx, rbx
0x140017192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017197  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001719e  test    rax, rax
0x1400171a1  jz      short loc_1400171B1
0x1400171a3  test    byte ptr [rbx+4], 2
0x1400171a7  jnz     short loc_1400171B1
0x1400171a9  mov     rcx, rbx
0x1400171ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400171b1  cmp     [rbx+8], edi
0x1400171b4  jl      short loc_1400171D2
0x1400171b6  cmp     r15d, 3
0x1400171ba  jz      short loc_1400171C2
0x1400171bc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400171c2  mov     ecx, 8000FFFFh; this
0x1400171c7  mov     [rbx+8], ecx
0x1400171ca  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400171cf  mov     [rbx+0Ch], eax
0x1400171d2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400171d9  jnz     short loc_1400171FA
0x1400171db  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400171e2  test    rax, rax
0x1400171e5  jz      short loc_1400171F0
0x1400171e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400171ec  test    al, al
0x1400171ee  jmp     short loc_1400171F8
0x1400171f0  call    cs:__imp_IsDebuggerPresent
0x1400171f6  test    eax, eax
0x1400171f8  jz      short loc_140017200
0x1400171fa  test    byte ptr [rbx+4], 2
0x1400171fe  jz      short loc_140017224
0x140017200  mov     rax, cs:g_pfnResultLoggingCallback
0x140017207  test    rax, rax
0x14001720a  jz      short loc_140017268
0x14001720c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140017213  jnz     short loc_140017268
0x140017215  xor     r8d, r8d
0x140017218  xor     edx, edx
0x14001721a  mov     rcx, rbx
0x14001721d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017222  jmp     short loc_140017268
0x140017224  mov     ebp, 800h
0x140017229  mov     rax, cs:g_pfnResultLoggingCallback
0x140017230  test    rax, rax
0x140017233  jz      short loc_14001724C
0x140017235  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14001723c  jnz     short loc_14001724C
0x14001723e  mov     r8d, ebp
0x140017241  mov     rdx, rsi
0x140017244  mov     rcx, rbx
0x140017247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001724c  cmp     [rsi], di
0x14001724f  jnz     short loc_14001725F
0x140017251  mov     r8, rbx; unsigned __int64
0x140017254  mov     rdx, rbp; unsigned __int16 *
0x140017257  mov     rcx, rsi; this
0x14001725a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14001725f  mov     rcx, rsi; lpOutputString
0x140017262  call    cs:__imp_OutputDebugStringW
0x140017268  test    byte ptr [rbx+4], 4
0x14001726c  jnz     short loc_140017277
0x14001726e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140017275  jz      short loc_140017289
0x140017277  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14001727e  test    rax, rax
0x140017281  jz      short loc_140017289
0x140017283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017288  nop
0x140017289  mov     rbx, [rsp+78h+arg_10]
0x140017291  add     rsp, 40h
0x140017295  pop     r15
0x140017297  pop     r14
0x140017299  pop     r13
0x14001729b  pop     r12
0x14001729d  pop     rdi
0x14001729e  pop     rsi
0x14001729f  pop     rbp
0x1400172a0  retn
```
