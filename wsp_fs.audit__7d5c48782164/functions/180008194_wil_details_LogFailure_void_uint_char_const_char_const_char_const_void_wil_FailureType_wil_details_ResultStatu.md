# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008194`
- end: `0x1800084a0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005af0`

## callees

- `0x180005504`
- `0x1800075a4`
- `0x180007e8c`
- `0x180008194`
- `0x180008e34`
- `0x180008e60`
- `0x180009000`
- `0x180009020`
- `0x18000a970`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800082b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800082b7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008454`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008454`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800083dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800083dc`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
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
0x180008194  mov     [rsp+arg_10], rbx
0x180008199  mov     [rsp+arg_8], edx
0x18000819d  mov     [rsp+arg_0], rcx
0x1800081a2  push    rbp
0x1800081a3  push    rsi
0x1800081a4  push    rdi
0x1800081a5  push    r12
0x1800081a7  push    r13
0x1800081a9  push    r14
0x1800081ab  push    r15
0x1800081ad  sub     rsp, 40h
0x1800081b1  mov     r12, r9
0x1800081b4  mov     r13, r8
0x1800081b7  mov     r10, rcx
0x1800081ba  xor     eax, eax
0x1800081bc  mov     rsi, [rsp+78h+lpOutputString]
0x1800081c4  mov     [rsi], ax
0x1800081c7  mov     rax, [rsp+78h+arg_60]
0x1800081cf  mov     byte ptr [rax], 0
0x1800081d2  mov     r14, [rsp+78h+arg_38]
0x1800081da  mov     edi, [r14]
0x1800081dd  mov     rbx, [rsp+78h+arg_78]
0x1800081e5  mov     [rbx+8], edi
0x1800081e8  mov     eax, [r14+4]
0x1800081ec  mov     [rbx+0Ch], eax
0x1800081ef  xor     ebp, ebp
0x1800081f1  mov     r15d, [rsp+78h+arg_30]
0x1800081f9  mov     ecx, r15d
0x1800081fc  test    r15d, r15d
0x1800081ff  jz      short loc_180008267
0x180008201  sub     ecx, 1
0x180008204  jz      short loc_18000825E
0x180008206  sub     ecx, 1
0x180008209  jz      short loc_180008219
0x18000820b  cmp     ecx, 1
0x18000820e  jnz     short loc_180008270
0x180008210  mov     ecx, edi; this
0x180008212  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008217  jmp     short loc_18000826E
0x180008219  test    edi, edi
0x18000821b  js      short loc_180008255
0x18000821d  mov     edi, 8007029Ch
0x180008222  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008226  mov     rax, [rsp+78h+arg_28]
0x18000822e  mov     [rsp+78h+var_50], rax; __int64
0x180008233  mov     rax, [rsp+78h+arg_20]
0x18000823b  mov     [rsp+78h+var_58], rax; __int64
0x180008240  mov     rcx, r10; int
0x180008243  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008248  mov     [rbx+8], edi
0x18000824b  mov     ecx, edi; this
0x18000824d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008252  mov     [rbx+0Ch], eax
0x180008255  mov     ecx, edi; this
0x180008257  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000825c  jmp     short loc_18000826E
0x18000825e  mov     ecx, edi; this
0x180008260  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008265  jmp     short loc_18000826E
0x180008267  mov     ecx, edi; this
0x180008269  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000826e  mov     ebp, eax
0x180008270  mov     [rbx], r15d
0x180008273  mov     eax, [rsp+78h+arg_70]
0x18000827a  mov     [rbx+4], eax
0x18000827d  cmp     dword ptr [r14+8], 1
0x180008282  jnz     short loc_18000828A
0x180008284  or      eax, 8
0x180008287  mov     [rbx+4], eax
0x18000828a  mov     eax, 1
0x18000828f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008297  inc     eax
0x180008299  mov     [rbx+10h], eax
0x18000829c  mov     rax, [rsp+78h+arg_40]
0x1800082a4  xor     edi, edi
0x1800082a6  test    rax, rax
0x1800082a9  jz      short loc_1800082B0
0x1800082ab  cmp     [rax], di
0x1800082ae  jnz     short loc_1800082B3
0x1800082b0  mov     rax, rdi
0x1800082b3  mov     [rbx+18h], rax
0x1800082b7  call    cs:__imp_GetCurrentThreadId
0x1800082be  nop     dword ptr [rax+rax+00h]
0x1800082c3  mov     [rbx+20h], eax
0x1800082c6  mov     [rbx+38h], r13
0x1800082ca  mov     eax, [rsp+78h+arg_8]
0x1800082d1  mov     [rbx+40h], eax
0x1800082d4  mov     [rbx+44h], ebp
0x1800082d7  mov     rax, [rsp+78h+arg_20]
0x1800082df  mov     [rbx+28h], rax
0x1800082e3  mov     [rbx+30h], r12
0x1800082e7  mov     rax, [rsp+78h+arg_28]
0x1800082ef  mov     [rbx+88h], rax
0x1800082f6  mov     rax, [rsp+78h+arg_0]
0x1800082fe  mov     [rbx+90h], rax
0x180008305  mov     [rbx+48h], rdi
0x180008309  xorps   xmm0, xmm0
0x18000830c  xor     eax, eax
0x18000830e  movups  xmmword ptr [rbx+68h], xmm0
0x180008312  mov     [rbx+78h], rax
0x180008316  movups  xmmword ptr [rbx+50h], xmm0
0x18000831a  mov     [rbx+60h], rax
0x18000831e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008325  test    rax, rax
0x180008328  jz      short loc_180008331
0x18000832a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000832f  jmp     short loc_180008334
0x180008331  mov     rax, rdi
0x180008334  mov     [rbx+80h], rax
0x18000833b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008342  test    rax, rax
0x180008345  jz      short loc_18000834F
0x180008347  mov     rcx, rbx
0x18000834a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000834f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008356  test    rax, rax
0x180008359  jz      short loc_180008371
0x18000835b  mov     r8d, 400h
0x180008361  mov     rdx, [rsp+78h+arg_60]
0x180008369  mov     rcx, rbx
0x18000836c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008371  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008378  test    rax, rax
0x18000837b  jz      short loc_180008385
0x18000837d  mov     rcx, rbx
0x180008380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008385  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000838c  test    rax, rax
0x18000838f  jz      short loc_18000839F
0x180008391  test    byte ptr [rbx+4], 2
0x180008395  jnz     short loc_18000839F
0x180008397  mov     rcx, rbx
0x18000839a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000839f  cmp     [rbx+8], edi
0x1800083a2  jl      short loc_1800083BE
0x1800083a4  cmp     r15d, 3
0x1800083a8  jnz     loc_18000849A
0x1800083ae  mov     ecx, 8000FFFFh; this
0x1800083b3  mov     [rbx+8], ecx
0x1800083b6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800083bb  mov     [rbx+0Ch], eax
0x1800083be  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800083c5  jnz     short loc_1800083EC
0x1800083c7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800083ce  test    rax, rax
0x1800083d1  jz      short loc_1800083DC
0x1800083d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d8  test    al, al
0x1800083da  jmp     short loc_1800083EA
0x1800083dc  call    cs:__imp_IsDebuggerPresent
0x1800083e3  nop     dword ptr [rax+rax+00h]
0x1800083e8  test    eax, eax
0x1800083ea  jz      short loc_1800083F2
0x1800083ec  test    byte ptr [rbx+4], 2
0x1800083f0  jz      short loc_180008416
0x1800083f2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800083f9  test    rax, rax
0x1800083fc  jz      short loc_180008460
0x1800083fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008405  jnz     short loc_180008460
0x180008407  xor     r8d, r8d
0x18000840a  xor     edx, edx
0x18000840c  mov     rcx, rbx
0x18000840f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008414  jmp     short loc_180008460
0x180008416  mov     ebp, 800h
0x18000841b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008422  test    rax, rax
0x180008425  jz      short loc_18000843E
0x180008427  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000842e  jnz     short loc_18000843E
0x180008430  mov     r8d, ebp
0x180008433  mov     rdx, rsi
0x180008436  mov     rcx, rbx
0x180008439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000843e  cmp     [rsi], di
0x180008441  jnz     short loc_180008451
0x180008443  mov     r8, rbx; unsigned __int64
0x180008446  mov     rdx, rbp; wchar_t *
0x180008449  mov     rcx, rsi; pszDest
0x18000844c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180008451  mov     rcx, rsi; lpOutputString
0x180008454  call    cs:__imp_OutputDebugStringW
0x18000845b  nop     dword ptr [rax+rax+00h]
0x180008460  test    byte ptr [rbx+4], 4
0x180008464  jnz     short loc_18000846F
0x180008466  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000846d  jz      short loc_180008481
0x18000846f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008476  test    rax, rax
0x180008479  jz      short loc_180008481
0x18000847b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008480  nop
0x180008481  mov     rbx, [rsp+78h+arg_10]
0x180008489  add     rsp, 40h
0x18000848d  pop     r15
0x18000848f  pop     r14
0x180008491  pop     r13
0x180008493  pop     r12
0x180008495  pop     rdi
0x180008496  pop     rsi
0x180008497  pop     rbp
0x180008498  retn
0x18000849a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
