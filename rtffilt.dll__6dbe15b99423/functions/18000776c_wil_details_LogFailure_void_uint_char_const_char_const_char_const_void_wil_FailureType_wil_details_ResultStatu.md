# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000776c`
- end: `0x180007a65`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800038f4`

## callees

- `0x18000304c`
- `0x180006b04`
- `0x1800074c0`
- `0x18000776c`
- `0x1800085e0`
- `0x180008600`
- `0x18000872c`
- `0x180008748`
- `0x18000c558`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000788f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000788f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800079ae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800079ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007a20`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007a20`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x18000776c  mov     [rsp+arg_10], rbx
0x180007771  mov     [rsp+arg_8], edx
0x180007775  mov     [rsp+arg_0], rcx
0x18000777a  push    rbp
0x18000777b  push    rsi
0x18000777c  push    rdi
0x18000777d  push    r12
0x18000777f  push    r13
0x180007781  push    r14
0x180007783  push    r15
0x180007785  sub     rsp, 40h
0x180007789  mov     r12, r9
0x18000778c  mov     r13, r8
0x18000778f  mov     r10, rcx
0x180007792  xor     eax, eax
0x180007794  mov     rsi, [rsp+78h+lpOutputString]
0x18000779c  mov     [rsi], ax
0x18000779f  mov     rax, [rsp+78h+arg_60]
0x1800077a7  mov     byte ptr [rax], 0
0x1800077aa  mov     r14, [rsp+78h+arg_38]
0x1800077b2  mov     edi, [r14]
0x1800077b5  mov     rbx, [rsp+78h+arg_78]
0x1800077bd  mov     [rbx+8], edi
0x1800077c0  mov     eax, [r14+4]
0x1800077c4  mov     [rbx+0Ch], eax
0x1800077c7  xor     ebp, ebp
0x1800077c9  mov     r15d, [rsp+78h+arg_30]
0x1800077d1  mov     ecx, r15d
0x1800077d4  test    r15d, r15d
0x1800077d7  jz      short loc_18000783F
0x1800077d9  sub     ecx, 1
0x1800077dc  jz      short loc_180007836
0x1800077de  sub     ecx, 1
0x1800077e1  jz      short loc_1800077F1
0x1800077e3  cmp     ecx, 1
0x1800077e6  jnz     short loc_180007848
0x1800077e8  mov     ecx, edi; this
0x1800077ea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800077ef  jmp     short loc_180007846
0x1800077f1  test    edi, edi
0x1800077f3  js      short loc_18000782D
0x1800077f5  mov     edi, 8007029Ch
0x1800077fa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800077fe  mov     rax, [rsp+78h+arg_28]
0x180007806  mov     [rsp+78h+var_50], rax; __int64
0x18000780b  mov     rax, [rsp+78h+arg_20]
0x180007813  mov     [rsp+78h+var_58], rax; __int64
0x180007818  mov     rcx, r10; int
0x18000781b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007820  mov     [rbx+8], edi
0x180007823  mov     ecx, edi; this
0x180007825  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000782a  mov     [rbx+0Ch], eax
0x18000782d  mov     ecx, edi; this
0x18000782f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007834  jmp     short loc_180007846
0x180007836  mov     ecx, edi; this
0x180007838  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000783d  jmp     short loc_180007846
0x18000783f  mov     ecx, edi; this
0x180007841  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007846  mov     ebp, eax
0x180007848  mov     [rbx], r15d
0x18000784b  mov     eax, [rsp+78h+arg_70]
0x180007852  mov     [rbx+4], eax
0x180007855  cmp     dword ptr [r14+8], 1
0x18000785a  jnz     short loc_180007862
0x18000785c  or      eax, 8
0x18000785f  mov     [rbx+4], eax
0x180007862  mov     eax, 1
0x180007867  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000786f  inc     eax
0x180007871  mov     [rbx+10h], eax
0x180007874  mov     rax, [rsp+78h+arg_40]
0x18000787c  xor     edi, edi
0x18000787e  test    rax, rax
0x180007881  jz      short loc_180007888
0x180007883  cmp     [rax], di
0x180007886  jnz     short loc_18000788B
0x180007888  mov     rax, rdi
0x18000788b  mov     [rbx+18h], rax
0x18000788f  call    cs:__imp_GetCurrentThreadId
0x180007895  mov     [rbx+20h], eax
0x180007898  mov     [rbx+38h], r13
0x18000789c  mov     eax, [rsp+78h+arg_8]
0x1800078a3  mov     [rbx+40h], eax
0x1800078a6  mov     [rbx+44h], ebp
0x1800078a9  mov     rax, [rsp+78h+arg_20]
0x1800078b1  mov     [rbx+28h], rax
0x1800078b5  mov     [rbx+30h], r12
0x1800078b9  mov     rax, [rsp+78h+arg_28]
0x1800078c1  mov     [rbx+88h], rax
0x1800078c8  mov     rax, [rsp+78h+arg_0]
0x1800078d0  mov     [rbx+90h], rax
0x1800078d7  mov     [rbx+48h], rdi
0x1800078db  xorps   xmm0, xmm0
0x1800078de  xor     eax, eax
0x1800078e0  movups  xmmword ptr [rbx+68h], xmm0
0x1800078e4  mov     [rbx+78h], rax
0x1800078e8  movups  xmmword ptr [rbx+50h], xmm0
0x1800078ec  mov     [rbx+60h], rax
0x1800078f0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800078f7  test    rax, rax
0x1800078fa  jz      short loc_180007903
0x1800078fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007901  jmp     short loc_180007906
0x180007903  mov     rax, rdi
0x180007906  mov     [rbx+80h], rax
0x18000790d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007914  test    rax, rax
0x180007917  jz      short loc_180007921
0x180007919  mov     rcx, rbx
0x18000791c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007921  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007928  test    rax, rax
0x18000792b  jz      short loc_180007943
0x18000792d  mov     r8d, 400h
0x180007933  mov     rdx, [rsp+78h+arg_60]
0x18000793b  mov     rcx, rbx
0x18000793e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007943  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000794a  test    rax, rax
0x18000794d  jz      short loc_180007957
0x18000794f  mov     rcx, rbx
0x180007952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007957  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000795e  test    rax, rax
0x180007961  jz      short loc_180007971
0x180007963  test    byte ptr [rbx+4], 2
0x180007967  jnz     short loc_180007971
0x180007969  mov     rcx, rbx
0x18000796c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007971  cmp     [rbx+8], edi
0x180007974  jl      short loc_180007990
0x180007976  cmp     r15d, 3
0x18000797a  jnz     loc_180007A5F
0x180007980  mov     ecx, 8000FFFFh; this
0x180007985  mov     [rbx+8], ecx
0x180007988  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000798d  mov     [rbx+0Ch], eax
0x180007990  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007997  jnz     short loc_1800079B8
0x180007999  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800079a0  test    rax, rax
0x1800079a3  jz      short loc_1800079AE
0x1800079a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079aa  test    al, al
0x1800079ac  jmp     short loc_1800079B6
0x1800079ae  call    cs:__imp_IsDebuggerPresent
0x1800079b4  test    eax, eax
0x1800079b6  jz      short loc_1800079BE
0x1800079b8  test    byte ptr [rbx+4], 2
0x1800079bc  jz      short loc_1800079E2
0x1800079be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800079c5  test    rax, rax
0x1800079c8  jz      short loc_180007A26
0x1800079ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800079d1  jnz     short loc_180007A26
0x1800079d3  xor     r8d, r8d
0x1800079d6  xor     edx, edx
0x1800079d8  mov     rcx, rbx
0x1800079db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e0  jmp     short loc_180007A26
0x1800079e2  mov     ebp, 800h
0x1800079e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800079ee  test    rax, rax
0x1800079f1  jz      short loc_180007A0A
0x1800079f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800079fa  jnz     short loc_180007A0A
0x1800079fc  mov     r8d, ebp
0x1800079ff  mov     rdx, rsi
0x180007a02  mov     rcx, rbx
0x180007a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a0a  cmp     [rsi], di
0x180007a0d  jnz     short loc_180007A1D
0x180007a0f  mov     r8, rbx; unsigned __int64
0x180007a12  mov     rdx, rbp; wchar_t *
0x180007a15  mov     rcx, rsi; this
0x180007a18  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180007a1d  mov     rcx, rsi; lpOutputString
0x180007a20  call    cs:__imp_OutputDebugStringW
0x180007a26  test    byte ptr [rbx+4], 4
0x180007a2a  jnz     short loc_180007A35
0x180007a2c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007a33  jz      short loc_180007A47
0x180007a35  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007a3c  test    rax, rax
0x180007a3f  jz      short loc_180007A47
0x180007a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a46  nop
0x180007a47  mov     rbx, [rsp+78h+arg_10]
0x180007a4f  add     rsp, 40h
0x180007a53  pop     r15
0x180007a55  pop     r14
0x180007a57  pop     r13
0x180007a59  pop     r12
0x180007a5b  pop     rdi
0x180007a5c  pop     rsi
0x180007a5d  pop     rbp
0x180007a5e  retn
0x180007a5f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
