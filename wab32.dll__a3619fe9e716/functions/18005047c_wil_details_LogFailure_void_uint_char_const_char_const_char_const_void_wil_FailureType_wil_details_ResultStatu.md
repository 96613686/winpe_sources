# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18005047c`
- end: `0x180050774`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800499e8`
- `0x180049d34`

## callees

- `0x180049928`
- `0x18004e688`
- `0x18004ff3c`
- `0x18005047c`
- `0x180051114`
- `0x180051130`
- `0x180051280`
- `0x18005129c`
- `0x180054ec8`
- `0x180093010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180050730`
- `KERNEL32!OutputDebugStringW` at `0x180050730`
- `KERNEL32!IsDebuggerPresent` at `0x1800506be`
- `KERNEL32!IsDebuggerPresent` at `0x1800506be`
- `KERNEL32!GetCurrentThreadId` at `0x18005059f`
- `KERNEL32!GetCurrentThreadId` at `0x18005059f`

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
0x18005047c  mov     [rsp+arg_10], rbx
0x180050481  mov     [rsp+arg_8], edx
0x180050485  mov     [rsp+arg_0], rcx
0x18005048a  push    rbp
0x18005048b  push    rsi
0x18005048c  push    rdi
0x18005048d  push    r12
0x18005048f  push    r13
0x180050491  push    r14
0x180050493  push    r15
0x180050495  sub     rsp, 40h
0x180050499  mov     r14, [rsp+78h+arg_38]
0x1800504a1  xor     eax, eax
0x1800504a3  mov     rbx, [rsp+78h+arg_78]
0x1800504ab  xor     ebp, ebp
0x1800504ad  mov     r15d, [rsp+78h+arg_30]
0x1800504b5  mov     r10, rcx
0x1800504b8  mov     rsi, [rsp+78h+lpOutputString]
0x1800504c0  mov     r12, r9
0x1800504c3  mov     r13, r8
0x1800504c6  mov     ecx, r15d
0x1800504c9  mov     [rsi], ax
0x1800504cc  mov     rax, [rsp+78h+arg_60]
0x1800504d4  mov     byte ptr [rax], 0
0x1800504d7  mov     edi, [r14]
0x1800504da  mov     [rbx+8], edi
0x1800504dd  mov     eax, [r14+4]
0x1800504e1  mov     [rbx+0Ch], eax
0x1800504e4  test    r15d, r15d
0x1800504e7  jz      short loc_18005054F
0x1800504e9  sub     ecx, 1
0x1800504ec  jz      short loc_180050546
0x1800504ee  sub     ecx, 1
0x1800504f1  jz      short loc_180050501
0x1800504f3  cmp     ecx, 1
0x1800504f6  jnz     short loc_180050558
0x1800504f8  mov     ecx, edi; this
0x1800504fa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800504ff  jmp     short loc_180050556
0x180050501  test    edi, edi
0x180050503  js      short loc_18005053D
0x180050505  mov     rax, [rsp+78h+arg_28]
0x18005050d  mov     edi, 8007029Ch
0x180050512  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180050516  mov     rcx, r10; int
0x180050519  mov     [rsp+78h+var_50], rax; __int64
0x18005051e  mov     rax, [rsp+78h+arg_20]
0x180050526  mov     [rsp+78h+var_58], rax; __int64
0x18005052b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180050530  mov     ecx, edi; this
0x180050532  mov     [rbx+8], edi
0x180050535  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005053a  mov     [rbx+0Ch], eax
0x18005053d  mov     ecx, edi; this
0x18005053f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180050544  jmp     short loc_180050556
0x180050546  mov     ecx, edi; this
0x180050548  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005054d  jmp     short loc_180050556
0x18005054f  mov     ecx, edi; this
0x180050551  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180050556  mov     ebp, eax
0x180050558  mov     eax, [rsp+78h+arg_70]
0x18005055f  mov     [rbx+4], eax
0x180050562  mov     [rbx], r15d
0x180050565  cmp     dword ptr [r14+8], 1
0x18005056a  jnz     short loc_180050572
0x18005056c  or      eax, 8
0x18005056f  mov     [rbx+4], eax
0x180050572  mov     eax, 1
0x180050577  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005057f  inc     eax
0x180050581  xor     edi, edi
0x180050583  mov     [rbx+10h], eax
0x180050586  mov     rax, [rsp+78h+arg_40]
0x18005058e  test    rax, rax
0x180050591  jz      short loc_180050598
0x180050593  cmp     [rax], di
0x180050596  jnz     short loc_18005059B
0x180050598  mov     rax, rdi
0x18005059b  mov     [rbx+18h], rax
0x18005059f  call    cs:__imp_GetCurrentThreadId
0x1800505a5  mov     [rbx+38h], r13
0x1800505a9  xorps   xmm0, xmm0
0x1800505ac  mov     [rbx+20h], eax
0x1800505af  mov     eax, [rsp+78h+arg_8]
0x1800505b6  mov     [rbx+40h], eax
0x1800505b9  mov     rax, [rsp+78h+arg_20]
0x1800505c1  mov     [rbx+28h], rax
0x1800505c5  mov     rax, [rsp+78h+arg_28]
0x1800505cd  mov     [rbx+88h], rax
0x1800505d4  mov     rax, [rsp+78h+arg_0]
0x1800505dc  mov     [rbx+90h], rax
0x1800505e3  xor     eax, eax
0x1800505e5  mov     [rbx+44h], ebp
0x1800505e8  mov     [rbx+30h], r12
0x1800505ec  mov     [rbx+48h], rdi
0x1800505f0  movups  xmmword ptr [rbx+68h], xmm0
0x1800505f4  mov     [rbx+78h], rax
0x1800505f8  movups  xmmword ptr [rbx+50h], xmm0
0x1800505fc  mov     [rbx+60h], rax
0x180050600  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180050607  test    rax, rax
0x18005060a  jz      short loc_180050613
0x18005060c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050611  jmp     short loc_180050616
0x180050613  mov     rax, rdi
0x180050616  mov     [rbx+80h], rax
0x18005061d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180050624  test    rax, rax
0x180050627  jz      short loc_180050631
0x180050629  mov     rcx, rbx
0x18005062c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050631  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180050638  test    rax, rax
0x18005063b  jz      short loc_180050653
0x18005063d  mov     rdx, [rsp+78h+arg_60]
0x180050645  mov     r8d, 400h
0x18005064b  mov     rcx, rbx
0x18005064e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050653  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005065a  test    rax, rax
0x18005065d  jz      short loc_180050667
0x18005065f  mov     rcx, rbx
0x180050662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050667  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005066e  test    rax, rax
0x180050671  jz      short loc_180050681
0x180050673  test    byte ptr [rbx+4], 2
0x180050677  jnz     short loc_180050681
0x180050679  mov     rcx, rbx
0x18005067c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050681  cmp     [rbx+8], edi
0x180050684  jl      short loc_1800506A0
0x180050686  cmp     r15d, 3
0x18005068a  jnz     loc_18005076E
0x180050690  mov     ecx, 8000FFFFh; this
0x180050695  mov     [rbx+8], ecx
0x180050698  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005069d  mov     [rbx+0Ch], eax
0x1800506a0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800506a7  jnz     short loc_1800506C8
0x1800506a9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800506b0  test    rax, rax
0x1800506b3  jz      short loc_1800506BE
0x1800506b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506ba  test    al, al
0x1800506bc  jmp     short loc_1800506C6
0x1800506be  call    cs:__imp_IsDebuggerPresent
0x1800506c4  test    eax, eax
0x1800506c6  jz      short loc_1800506CE
0x1800506c8  test    byte ptr [rbx+4], 2
0x1800506cc  jz      short loc_1800506F2
0x1800506ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800506d5  test    rax, rax
0x1800506d8  jz      short loc_180050736
0x1800506da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800506e1  jnz     short loc_180050736
0x1800506e3  xor     r8d, r8d
0x1800506e6  xor     edx, edx
0x1800506e8  mov     rcx, rbx
0x1800506eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506f0  jmp     short loc_180050736
0x1800506f2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800506f9  mov     ebp, 800h
0x1800506fe  test    rax, rax
0x180050701  jz      short loc_18005071A
0x180050703  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005070a  jnz     short loc_18005071A
0x18005070c  mov     r8d, ebp
0x18005070f  mov     rdx, rsi
0x180050712  mov     rcx, rbx
0x180050715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005071a  cmp     [rsi], di
0x18005071d  jnz     short loc_18005072D
0x18005071f  mov     r8, rbx; unsigned __int64
0x180050722  mov     rdx, rbp; unsigned __int16 *
0x180050725  mov     rcx, rsi; this
0x180050728  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005072d  mov     rcx, rsi; lpOutputString
0x180050730  call    cs:__imp_OutputDebugStringW
0x180050736  test    byte ptr [rbx+4], 4
0x18005073a  jnz     short loc_180050745
0x18005073c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180050743  jz      short loc_180050756
0x180050745  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005074c  test    rax, rax
0x18005074f  jz      short loc_180050756
0x180050751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050756  mov     rbx, [rsp+78h+arg_10]
0x18005075e  add     rsp, 40h
0x180050762  pop     r15
0x180050764  pop     r14
0x180050766  pop     r13
0x180050768  pop     r12
0x18005076a  pop     rdi
0x18005076b  pop     rsi
0x18005076c  pop     rbp
0x18005076d  retn
0x18005076e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
