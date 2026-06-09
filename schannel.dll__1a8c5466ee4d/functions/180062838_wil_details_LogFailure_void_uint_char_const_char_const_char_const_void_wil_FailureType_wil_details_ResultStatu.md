# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180062838`
- end: `0x180062b2c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800614b0`
- `0x180061560`
- `0x180061650`

## callees

- `0x180054e3c`
- `0x180061404`
- `0x180062104`
- `0x180062838`
- `0x180063424`
- `0x180063440`
- `0x180063454`
- `0x180063470`
- `0x180067d7c`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006295b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006295b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180062a7c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180062a7c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180062aee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180062aee`

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
0x180062838  mov     [rsp+arg_10], rbx
0x18006283d  mov     [rsp+arg_8], edx
0x180062841  mov     [rsp+arg_0], rcx
0x180062846  push    rbp
0x180062847  push    rsi
0x180062848  push    rdi
0x180062849  push    r12
0x18006284b  push    r13
0x18006284d  push    r14
0x18006284f  push    r15
0x180062851  sub     rsp, 40h
0x180062855  mov     r14, [rsp+78h+arg_38]
0x18006285d  xor     eax, eax
0x18006285f  mov     rbx, [rsp+78h+arg_78]
0x180062867  xor     ebp, ebp
0x180062869  mov     r15d, [rsp+78h+arg_30]
0x180062871  mov     r10, rcx
0x180062874  mov     rsi, [rsp+78h+lpOutputString]
0x18006287c  mov     r12, r9
0x18006287f  mov     r13, r8
0x180062882  mov     ecx, r15d
0x180062885  mov     [rsi], ax
0x180062888  mov     rax, [rsp+78h+arg_60]
0x180062890  mov     byte ptr [rax], 0
0x180062893  mov     edi, [r14]
0x180062896  mov     [rbx+8], edi
0x180062899  mov     eax, [r14+4]
0x18006289d  mov     [rbx+0Ch], eax
0x1800628a0  test    r15d, r15d
0x1800628a3  jz      short loc_18006290B
0x1800628a5  sub     ecx, 1
0x1800628a8  jz      short loc_180062902
0x1800628aa  sub     ecx, 1
0x1800628ad  jz      short loc_1800628BD
0x1800628af  cmp     ecx, 1
0x1800628b2  jnz     short loc_180062914
0x1800628b4  mov     ecx, edi; this
0x1800628b6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800628bb  jmp     short loc_180062912
0x1800628bd  test    edi, edi
0x1800628bf  js      short loc_1800628F9
0x1800628c1  mov     rax, [rsp+78h+arg_28]
0x1800628c9  mov     edi, 8007029Ch
0x1800628ce  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800628d2  mov     rcx, r10; int
0x1800628d5  mov     [rsp+78h+var_50], rax; __int64
0x1800628da  mov     rax, [rsp+78h+arg_20]
0x1800628e2  mov     [rsp+78h+var_58], rax; __int64
0x1800628e7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800628ec  mov     ecx, edi; this
0x1800628ee  mov     [rbx+8], edi
0x1800628f1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800628f6  mov     [rbx+0Ch], eax
0x1800628f9  mov     ecx, edi; this
0x1800628fb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180062900  jmp     short loc_180062912
0x180062902  mov     ecx, edi; this
0x180062904  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180062909  jmp     short loc_180062912
0x18006290b  mov     ecx, edi; this
0x18006290d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180062912  mov     ebp, eax
0x180062914  mov     eax, [rsp+78h+arg_70]
0x18006291b  mov     [rbx+4], eax
0x18006291e  mov     [rbx], r15d
0x180062921  cmp     dword ptr [r14+8], 1
0x180062926  jnz     short loc_18006292E
0x180062928  or      eax, 8
0x18006292b  mov     [rbx+4], eax
0x18006292e  mov     eax, 1
0x180062933  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18006293b  inc     eax
0x18006293d  xor     edi, edi
0x18006293f  mov     [rbx+10h], eax
0x180062942  mov     rax, [rsp+78h+arg_40]
0x18006294a  test    rax, rax
0x18006294d  jz      short loc_180062954
0x18006294f  cmp     [rax], di
0x180062952  jnz     short loc_180062957
0x180062954  mov     rax, rdi
0x180062957  mov     [rbx+18h], rax
0x18006295b  call    cs:__imp_GetCurrentThreadId
0x180062961  mov     [rbx+38h], r13
0x180062965  xorps   xmm0, xmm0
0x180062968  mov     [rbx+20h], eax
0x18006296b  mov     eax, [rsp+78h+arg_8]
0x180062972  mov     [rbx+40h], eax
0x180062975  mov     rax, [rsp+78h+arg_20]
0x18006297d  mov     [rbx+28h], rax
0x180062981  mov     rax, [rsp+78h+arg_28]
0x180062989  mov     [rbx+88h], rax
0x180062990  mov     rax, [rsp+78h+arg_0]
0x180062998  mov     [rbx+90h], rax
0x18006299f  xor     eax, eax
0x1800629a1  mov     [rbx+44h], ebp
0x1800629a4  mov     [rbx+30h], r12
0x1800629a8  mov     [rbx+48h], rdi
0x1800629ac  movups  xmmword ptr [rbx+68h], xmm0
0x1800629b0  mov     [rbx+78h], rax
0x1800629b4  movups  xmmword ptr [rbx+50h], xmm0
0x1800629b8  mov     [rbx+60h], rax
0x1800629bc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800629c3  test    rax, rax
0x1800629c6  jz      short loc_1800629CF
0x1800629c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629cd  jmp     short loc_1800629D2
0x1800629cf  mov     rax, rdi
0x1800629d2  mov     [rbx+80h], rax
0x1800629d9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800629e0  test    rax, rax
0x1800629e3  jz      short loc_1800629ED
0x1800629e5  mov     rcx, rbx
0x1800629e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629ed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800629f4  test    rax, rax
0x1800629f7  jz      short loc_180062A0F
0x1800629f9  mov     rdx, [rsp+78h+arg_60]
0x180062a01  mov     r8d, 400h
0x180062a07  mov     rcx, rbx
0x180062a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a0f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180062a16  test    rax, rax
0x180062a19  jz      short loc_180062A23
0x180062a1b  mov     rcx, rbx
0x180062a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a23  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180062a2a  test    rax, rax
0x180062a2d  jz      short loc_180062A3D
0x180062a2f  test    byte ptr [rbx+4], 2
0x180062a33  jnz     short loc_180062A3D
0x180062a35  mov     rcx, rbx
0x180062a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a3d  cmp     [rbx+8], edi
0x180062a40  jl      short loc_180062A5E
0x180062a42  cmp     r15d, 3
0x180062a46  jz      short loc_180062A4E
0x180062a48  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180062a4e  mov     ecx, 8000FFFFh; this
0x180062a53  mov     [rbx+8], ecx
0x180062a56  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180062a5b  mov     [rbx+0Ch], eax
0x180062a5e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180062a65  jnz     short loc_180062A86
0x180062a67  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180062a6e  test    rax, rax
0x180062a71  jz      short loc_180062A7C
0x180062a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a78  test    al, al
0x180062a7a  jmp     short loc_180062A84
0x180062a7c  call    cs:__imp_IsDebuggerPresent
0x180062a82  test    eax, eax
0x180062a84  jz      short loc_180062A8C
0x180062a86  test    byte ptr [rbx+4], 2
0x180062a8a  jz      short loc_180062AB0
0x180062a8c  mov     rax, cs:g_pfnResultLoggingCallback
0x180062a93  test    rax, rax
0x180062a96  jz      short loc_180062AF4
0x180062a98  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180062a9f  jnz     short loc_180062AF4
0x180062aa1  xor     r8d, r8d
0x180062aa4  xor     edx, edx
0x180062aa6  mov     rcx, rbx
0x180062aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062aae  jmp     short loc_180062AF4
0x180062ab0  mov     rax, cs:g_pfnResultLoggingCallback
0x180062ab7  mov     ebp, 800h
0x180062abc  test    rax, rax
0x180062abf  jz      short loc_180062AD8
0x180062ac1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180062ac8  jnz     short loc_180062AD8
0x180062aca  mov     r8d, ebp
0x180062acd  mov     rdx, rsi
0x180062ad0  mov     rcx, rbx
0x180062ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062ad8  cmp     [rsi], di
0x180062adb  jnz     short loc_180062AEB
0x180062add  mov     r8, rbx; unsigned __int64
0x180062ae0  mov     rdx, rbp; unsigned __int16 *
0x180062ae3  mov     rcx, rsi; this
0x180062ae6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180062aeb  mov     rcx, rsi; lpOutputString
0x180062aee  call    cs:__imp_OutputDebugStringW
0x180062af4  test    byte ptr [rbx+4], 4
0x180062af8  jnz     short loc_180062B03
0x180062afa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180062b01  jz      short loc_180062B14
0x180062b03  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180062b0a  test    rax, rax
0x180062b0d  jz      short loc_180062B14
0x180062b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b14  mov     rbx, [rsp+78h+arg_10]
0x180062b1c  add     rsp, 40h
0x180062b20  pop     r15
0x180062b22  pop     r14
0x180062b24  pop     r13
0x180062b26  pop     r12
0x180062b28  pop     rdi
0x180062b29  pop     rsi
0x180062b2a  pop     rbp
0x180062b2b  retn
```
