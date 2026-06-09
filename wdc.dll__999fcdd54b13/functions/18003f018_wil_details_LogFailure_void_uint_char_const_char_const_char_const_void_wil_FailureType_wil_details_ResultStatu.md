# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003f018`
- end: `0x18003f310`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18003d248`
- `0x18003d58c`

## callees

- `0x1800356f0`
- `0x18003d188`
- `0x18003e694`
- `0x18003f018`
- `0x18003fc78`
- `0x18003fca0`
- `0x18003fd5c`
- `0x18003fd78`
- `0x180041230`
- `0x180086010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18003f25a`
- `KERNEL32!IsDebuggerPresent` at `0x18003f25a`
- `KERNEL32!OutputDebugStringW` at `0x18003f2cc`
- `KERNEL32!OutputDebugStringW` at `0x18003f2cc`
- `KERNEL32!GetCurrentThreadId` at `0x18003f13b`
- `KERNEL32!GetCurrentThreadId` at `0x18003f13b`

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
0x18003f018  mov     [rsp+arg_10], rbx
0x18003f01d  mov     [rsp+arg_8], edx
0x18003f021  mov     [rsp+arg_0], rcx
0x18003f026  push    rbp
0x18003f027  push    rsi
0x18003f028  push    rdi
0x18003f029  push    r12
0x18003f02b  push    r13
0x18003f02d  push    r14
0x18003f02f  push    r15
0x18003f031  sub     rsp, 40h
0x18003f035  mov     r14, [rsp+78h+arg_38]
0x18003f03d  xor     eax, eax
0x18003f03f  mov     rbx, [rsp+78h+arg_78]
0x18003f047  xor     ebp, ebp
0x18003f049  mov     r15d, [rsp+78h+arg_30]
0x18003f051  mov     r10, rcx
0x18003f054  mov     rsi, [rsp+78h+lpOutputString]
0x18003f05c  mov     r12, r9
0x18003f05f  mov     r13, r8
0x18003f062  mov     ecx, r15d
0x18003f065  mov     [rsi], ax
0x18003f068  mov     rax, [rsp+78h+arg_60]
0x18003f070  mov     byte ptr [rax], 0
0x18003f073  mov     edi, [r14]
0x18003f076  mov     [rbx+8], edi
0x18003f079  mov     eax, [r14+4]
0x18003f07d  mov     [rbx+0Ch], eax
0x18003f080  test    r15d, r15d
0x18003f083  jz      short loc_18003F0EB
0x18003f085  sub     ecx, 1
0x18003f088  jz      short loc_18003F0E2
0x18003f08a  sub     ecx, 1
0x18003f08d  jz      short loc_18003F09D
0x18003f08f  cmp     ecx, 1
0x18003f092  jnz     short loc_18003F0F4
0x18003f094  mov     ecx, edi; this
0x18003f096  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003f09b  jmp     short loc_18003F0F2
0x18003f09d  test    edi, edi
0x18003f09f  js      short loc_18003F0D9
0x18003f0a1  mov     rax, [rsp+78h+arg_28]
0x18003f0a9  mov     edi, 8007029Ch
0x18003f0ae  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003f0b2  mov     rcx, r10; int
0x18003f0b5  mov     [rsp+78h+var_50], rax; __int64
0x18003f0ba  mov     rax, [rsp+78h+arg_20]
0x18003f0c2  mov     [rsp+78h+var_58], rax; __int64
0x18003f0c7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003f0cc  mov     ecx, edi; this
0x18003f0ce  mov     [rbx+8], edi
0x18003f0d1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003f0d6  mov     [rbx+0Ch], eax
0x18003f0d9  mov     ecx, edi; this
0x18003f0db  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003f0e0  jmp     short loc_18003F0F2
0x18003f0e2  mov     ecx, edi; this
0x18003f0e4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003f0e9  jmp     short loc_18003F0F2
0x18003f0eb  mov     ecx, edi; this
0x18003f0ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003f0f2  mov     ebp, eax
0x18003f0f4  mov     eax, [rsp+78h+arg_70]
0x18003f0fb  mov     [rbx+4], eax
0x18003f0fe  mov     [rbx], r15d
0x18003f101  cmp     dword ptr [r14+8], 1
0x18003f106  jnz     short loc_18003F10E
0x18003f108  or      eax, 8
0x18003f10b  mov     [rbx+4], eax
0x18003f10e  mov     eax, 1
0x18003f113  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003f11b  inc     eax
0x18003f11d  xor     edi, edi
0x18003f11f  mov     [rbx+10h], eax
0x18003f122  mov     rax, [rsp+78h+arg_40]
0x18003f12a  test    rax, rax
0x18003f12d  jz      short loc_18003F134
0x18003f12f  cmp     [rax], di
0x18003f132  jnz     short loc_18003F137
0x18003f134  mov     rax, rdi
0x18003f137  mov     [rbx+18h], rax
0x18003f13b  call    cs:__imp_GetCurrentThreadId
0x18003f141  mov     [rbx+38h], r13
0x18003f145  xorps   xmm0, xmm0
0x18003f148  mov     [rbx+20h], eax
0x18003f14b  mov     eax, [rsp+78h+arg_8]
0x18003f152  mov     [rbx+40h], eax
0x18003f155  mov     rax, [rsp+78h+arg_20]
0x18003f15d  mov     [rbx+28h], rax
0x18003f161  mov     rax, [rsp+78h+arg_28]
0x18003f169  mov     [rbx+88h], rax
0x18003f170  mov     rax, [rsp+78h+arg_0]
0x18003f178  mov     [rbx+90h], rax
0x18003f17f  xor     eax, eax
0x18003f181  mov     [rbx+44h], ebp
0x18003f184  mov     [rbx+30h], r12
0x18003f188  mov     [rbx+48h], rdi
0x18003f18c  movups  xmmword ptr [rbx+68h], xmm0
0x18003f190  mov     [rbx+78h], rax
0x18003f194  movups  xmmword ptr [rbx+50h], xmm0
0x18003f198  mov     [rbx+60h], rax
0x18003f19c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003f1a3  test    rax, rax
0x18003f1a6  jz      short loc_18003F1AF
0x18003f1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1ad  jmp     short loc_18003F1B2
0x18003f1af  mov     rax, rdi
0x18003f1b2  mov     [rbx+80h], rax
0x18003f1b9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003f1c0  test    rax, rax
0x18003f1c3  jz      short loc_18003F1CD
0x18003f1c5  mov     rcx, rbx
0x18003f1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1cd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003f1d4  test    rax, rax
0x18003f1d7  jz      short loc_18003F1EF
0x18003f1d9  mov     rdx, [rsp+78h+arg_60]
0x18003f1e1  mov     r8d, 400h
0x18003f1e7  mov     rcx, rbx
0x18003f1ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1ef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003f1f6  test    rax, rax
0x18003f1f9  jz      short loc_18003F203
0x18003f1fb  mov     rcx, rbx
0x18003f1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f203  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003f20a  test    rax, rax
0x18003f20d  jz      short loc_18003F21D
0x18003f20f  test    byte ptr [rbx+4], 2
0x18003f213  jnz     short loc_18003F21D
0x18003f215  mov     rcx, rbx
0x18003f218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f21d  cmp     [rbx+8], edi
0x18003f220  jl      short loc_18003F23C
0x18003f222  cmp     r15d, 3
0x18003f226  jnz     loc_18003F30A
0x18003f22c  mov     ecx, 8000FFFFh; this
0x18003f231  mov     [rbx+8], ecx
0x18003f234  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003f239  mov     [rbx+0Ch], eax
0x18003f23c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18003f243  jnz     short loc_18003F264
0x18003f245  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003f24c  test    rax, rax
0x18003f24f  jz      short loc_18003F25A
0x18003f251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f256  test    al, al
0x18003f258  jmp     short loc_18003F262
0x18003f25a  call    cs:__imp_IsDebuggerPresent
0x18003f260  test    eax, eax
0x18003f262  jz      short loc_18003F26A
0x18003f264  test    byte ptr [rbx+4], 2
0x18003f268  jz      short loc_18003F28E
0x18003f26a  mov     rax, cs:g_pfnResultLoggingCallback
0x18003f271  test    rax, rax
0x18003f274  jz      short loc_18003F2D2
0x18003f276  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003f27d  jnz     short loc_18003F2D2
0x18003f27f  xor     r8d, r8d
0x18003f282  xor     edx, edx
0x18003f284  mov     rcx, rbx
0x18003f287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f28c  jmp     short loc_18003F2D2
0x18003f28e  mov     rax, cs:g_pfnResultLoggingCallback
0x18003f295  mov     ebp, 800h
0x18003f29a  test    rax, rax
0x18003f29d  jz      short loc_18003F2B6
0x18003f29f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003f2a6  jnz     short loc_18003F2B6
0x18003f2a8  mov     r8d, ebp
0x18003f2ab  mov     rdx, rsi
0x18003f2ae  mov     rcx, rbx
0x18003f2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2b6  cmp     [rsi], di
0x18003f2b9  jnz     short loc_18003F2C9
0x18003f2bb  mov     r8, rbx; unsigned __int64
0x18003f2be  mov     rdx, rbp; unsigned __int16 *
0x18003f2c1  mov     rcx, rsi; this
0x18003f2c4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003f2c9  mov     rcx, rsi; lpOutputString
0x18003f2cc  call    cs:__imp_OutputDebugStringW
0x18003f2d2  test    byte ptr [rbx+4], 4
0x18003f2d6  jnz     short loc_18003F2E1
0x18003f2d8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003f2df  jz      short loc_18003F2F2
0x18003f2e1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003f2e8  test    rax, rax
0x18003f2eb  jz      short loc_18003F2F2
0x18003f2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2f2  mov     rbx, [rsp+78h+arg_10]
0x18003f2fa  add     rsp, 40h
0x18003f2fe  pop     r15
0x18003f300  pop     r14
0x18003f302  pop     r13
0x18003f304  pop     r12
0x18003f306  pop     rdi
0x18003f307  pop     rsi
0x18003f308  pop     rbp
0x18003f309  retn
0x18003f30a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
