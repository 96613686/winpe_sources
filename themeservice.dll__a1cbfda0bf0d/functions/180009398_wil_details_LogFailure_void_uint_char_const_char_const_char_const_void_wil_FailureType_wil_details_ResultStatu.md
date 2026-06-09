# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009398`
- end: `0x18000968c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800082dc`
- `0x18000838c`
- `0x180008480`

## callees

- `0x180006b5c`
- `0x180008230`
- `0x180008ca4`
- `0x180009398`
- `0x1800099a4`
- `0x1800099c0`
- `0x1800099d4`
- `0x1800099f0`
- `0x18000a25c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800094bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800094bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000964e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000964e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800095dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800095dc`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
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
0x180009398  mov     [rsp+arg_10], rbx
0x18000939d  mov     [rsp+arg_8], edx
0x1800093a1  mov     [rsp+arg_0], rcx
0x1800093a6  push    rbp
0x1800093a7  push    rsi
0x1800093a8  push    rdi
0x1800093a9  push    r12
0x1800093ab  push    r13
0x1800093ad  push    r14
0x1800093af  push    r15
0x1800093b1  sub     rsp, 40h
0x1800093b5  mov     r14, [rsp+78h+arg_38]
0x1800093bd  xor     eax, eax
0x1800093bf  mov     rbx, [rsp+78h+arg_78]
0x1800093c7  xor     ebp, ebp
0x1800093c9  mov     r15d, [rsp+78h+arg_30]
0x1800093d1  mov     r10, rcx
0x1800093d4  mov     rsi, [rsp+78h+lpOutputString]
0x1800093dc  mov     r12, r9
0x1800093df  mov     r13, r8
0x1800093e2  mov     ecx, r15d
0x1800093e5  mov     [rsi], ax
0x1800093e8  mov     rax, [rsp+78h+arg_60]
0x1800093f0  mov     byte ptr [rax], 0
0x1800093f3  mov     edi, [r14]
0x1800093f6  mov     [rbx+8], edi
0x1800093f9  mov     eax, [r14+4]
0x1800093fd  mov     [rbx+0Ch], eax
0x180009400  test    r15d, r15d
0x180009403  jz      short loc_18000946B
0x180009405  sub     ecx, 1
0x180009408  jz      short loc_180009462
0x18000940a  sub     ecx, 1
0x18000940d  jz      short loc_18000941D
0x18000940f  cmp     ecx, 1
0x180009412  jnz     short loc_180009474
0x180009414  mov     ecx, edi; this
0x180009416  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000941b  jmp     short loc_180009472
0x18000941d  test    edi, edi
0x18000941f  js      short loc_180009459
0x180009421  mov     rax, [rsp+78h+arg_28]
0x180009429  mov     edi, 8007029Ch
0x18000942e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180009432  mov     rcx, r10; int
0x180009435  mov     [rsp+78h+var_50], rax; __int64
0x18000943a  mov     rax, [rsp+78h+arg_20]
0x180009442  mov     [rsp+78h+var_58], rax; __int64
0x180009447  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000944c  mov     ecx, edi; this
0x18000944e  mov     [rbx+8], edi
0x180009451  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009456  mov     [rbx+0Ch], eax
0x180009459  mov     ecx, edi; this
0x18000945b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009460  jmp     short loc_180009472
0x180009462  mov     ecx, edi; this
0x180009464  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009469  jmp     short loc_180009472
0x18000946b  mov     ecx, edi; this
0x18000946d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009472  mov     ebp, eax
0x180009474  mov     eax, [rsp+78h+arg_70]
0x18000947b  mov     [rbx+4], eax
0x18000947e  mov     [rbx], r15d
0x180009481  cmp     dword ptr [r14+8], 1
0x180009486  jnz     short loc_18000948E
0x180009488  or      eax, 8
0x18000948b  mov     [rbx+4], eax
0x18000948e  mov     eax, 1
0x180009493  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000949b  inc     eax
0x18000949d  xor     edi, edi
0x18000949f  mov     [rbx+10h], eax
0x1800094a2  mov     rax, [rsp+78h+arg_40]
0x1800094aa  test    rax, rax
0x1800094ad  jz      short loc_1800094B4
0x1800094af  cmp     [rax], di
0x1800094b2  jnz     short loc_1800094B7
0x1800094b4  mov     rax, rdi
0x1800094b7  mov     [rbx+18h], rax
0x1800094bb  call    cs:__imp_GetCurrentThreadId
0x1800094c1  mov     [rbx+38h], r13
0x1800094c5  xorps   xmm0, xmm0
0x1800094c8  mov     [rbx+20h], eax
0x1800094cb  mov     eax, [rsp+78h+arg_8]
0x1800094d2  mov     [rbx+40h], eax
0x1800094d5  mov     rax, [rsp+78h+arg_20]
0x1800094dd  mov     [rbx+28h], rax
0x1800094e1  mov     rax, [rsp+78h+arg_28]
0x1800094e9  mov     [rbx+88h], rax
0x1800094f0  mov     rax, [rsp+78h+arg_0]
0x1800094f8  mov     [rbx+90h], rax
0x1800094ff  xor     eax, eax
0x180009501  mov     [rbx+44h], ebp
0x180009504  mov     [rbx+30h], r12
0x180009508  mov     [rbx+48h], rdi
0x18000950c  movups  xmmword ptr [rbx+68h], xmm0
0x180009510  mov     [rbx+78h], rax
0x180009514  movups  xmmword ptr [rbx+50h], xmm0
0x180009518  mov     [rbx+60h], rax
0x18000951c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009523  test    rax, rax
0x180009526  jz      short loc_18000952F
0x180009528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000952d  jmp     short loc_180009532
0x18000952f  mov     rax, rdi
0x180009532  mov     [rbx+80h], rax
0x180009539  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009540  test    rax, rax
0x180009543  jz      short loc_18000954D
0x180009545  mov     rcx, rbx
0x180009548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000954d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009554  test    rax, rax
0x180009557  jz      short loc_18000956F
0x180009559  mov     rdx, [rsp+78h+arg_60]
0x180009561  mov     r8d, 400h
0x180009567  mov     rcx, rbx
0x18000956a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000956f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009576  test    rax, rax
0x180009579  jz      short loc_180009583
0x18000957b  mov     rcx, rbx
0x18000957e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009583  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000958a  test    rax, rax
0x18000958d  jz      short loc_18000959D
0x18000958f  test    byte ptr [rbx+4], 2
0x180009593  jnz     short loc_18000959D
0x180009595  mov     rcx, rbx
0x180009598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000959d  cmp     [rbx+8], edi
0x1800095a0  jl      short loc_1800095BE
0x1800095a2  cmp     r15d, 3
0x1800095a6  jz      short loc_1800095AE
0x1800095a8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800095ae  mov     ecx, 8000FFFFh; this
0x1800095b3  mov     [rbx+8], ecx
0x1800095b6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800095bb  mov     [rbx+0Ch], eax
0x1800095be  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800095c5  jnz     short loc_1800095E6
0x1800095c7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800095ce  test    rax, rax
0x1800095d1  jz      short loc_1800095DC
0x1800095d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d8  test    al, al
0x1800095da  jmp     short loc_1800095E4
0x1800095dc  call    cs:__imp_IsDebuggerPresent
0x1800095e2  test    eax, eax
0x1800095e4  jz      short loc_1800095EC
0x1800095e6  test    byte ptr [rbx+4], 2
0x1800095ea  jz      short loc_180009610
0x1800095ec  mov     rax, cs:g_pfnResultLoggingCallback
0x1800095f3  test    rax, rax
0x1800095f6  jz      short loc_180009654
0x1800095f8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800095ff  jnz     short loc_180009654
0x180009601  xor     r8d, r8d
0x180009604  xor     edx, edx
0x180009606  mov     rcx, rbx
0x180009609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000960e  jmp     short loc_180009654
0x180009610  mov     rax, cs:g_pfnResultLoggingCallback
0x180009617  mov     ebp, 800h
0x18000961c  test    rax, rax
0x18000961f  jz      short loc_180009638
0x180009621  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009628  jnz     short loc_180009638
0x18000962a  mov     r8d, ebp
0x18000962d  mov     rdx, rsi
0x180009630  mov     rcx, rbx
0x180009633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009638  cmp     [rsi], di
0x18000963b  jnz     short loc_18000964B
0x18000963d  mov     r8, rbx; unsigned __int64
0x180009640  mov     rdx, rbp; unsigned __int16 *
0x180009643  mov     rcx, rsi; this
0x180009646  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000964b  mov     rcx, rsi; lpOutputString
0x18000964e  call    cs:__imp_OutputDebugStringW
0x180009654  test    byte ptr [rbx+4], 4
0x180009658  jnz     short loc_180009663
0x18000965a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009661  jz      short loc_180009674
0x180009663  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000966a  test    rax, rax
0x18000966d  jz      short loc_180009674
0x18000966f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009674  mov     rbx, [rsp+78h+arg_10]
0x18000967c  add     rsp, 40h
0x180009680  pop     r15
0x180009682  pop     r14
0x180009684  pop     r13
0x180009686  pop     r12
0x180009688  pop     rdi
0x180009689  pop     rsi
0x18000968a  pop     rbp
0x18000968b  retn
```
