# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800676c0`
- end: `0x1800679b9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18006722c`
- `0x180067330`
- `0x1800675c4`
- `0x1800cfef4`

## callees

- `0x1800676c0`
- `0x1800760f0`
- `0x18007f960`
- `0x180097a94`
- `0x1800983e8`
- `0x180098410`
- `0x180098424`
- `0x180098440`
- `0x180099430`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800677e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800677e7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180067908`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180067908`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006797a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006797a`

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
0x1800676c0  mov     [rsp+arg_10], rbx
0x1800676c5  mov     [rsp+arg_8], edx
0x1800676c9  mov     [rsp+arg_0], rcx
0x1800676ce  push    rbp
0x1800676cf  push    rsi
0x1800676d0  push    rdi
0x1800676d1  push    r12
0x1800676d3  push    r13
0x1800676d5  push    r14
0x1800676d7  push    r15
0x1800676d9  sub     rsp, 40h
0x1800676dd  mov     r12, r9
0x1800676e0  mov     r13, r8
0x1800676e3  mov     r10, rcx
0x1800676e6  xor     eax, eax
0x1800676e8  mov     rsi, [rsp+78h+lpOutputString]
0x1800676f0  mov     [rsi], ax
0x1800676f3  mov     rax, [rsp+78h+arg_60]
0x1800676fb  mov     byte ptr [rax], 0
0x1800676fe  mov     r14, [rsp+78h+arg_38]
0x180067706  mov     edi, [r14]
0x180067709  mov     rbx, [rsp+78h+arg_78]
0x180067711  mov     [rbx+8], edi
0x180067714  mov     eax, [r14+4]
0x180067718  mov     [rbx+0Ch], eax
0x18006771b  xor     ebp, ebp
0x18006771d  mov     r15d, [rsp+78h+arg_30]
0x180067725  mov     ecx, r15d
0x180067728  test    r15d, r15d
0x18006772b  jz      short loc_180067797
0x18006772d  sub     ecx, 1
0x180067730  jz      short loc_18006778E
0x180067732  sub     ecx, 1
0x180067735  jz      short loc_180067745
0x180067737  cmp     ecx, 1
0x18006773a  jnz     short loc_1800677A0
0x18006773c  mov     ecx, edi; this
0x18006773e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180067743  jmp     short loc_18006779E
0x180067745  test    edi, edi
0x180067747  js      short loc_180067785
0x180067749  mov     [rsp+78h+var_40], ebp
0x18006774d  mov     edi, 8007029Ch
0x180067752  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180067756  mov     rax, [rsp+78h+arg_28]
0x18006775e  mov     [rsp+78h+var_50], rax; __int64
0x180067763  mov     rax, [rsp+78h+arg_20]
0x18006776b  mov     [rsp+78h+var_58], rax; __int64
0x180067770  mov     rcx, r10; int
0x180067773  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180067778  mov     [rbx+8], edi
0x18006777b  mov     ecx, edi; this
0x18006777d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180067782  mov     [rbx+0Ch], eax
0x180067785  mov     ecx, edi; this
0x180067787  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18006778c  jmp     short loc_18006779E
0x18006778e  mov     ecx, edi; this
0x180067790  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180067795  jmp     short loc_18006779E
0x180067797  mov     ecx, edi; this
0x180067799  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18006779e  mov     ebp, eax
0x1800677a0  mov     [rbx], r15d
0x1800677a3  mov     eax, [rsp+78h+arg_70]
0x1800677aa  mov     [rbx+4], eax
0x1800677ad  cmp     dword ptr [r14+8], 1
0x1800677b2  jnz     short loc_1800677BA
0x1800677b4  or      eax, 8
0x1800677b7  mov     [rbx+4], eax
0x1800677ba  mov     eax, 1
0x1800677bf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800677c7  inc     eax
0x1800677c9  mov     [rbx+10h], eax
0x1800677cc  mov     rax, [rsp+78h+arg_40]
0x1800677d4  xor     edi, edi
0x1800677d6  test    rax, rax
0x1800677d9  jz      short loc_1800677E0
0x1800677db  cmp     [rax], di
0x1800677de  jnz     short loc_1800677E3
0x1800677e0  mov     rax, rdi
0x1800677e3  mov     [rbx+18h], rax
0x1800677e7  call    cs:__imp_GetCurrentThreadId
0x1800677ed  mov     [rbx+20h], eax
0x1800677f0  mov     [rbx+38h], r13
0x1800677f4  mov     eax, [rsp+78h+arg_8]
0x1800677fb  mov     [rbx+40h], eax
0x1800677fe  mov     [rbx+44h], ebp
0x180067801  mov     rax, [rsp+78h+arg_20]
0x180067809  mov     [rbx+28h], rax
0x18006780d  mov     [rbx+30h], r12
0x180067811  mov     rax, [rsp+78h+arg_28]
0x180067819  mov     [rbx+88h], rax
0x180067820  mov     rax, [rsp+78h+arg_0]
0x180067828  mov     [rbx+90h], rax
0x18006782f  mov     [rbx+48h], rdi
0x180067833  xorps   xmm0, xmm0
0x180067836  xor     eax, eax
0x180067838  movups  xmmword ptr [rbx+68h], xmm0
0x18006783c  mov     [rbx+78h], rax
0x180067840  movups  xmmword ptr [rbx+50h], xmm0
0x180067844  mov     [rbx+60h], rax
0x180067848  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18006784f  test    rax, rax
0x180067852  jz      short loc_18006785B
0x180067854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067859  jmp     short loc_18006785E
0x18006785b  mov     rax, rdi
0x18006785e  mov     [rbx+80h], rax
0x180067865  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18006786c  test    rax, rax
0x18006786f  jz      short loc_180067879
0x180067871  mov     rcx, rbx
0x180067874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067879  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180067880  test    rax, rax
0x180067883  jz      short loc_18006789B
0x180067885  mov     r8d, 400h
0x18006788b  mov     rdx, [rsp+78h+arg_60]
0x180067893  mov     rcx, rbx
0x180067896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006789b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800678a2  test    rax, rax
0x1800678a5  jz      short loc_1800678AF
0x1800678a7  mov     rcx, rbx
0x1800678aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800678af  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800678b6  test    rax, rax
0x1800678b9  jz      short loc_1800678C9
0x1800678bb  test    byte ptr [rbx+4], 2
0x1800678bf  jnz     short loc_1800678C9
0x1800678c1  mov     rcx, rbx
0x1800678c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800678c9  cmp     [rbx+8], edi
0x1800678cc  jl      short loc_1800678EA
0x1800678ce  cmp     r15d, 3
0x1800678d2  jz      short loc_1800678DA
0x1800678d4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800678da  mov     ecx, 8000FFFFh; this
0x1800678df  mov     [rbx+8], ecx
0x1800678e2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800678e7  mov     [rbx+0Ch], eax
0x1800678ea  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800678f1  jnz     short loc_180067912
0x1800678f3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800678fa  test    rax, rax
0x1800678fd  jz      short loc_180067908
0x1800678ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067904  test    al, al
0x180067906  jmp     short loc_180067910
0x180067908  call    cs:__imp_IsDebuggerPresent
0x18006790e  test    eax, eax
0x180067910  jz      short loc_180067918
0x180067912  test    byte ptr [rbx+4], 2
0x180067916  jz      short loc_18006793C
0x180067918  mov     rax, cs:g_pfnResultLoggingCallback
0x18006791f  test    rax, rax
0x180067922  jz      short loc_180067980
0x180067924  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18006792b  jnz     short loc_180067980
0x18006792d  xor     r8d, r8d
0x180067930  xor     edx, edx
0x180067932  mov     rcx, rbx
0x180067935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006793a  jmp     short loc_180067980
0x18006793c  mov     ebp, 800h
0x180067941  mov     rax, cs:g_pfnResultLoggingCallback
0x180067948  test    rax, rax
0x18006794b  jz      short loc_180067964
0x18006794d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180067954  jnz     short loc_180067964
0x180067956  mov     r8d, ebp
0x180067959  mov     rdx, rsi
0x18006795c  mov     rcx, rbx
0x18006795f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067964  cmp     [rsi], di
0x180067967  jnz     short loc_180067977
0x180067969  mov     r8, rbx; unsigned __int64
0x18006796c  mov     rdx, rbp; unsigned __int16 *
0x18006796f  mov     rcx, rsi; this
0x180067972  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180067977  mov     rcx, rsi; lpOutputString
0x18006797a  call    cs:__imp_OutputDebugStringW
0x180067980  test    byte ptr [rbx+4], 4
0x180067984  jnz     short loc_18006798F
0x180067986  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18006798d  jz      short loc_1800679A1
0x18006798f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180067996  test    rax, rax
0x180067999  jz      short loc_1800679A1
0x18006799b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800679a0  nop
0x1800679a1  mov     rbx, [rsp+78h+arg_10]
0x1800679a9  add     rsp, 40h
0x1800679ad  pop     r15
0x1800679af  pop     r14
0x1800679b1  pop     r13
0x1800679b3  pop     r12
0x1800679b5  pop     rdi
0x1800679b6  pop     rsi
0x1800679b7  pop     rbp
0x1800679b8  retn
```
