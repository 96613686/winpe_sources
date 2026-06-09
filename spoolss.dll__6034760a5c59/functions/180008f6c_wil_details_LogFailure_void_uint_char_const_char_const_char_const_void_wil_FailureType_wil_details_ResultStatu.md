# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008f6c`
- end: `0x180009265`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180006920`
- `0x180006c6c`

## callees

- `0x180004c34`
- `0x180006860`
- `0x1800085b4`
- `0x180008f6c`
- `0x180009b90`
- `0x180009bb0`
- `0x180009d00`
- `0x180009d1c`
- `0x18000ba84`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000908f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000908f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800091ae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800091ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009220`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009220`

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
0x180008f6c  mov     [rsp+arg_10], rbx
0x180008f71  mov     [rsp+arg_8], edx
0x180008f75  mov     [rsp+arg_0], rcx
0x180008f7a  push    rbp
0x180008f7b  push    rsi
0x180008f7c  push    rdi
0x180008f7d  push    r12
0x180008f7f  push    r13
0x180008f81  push    r14
0x180008f83  push    r15
0x180008f85  sub     rsp, 40h
0x180008f89  mov     r12, r9
0x180008f8c  mov     r13, r8
0x180008f8f  mov     r10, rcx
0x180008f92  xor     eax, eax
0x180008f94  mov     rsi, [rsp+78h+lpOutputString]
0x180008f9c  mov     [rsi], ax
0x180008f9f  mov     rax, [rsp+78h+arg_60]
0x180008fa7  mov     byte ptr [rax], 0
0x180008faa  mov     r14, [rsp+78h+arg_38]
0x180008fb2  mov     edi, [r14]
0x180008fb5  mov     rbx, [rsp+78h+arg_78]
0x180008fbd  mov     [rbx+8], edi
0x180008fc0  mov     eax, [r14+4]
0x180008fc4  mov     [rbx+0Ch], eax
0x180008fc7  xor     ebp, ebp
0x180008fc9  mov     r15d, [rsp+78h+arg_30]
0x180008fd1  mov     ecx, r15d
0x180008fd4  test    r15d, r15d
0x180008fd7  jz      short loc_18000903F
0x180008fd9  sub     ecx, 1
0x180008fdc  jz      short loc_180009036
0x180008fde  sub     ecx, 1
0x180008fe1  jz      short loc_180008FF1
0x180008fe3  cmp     ecx, 1
0x180008fe6  jnz     short loc_180009048
0x180008fe8  mov     ecx, edi; this
0x180008fea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008fef  jmp     short loc_180009046
0x180008ff1  test    edi, edi
0x180008ff3  js      short loc_18000902D
0x180008ff5  mov     edi, 8007029Ch
0x180008ffa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008ffe  mov     rax, [rsp+78h+arg_28]
0x180009006  mov     [rsp+78h+var_50], rax; __int64
0x18000900b  mov     rax, [rsp+78h+arg_20]
0x180009013  mov     [rsp+78h+var_58], rax; __int64
0x180009018  mov     rcx, r10; int
0x18000901b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009020  mov     [rbx+8], edi
0x180009023  mov     ecx, edi; this
0x180009025  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000902a  mov     [rbx+0Ch], eax
0x18000902d  mov     ecx, edi; this
0x18000902f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009034  jmp     short loc_180009046
0x180009036  mov     ecx, edi; this
0x180009038  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000903d  jmp     short loc_180009046
0x18000903f  mov     ecx, edi; this
0x180009041  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009046  mov     ebp, eax
0x180009048  mov     [rbx], r15d
0x18000904b  mov     eax, [rsp+78h+arg_70]
0x180009052  mov     [rbx+4], eax
0x180009055  cmp     dword ptr [r14+8], 1
0x18000905a  jnz     short loc_180009062
0x18000905c  or      eax, 8
0x18000905f  mov     [rbx+4], eax
0x180009062  mov     eax, 1
0x180009067  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000906f  inc     eax
0x180009071  mov     [rbx+10h], eax
0x180009074  mov     rax, [rsp+78h+arg_40]
0x18000907c  xor     edi, edi
0x18000907e  test    rax, rax
0x180009081  jz      short loc_180009088
0x180009083  cmp     [rax], di
0x180009086  jnz     short loc_18000908B
0x180009088  mov     rax, rdi
0x18000908b  mov     [rbx+18h], rax
0x18000908f  call    cs:__imp_GetCurrentThreadId
0x180009095  mov     [rbx+20h], eax
0x180009098  mov     [rbx+38h], r13
0x18000909c  mov     eax, [rsp+78h+arg_8]
0x1800090a3  mov     [rbx+40h], eax
0x1800090a6  mov     [rbx+44h], ebp
0x1800090a9  mov     rax, [rsp+78h+arg_20]
0x1800090b1  mov     [rbx+28h], rax
0x1800090b5  mov     [rbx+30h], r12
0x1800090b9  mov     rax, [rsp+78h+arg_28]
0x1800090c1  mov     [rbx+88h], rax
0x1800090c8  mov     rax, [rsp+78h+arg_0]
0x1800090d0  mov     [rbx+90h], rax
0x1800090d7  mov     [rbx+48h], rdi
0x1800090db  xorps   xmm0, xmm0
0x1800090de  xor     eax, eax
0x1800090e0  movups  xmmword ptr [rbx+68h], xmm0
0x1800090e4  mov     [rbx+78h], rax
0x1800090e8  movups  xmmword ptr [rbx+50h], xmm0
0x1800090ec  mov     [rbx+60h], rax
0x1800090f0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800090f7  test    rax, rax
0x1800090fa  jz      short loc_180009103
0x1800090fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009101  jmp     short loc_180009106
0x180009103  mov     rax, rdi
0x180009106  mov     [rbx+80h], rax
0x18000910d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009114  test    rax, rax
0x180009117  jz      short loc_180009121
0x180009119  mov     rcx, rbx
0x18000911c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009121  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009128  test    rax, rax
0x18000912b  jz      short loc_180009143
0x18000912d  mov     r8d, 400h
0x180009133  mov     rdx, [rsp+78h+arg_60]
0x18000913b  mov     rcx, rbx
0x18000913e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009143  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000914a  test    rax, rax
0x18000914d  jz      short loc_180009157
0x18000914f  mov     rcx, rbx
0x180009152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009157  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000915e  test    rax, rax
0x180009161  jz      short loc_180009171
0x180009163  test    byte ptr [rbx+4], 2
0x180009167  jnz     short loc_180009171
0x180009169  mov     rcx, rbx
0x18000916c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009171  cmp     [rbx+8], edi
0x180009174  jl      short loc_180009190
0x180009176  cmp     r15d, 3
0x18000917a  jnz     loc_18000925F
0x180009180  mov     ecx, 8000FFFFh; this
0x180009185  mov     [rbx+8], ecx
0x180009188  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000918d  mov     [rbx+0Ch], eax
0x180009190  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009197  jnz     short loc_1800091B8
0x180009199  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800091a0  test    rax, rax
0x1800091a3  jz      short loc_1800091AE
0x1800091a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091aa  test    al, al
0x1800091ac  jmp     short loc_1800091B6
0x1800091ae  call    cs:__imp_IsDebuggerPresent
0x1800091b4  test    eax, eax
0x1800091b6  jz      short loc_1800091BE
0x1800091b8  test    byte ptr [rbx+4], 2
0x1800091bc  jz      short loc_1800091E2
0x1800091be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800091c5  test    rax, rax
0x1800091c8  jz      short loc_180009226
0x1800091ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800091d1  jnz     short loc_180009226
0x1800091d3  xor     r8d, r8d
0x1800091d6  xor     edx, edx
0x1800091d8  mov     rcx, rbx
0x1800091db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091e0  jmp     short loc_180009226
0x1800091e2  mov     ebp, 800h
0x1800091e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800091ee  test    rax, rax
0x1800091f1  jz      short loc_18000920A
0x1800091f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800091fa  jnz     short loc_18000920A
0x1800091fc  mov     r8d, ebp
0x1800091ff  mov     rdx, rsi
0x180009202  mov     rcx, rbx
0x180009205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000920a  cmp     [rsi], di
0x18000920d  jnz     short loc_18000921D
0x18000920f  mov     r8, rbx; unsigned __int64
0x180009212  mov     rdx, rbp; unsigned __int16 *
0x180009215  mov     rcx, rsi; this
0x180009218  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000921d  mov     rcx, rsi; lpOutputString
0x180009220  call    cs:__imp_OutputDebugStringW
0x180009226  test    byte ptr [rbx+4], 4
0x18000922a  jnz     short loc_180009235
0x18000922c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009233  jz      short loc_180009247
0x180009235  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000923c  test    rax, rax
0x18000923f  jz      short loc_180009247
0x180009241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009246  nop
0x180009247  mov     rbx, [rsp+78h+arg_10]
0x18000924f  add     rsp, 40h
0x180009253  pop     r15
0x180009255  pop     r14
0x180009257  pop     r13
0x180009259  pop     r12
0x18000925b  pop     rdi
0x18000925c  pop     rsi
0x18000925d  pop     rbp
0x18000925e  retn
0x18000925f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
