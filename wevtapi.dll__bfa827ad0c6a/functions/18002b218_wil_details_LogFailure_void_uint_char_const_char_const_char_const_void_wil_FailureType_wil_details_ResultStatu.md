# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002b218`
- end: `0x18002b50d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18002963c`
- `0x1800296ec`
- `0x1800297e0`

## callees

- `0x180023e80`
- `0x180029590`
- `0x18002a8f4`
- `0x18002b218`
- `0x18002be04`
- `0x18002be20`
- `0x18002bedc`
- `0x18002bef8`
- `0x18002d488`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b33b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b33b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b45c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b45c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002b4ce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002b4ce`

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
0x18002b218  mov     [rsp+arg_10], rbx
0x18002b21d  mov     [rsp+arg_8], edx
0x18002b221  mov     [rsp+arg_0], rcx
0x18002b226  push    rbp
0x18002b227  push    rsi
0x18002b228  push    rdi
0x18002b229  push    r12
0x18002b22b  push    r13
0x18002b22d  push    r14
0x18002b22f  push    r15
0x18002b231  sub     rsp, 40h
0x18002b235  mov     r12, r9
0x18002b238  mov     r13, r8
0x18002b23b  mov     r10, rcx
0x18002b23e  xor     eax, eax
0x18002b240  mov     rsi, [rsp+78h+lpOutputString]
0x18002b248  mov     [rsi], ax
0x18002b24b  mov     rax, [rsp+78h+arg_60]
0x18002b253  mov     byte ptr [rax], 0
0x18002b256  mov     r14, [rsp+78h+arg_38]
0x18002b25e  mov     edi, [r14]
0x18002b261  mov     rbx, [rsp+78h+arg_78]
0x18002b269  mov     [rbx+8], edi
0x18002b26c  mov     eax, [r14+4]
0x18002b270  mov     [rbx+0Ch], eax
0x18002b273  xor     ebp, ebp
0x18002b275  mov     r15d, [rsp+78h+arg_30]
0x18002b27d  mov     ecx, r15d
0x18002b280  test    r15d, r15d
0x18002b283  jz      short loc_18002B2EB
0x18002b285  sub     ecx, 1
0x18002b288  jz      short loc_18002B2E2
0x18002b28a  sub     ecx, 1
0x18002b28d  jz      short loc_18002B29D
0x18002b28f  cmp     ecx, 1
0x18002b292  jnz     short loc_18002B2F4
0x18002b294  mov     ecx, edi; this
0x18002b296  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002b29b  jmp     short loc_18002B2F2
0x18002b29d  test    edi, edi
0x18002b29f  js      short loc_18002B2D9
0x18002b2a1  mov     edi, 8007029Ch
0x18002b2a6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18002b2aa  mov     rax, [rsp+78h+arg_28]
0x18002b2b2  mov     [rsp+78h+var_50], rax; __int64
0x18002b2b7  mov     rax, [rsp+78h+arg_20]
0x18002b2bf  mov     [rsp+78h+var_58], rax; __int64
0x18002b2c4  mov     rcx, r10; int
0x18002b2c7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002b2cc  mov     [rbx+8], edi
0x18002b2cf  mov     ecx, edi; this
0x18002b2d1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002b2d6  mov     [rbx+0Ch], eax
0x18002b2d9  mov     ecx, edi; this
0x18002b2db  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002b2e0  jmp     short loc_18002B2F2
0x18002b2e2  mov     ecx, edi; this
0x18002b2e4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002b2e9  jmp     short loc_18002B2F2
0x18002b2eb  mov     ecx, edi; this
0x18002b2ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002b2f2  mov     ebp, eax
0x18002b2f4  mov     [rbx], r15d
0x18002b2f7  mov     eax, [rsp+78h+arg_70]
0x18002b2fe  mov     [rbx+4], eax
0x18002b301  cmp     dword ptr [r14+8], 1
0x18002b306  jnz     short loc_18002B30E
0x18002b308  or      eax, 8
0x18002b30b  mov     [rbx+4], eax
0x18002b30e  mov     eax, 1
0x18002b313  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002b31b  inc     eax
0x18002b31d  mov     [rbx+10h], eax
0x18002b320  mov     rax, [rsp+78h+arg_40]
0x18002b328  xor     edi, edi
0x18002b32a  test    rax, rax
0x18002b32d  jz      short loc_18002B334
0x18002b32f  cmp     [rax], di
0x18002b332  jnz     short loc_18002B337
0x18002b334  mov     rax, rdi
0x18002b337  mov     [rbx+18h], rax
0x18002b33b  call    cs:__imp_GetCurrentThreadId
0x18002b341  mov     [rbx+20h], eax
0x18002b344  mov     [rbx+38h], r13
0x18002b348  mov     eax, [rsp+78h+arg_8]
0x18002b34f  mov     [rbx+40h], eax
0x18002b352  mov     [rbx+44h], ebp
0x18002b355  mov     rax, [rsp+78h+arg_20]
0x18002b35d  mov     [rbx+28h], rax
0x18002b361  mov     [rbx+30h], r12
0x18002b365  mov     rax, [rsp+78h+arg_28]
0x18002b36d  mov     [rbx+88h], rax
0x18002b374  mov     rax, [rsp+78h+arg_0]
0x18002b37c  mov     [rbx+90h], rax
0x18002b383  mov     [rbx+48h], rdi
0x18002b387  xorps   xmm0, xmm0
0x18002b38a  xor     eax, eax
0x18002b38c  movups  xmmword ptr [rbx+68h], xmm0
0x18002b390  mov     [rbx+78h], rax
0x18002b394  movups  xmmword ptr [rbx+50h], xmm0
0x18002b398  mov     [rbx+60h], rax
0x18002b39c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002b3a3  test    rax, rax
0x18002b3a6  jz      short loc_18002B3AF
0x18002b3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3ad  jmp     short loc_18002B3B2
0x18002b3af  mov     rax, rdi
0x18002b3b2  mov     [rbx+80h], rax
0x18002b3b9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002b3c0  test    rax, rax
0x18002b3c3  jz      short loc_18002B3CD
0x18002b3c5  mov     rcx, rbx
0x18002b3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3cd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002b3d4  test    rax, rax
0x18002b3d7  jz      short loc_18002B3EF
0x18002b3d9  mov     r8d, 400h
0x18002b3df  mov     rdx, [rsp+78h+arg_60]
0x18002b3e7  mov     rcx, rbx
0x18002b3ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3ef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002b3f6  test    rax, rax
0x18002b3f9  jz      short loc_18002B403
0x18002b3fb  mov     rcx, rbx
0x18002b3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b403  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002b40a  test    rax, rax
0x18002b40d  jz      short loc_18002B41D
0x18002b40f  test    byte ptr [rbx+4], 2
0x18002b413  jnz     short loc_18002B41D
0x18002b415  mov     rcx, rbx
0x18002b418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b41d  cmp     [rbx+8], edi
0x18002b420  jl      short loc_18002B43E
0x18002b422  cmp     r15d, 3
0x18002b426  jz      short loc_18002B42E
0x18002b428  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002b42e  mov     ecx, 8000FFFFh; this
0x18002b433  mov     [rbx+8], ecx
0x18002b436  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002b43b  mov     [rbx+0Ch], eax
0x18002b43e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002b445  jnz     short loc_18002B466
0x18002b447  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002b44e  test    rax, rax
0x18002b451  jz      short loc_18002B45C
0x18002b453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b458  test    al, al
0x18002b45a  jmp     short loc_18002B464
0x18002b45c  call    cs:__imp_IsDebuggerPresent
0x18002b462  test    eax, eax
0x18002b464  jz      short loc_18002B46C
0x18002b466  test    byte ptr [rbx+4], 2
0x18002b46a  jz      short loc_18002B490
0x18002b46c  mov     rax, cs:g_pfnResultLoggingCallback
0x18002b473  test    rax, rax
0x18002b476  jz      short loc_18002B4D4
0x18002b478  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002b47f  jnz     short loc_18002B4D4
0x18002b481  xor     r8d, r8d
0x18002b484  xor     edx, edx
0x18002b486  mov     rcx, rbx
0x18002b489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b48e  jmp     short loc_18002B4D4
0x18002b490  mov     ebp, 800h
0x18002b495  mov     rax, cs:g_pfnResultLoggingCallback
0x18002b49c  test    rax, rax
0x18002b49f  jz      short loc_18002B4B8
0x18002b4a1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002b4a8  jnz     short loc_18002B4B8
0x18002b4aa  mov     r8d, ebp
0x18002b4ad  mov     rdx, rsi
0x18002b4b0  mov     rcx, rbx
0x18002b4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4b8  cmp     [rsi], di
0x18002b4bb  jnz     short loc_18002B4CB
0x18002b4bd  mov     r8, rbx; unsigned __int64
0x18002b4c0  mov     rdx, rbp; wchar_t *
0x18002b4c3  mov     rcx, rsi; this
0x18002b4c6  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18002b4cb  mov     rcx, rsi; lpOutputString
0x18002b4ce  call    cs:__imp_OutputDebugStringW
0x18002b4d4  test    byte ptr [rbx+4], 4
0x18002b4d8  jnz     short loc_18002B4E3
0x18002b4da  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002b4e1  jz      short loc_18002B4F5
0x18002b4e3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002b4ea  test    rax, rax
0x18002b4ed  jz      short loc_18002B4F5
0x18002b4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4f4  nop
0x18002b4f5  mov     rbx, [rsp+78h+arg_10]
0x18002b4fd  add     rsp, 40h
0x18002b501  pop     r15
0x18002b503  pop     r14
0x18002b505  pop     r13
0x18002b507  pop     r12
0x18002b509  pop     rdi
0x18002b50a  pop     rsi
0x18002b50b  pop     rbp
0x18002b50c  retn
```
