# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180025a70`
- end: `0x180025d68`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800243b0`
- `0x180024700`

## callees

- `0x1800242f8`
- `0x1800250c4`
- `0x18002576c`
- `0x180025a70`
- `0x1800267f8`
- `0x180026820`
- `0x180026834`
- `0x180026850`
- `0x180027144`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180025b93`
- `KERNEL32!GetCurrentThreadId` at `0x180025b93`
- `KERNEL32!OutputDebugStringW` at `0x180025d24`
- `KERNEL32!OutputDebugStringW` at `0x180025d24`
- `KERNEL32!IsDebuggerPresent` at `0x180025cb2`
- `KERNEL32!IsDebuggerPresent` at `0x180025cb2`

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
0x180025a70  mov     [rsp+arg_10], rbx
0x180025a75  mov     [rsp+arg_8], edx
0x180025a79  mov     [rsp+arg_0], rcx
0x180025a7e  push    rbp
0x180025a7f  push    rsi
0x180025a80  push    rdi
0x180025a81  push    r12
0x180025a83  push    r13
0x180025a85  push    r14
0x180025a87  push    r15
0x180025a89  sub     rsp, 40h
0x180025a8d  mov     r14, [rsp+78h+arg_38]
0x180025a95  xor     eax, eax
0x180025a97  mov     rbx, [rsp+78h+arg_78]
0x180025a9f  xor     ebp, ebp
0x180025aa1  mov     r15d, [rsp+78h+arg_30]
0x180025aa9  mov     r10, rcx
0x180025aac  mov     rsi, [rsp+78h+lpOutputString]
0x180025ab4  mov     r12, r9
0x180025ab7  mov     r13, r8
0x180025aba  mov     ecx, r15d
0x180025abd  mov     [rsi], ax
0x180025ac0  mov     rax, [rsp+78h+arg_60]
0x180025ac8  mov     byte ptr [rax], 0
0x180025acb  mov     edi, [r14]
0x180025ace  mov     [rbx+8], edi
0x180025ad1  mov     eax, [r14+4]
0x180025ad5  mov     [rbx+0Ch], eax
0x180025ad8  test    r15d, r15d
0x180025adb  jz      short loc_180025B43
0x180025add  sub     ecx, 1
0x180025ae0  jz      short loc_180025B3A
0x180025ae2  sub     ecx, 1
0x180025ae5  jz      short loc_180025AF5
0x180025ae7  cmp     ecx, 1
0x180025aea  jnz     short loc_180025B4C
0x180025aec  mov     ecx, edi; this
0x180025aee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180025af3  jmp     short loc_180025B4A
0x180025af5  test    edi, edi
0x180025af7  js      short loc_180025B31
0x180025af9  mov     rax, [rsp+78h+arg_28]
0x180025b01  mov     edi, 8007029Ch
0x180025b06  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180025b0a  mov     rcx, r10; int
0x180025b0d  mov     [rsp+78h+var_50], rax; __int64
0x180025b12  mov     rax, [rsp+78h+arg_20]
0x180025b1a  mov     [rsp+78h+var_58], rax; __int64
0x180025b1f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180025b24  mov     ecx, edi; this
0x180025b26  mov     [rbx+8], edi
0x180025b29  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025b2e  mov     [rbx+0Ch], eax
0x180025b31  mov     ecx, edi; this
0x180025b33  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180025b38  jmp     short loc_180025B4A
0x180025b3a  mov     ecx, edi; this
0x180025b3c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180025b41  jmp     short loc_180025B4A
0x180025b43  mov     ecx, edi; this
0x180025b45  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180025b4a  mov     ebp, eax
0x180025b4c  mov     eax, [rsp+78h+arg_70]
0x180025b53  mov     [rbx+4], eax
0x180025b56  mov     [rbx], r15d
0x180025b59  cmp     dword ptr [r14+8], 1
0x180025b5e  jnz     short loc_180025B66
0x180025b60  or      eax, 8
0x180025b63  mov     [rbx+4], eax
0x180025b66  mov     eax, 1
0x180025b6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180025b73  inc     eax
0x180025b75  xor     edi, edi
0x180025b77  mov     [rbx+10h], eax
0x180025b7a  mov     rax, [rsp+78h+arg_40]
0x180025b82  test    rax, rax
0x180025b85  jz      short loc_180025B8C
0x180025b87  cmp     [rax], di
0x180025b8a  jnz     short loc_180025B8F
0x180025b8c  mov     rax, rdi
0x180025b8f  mov     [rbx+18h], rax
0x180025b93  call    cs:__imp_GetCurrentThreadId
0x180025b99  mov     [rbx+38h], r13
0x180025b9d  xorps   xmm0, xmm0
0x180025ba0  mov     [rbx+20h], eax
0x180025ba3  mov     eax, [rsp+78h+arg_8]
0x180025baa  mov     [rbx+40h], eax
0x180025bad  mov     rax, [rsp+78h+arg_20]
0x180025bb5  mov     [rbx+28h], rax
0x180025bb9  mov     rax, [rsp+78h+arg_28]
0x180025bc1  mov     [rbx+88h], rax
0x180025bc8  mov     rax, [rsp+78h+arg_0]
0x180025bd0  mov     [rbx+90h], rax
0x180025bd7  xor     eax, eax
0x180025bd9  mov     [rbx+44h], ebp
0x180025bdc  mov     [rbx+30h], r12
0x180025be0  mov     [rbx+48h], rdi
0x180025be4  movups  xmmword ptr [rbx+68h], xmm0
0x180025be8  mov     [rbx+78h], rax
0x180025bec  movups  xmmword ptr [rbx+50h], xmm0
0x180025bf0  mov     [rbx+60h], rax
0x180025bf4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180025bfb  test    rax, rax
0x180025bfe  jz      short loc_180025C07
0x180025c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c05  jmp     short loc_180025C0A
0x180025c07  mov     rax, rdi
0x180025c0a  mov     [rbx+80h], rax
0x180025c11  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025c18  test    rax, rax
0x180025c1b  jz      short loc_180025C25
0x180025c1d  mov     rcx, rbx
0x180025c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c25  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025c2c  test    rax, rax
0x180025c2f  jz      short loc_180025C47
0x180025c31  mov     rdx, [rsp+78h+arg_60]
0x180025c39  mov     r8d, 400h
0x180025c3f  mov     rcx, rbx
0x180025c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c47  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025c4e  test    rax, rax
0x180025c51  jz      short loc_180025C5B
0x180025c53  mov     rcx, rbx
0x180025c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c5b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025c62  test    rax, rax
0x180025c65  jz      short loc_180025C75
0x180025c67  test    byte ptr [rbx+4], 2
0x180025c6b  jnz     short loc_180025C75
0x180025c6d  mov     rcx, rbx
0x180025c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c75  cmp     [rbx+8], edi
0x180025c78  jl      short loc_180025C94
0x180025c7a  cmp     r15d, 3
0x180025c7e  jnz     loc_180025D62
0x180025c84  mov     ecx, 8000FFFFh; this
0x180025c89  mov     [rbx+8], ecx
0x180025c8c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025c91  mov     [rbx+0Ch], eax
0x180025c94  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180025c9b  jnz     short loc_180025CBC
0x180025c9d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180025ca4  test    rax, rax
0x180025ca7  jz      short loc_180025CB2
0x180025ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cae  test    al, al
0x180025cb0  jmp     short loc_180025CBA
0x180025cb2  call    cs:__imp_IsDebuggerPresent
0x180025cb8  test    eax, eax
0x180025cba  jz      short loc_180025CC2
0x180025cbc  test    byte ptr [rbx+4], 2
0x180025cc0  jz      short loc_180025CE6
0x180025cc2  mov     rax, cs:g_pfnResultLoggingCallback
0x180025cc9  test    rax, rax
0x180025ccc  jz      short loc_180025D2A
0x180025cce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025cd5  jnz     short loc_180025D2A
0x180025cd7  xor     r8d, r8d
0x180025cda  xor     edx, edx
0x180025cdc  mov     rcx, rbx
0x180025cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ce4  jmp     short loc_180025D2A
0x180025ce6  mov     rax, cs:g_pfnResultLoggingCallback
0x180025ced  mov     ebp, 800h
0x180025cf2  test    rax, rax
0x180025cf5  jz      short loc_180025D0E
0x180025cf7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025cfe  jnz     short loc_180025D0E
0x180025d00  mov     r8d, ebp
0x180025d03  mov     rdx, rsi
0x180025d06  mov     rcx, rbx
0x180025d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d0e  cmp     [rsi], di
0x180025d11  jnz     short loc_180025D21
0x180025d13  mov     r8, rbx; unsigned __int64
0x180025d16  mov     rdx, rbp; unsigned __int16 *
0x180025d19  mov     rcx, rsi; this
0x180025d1c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025d21  mov     rcx, rsi; lpOutputString
0x180025d24  call    cs:__imp_OutputDebugStringW
0x180025d2a  test    byte ptr [rbx+4], 4
0x180025d2e  jnz     short loc_180025D39
0x180025d30  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180025d37  jz      short loc_180025D4A
0x180025d39  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025d40  test    rax, rax
0x180025d43  jz      short loc_180025D4A
0x180025d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d4a  mov     rbx, [rsp+78h+arg_10]
0x180025d52  add     rsp, 40h
0x180025d56  pop     r15
0x180025d58  pop     r14
0x180025d5a  pop     r13
0x180025d5c  pop     r12
0x180025d5e  pop     rdi
0x180025d5f  pop     rsi
0x180025d60  pop     rbp
0x180025d61  retn
0x180025d62  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
