# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800427d0`
- end: `0x180042adb`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18003e4b4`
- `0x18003e814`

## callees

- `0x18003c42c`
- `0x18003e3f4`
- `0x180041bc4`
- `0x1800427d0`
- `0x180043b14`
- `0x180043b40`
- `0x180043c04`
- `0x180043c24`
- `0x180046edc`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800428f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800428f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180042a18`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180042a18`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180042a90`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180042a90`

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
0x1800427d0  mov     [rsp+arg_10], rbx
0x1800427d5  mov     [rsp+arg_8], edx
0x1800427d9  mov     [rsp+arg_0], rcx
0x1800427de  push    rbp
0x1800427df  push    rsi
0x1800427e0  push    rdi
0x1800427e1  push    r12
0x1800427e3  push    r13
0x1800427e5  push    r14
0x1800427e7  push    r15
0x1800427e9  sub     rsp, 40h
0x1800427ed  mov     r14, [rsp+78h+arg_38]
0x1800427f5  xor     eax, eax
0x1800427f7  mov     rbx, [rsp+78h+arg_78]
0x1800427ff  xor     ebp, ebp
0x180042801  mov     r15d, [rsp+78h+arg_30]
0x180042809  mov     r10, rcx
0x18004280c  mov     rsi, [rsp+78h+lpOutputString]
0x180042814  mov     r12, r9
0x180042817  mov     r13, r8
0x18004281a  mov     ecx, r15d
0x18004281d  mov     [rsi], ax
0x180042820  mov     rax, [rsp+78h+arg_60]
0x180042828  mov     byte ptr [rax], 0
0x18004282b  mov     edi, [r14]
0x18004282e  mov     [rbx+8], edi
0x180042831  mov     eax, [r14+4]
0x180042835  mov     [rbx+0Ch], eax
0x180042838  test    r15d, r15d
0x18004283b  jz      short loc_1800428A3
0x18004283d  sub     ecx, 1
0x180042840  jz      short loc_18004289A
0x180042842  sub     ecx, 1
0x180042845  jz      short loc_180042855
0x180042847  cmp     ecx, 1
0x18004284a  jnz     short loc_1800428AC
0x18004284c  mov     ecx, edi; this
0x18004284e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180042853  jmp     short loc_1800428AA
0x180042855  test    edi, edi
0x180042857  js      short loc_180042891
0x180042859  mov     rax, [rsp+78h+arg_28]
0x180042861  mov     edi, 8007029Ch
0x180042866  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18004286a  mov     rcx, r10; int
0x18004286d  mov     [rsp+78h+var_50], rax; __int64
0x180042872  mov     rax, [rsp+78h+arg_20]
0x18004287a  mov     [rsp+78h+var_58], rax; __int64
0x18004287f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180042884  mov     ecx, edi; this
0x180042886  mov     [rbx+8], edi
0x180042889  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004288e  mov     [rbx+0Ch], eax
0x180042891  mov     ecx, edi; this
0x180042893  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180042898  jmp     short loc_1800428AA
0x18004289a  mov     ecx, edi; this
0x18004289c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800428a1  jmp     short loc_1800428AA
0x1800428a3  mov     ecx, edi; this
0x1800428a5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800428aa  mov     ebp, eax
0x1800428ac  mov     eax, [rsp+78h+arg_70]
0x1800428b3  mov     [rbx+4], eax
0x1800428b6  mov     [rbx], r15d
0x1800428b9  cmp     dword ptr [r14+8], 1
0x1800428be  jnz     short loc_1800428C6
0x1800428c0  or      eax, 8
0x1800428c3  mov     [rbx+4], eax
0x1800428c6  mov     eax, 1
0x1800428cb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800428d3  inc     eax
0x1800428d5  xor     edi, edi
0x1800428d7  mov     [rbx+10h], eax
0x1800428da  mov     rax, [rsp+78h+arg_40]
0x1800428e2  test    rax, rax
0x1800428e5  jz      short loc_1800428EC
0x1800428e7  cmp     [rax], di
0x1800428ea  jnz     short loc_1800428EF
0x1800428ec  mov     rax, rdi
0x1800428ef  mov     [rbx+18h], rax
0x1800428f3  call    cs:__imp_GetCurrentThreadId
0x1800428fa  nop     dword ptr [rax+rax+00h]
0x1800428ff  mov     [rbx+38h], r13
0x180042903  xorps   xmm0, xmm0
0x180042906  mov     [rbx+20h], eax
0x180042909  mov     eax, [rsp+78h+arg_8]
0x180042910  mov     [rbx+40h], eax
0x180042913  mov     rax, [rsp+78h+arg_20]
0x18004291b  mov     [rbx+28h], rax
0x18004291f  mov     rax, [rsp+78h+arg_28]
0x180042927  mov     [rbx+88h], rax
0x18004292e  mov     rax, [rsp+78h+arg_0]
0x180042936  mov     [rbx+90h], rax
0x18004293d  xor     eax, eax
0x18004293f  mov     [rbx+44h], ebp
0x180042942  mov     [rbx+30h], r12
0x180042946  mov     [rbx+48h], rdi
0x18004294a  movups  xmmword ptr [rbx+68h], xmm0
0x18004294e  mov     [rbx+78h], rax
0x180042952  movups  xmmword ptr [rbx+50h], xmm0
0x180042956  mov     [rbx+60h], rax
0x18004295a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180042961  test    rax, rax
0x180042964  jz      short loc_18004296D
0x180042966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004296b  jmp     short loc_180042970
0x18004296d  mov     rax, rdi
0x180042970  mov     [rbx+80h], rax
0x180042977  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004297e  test    rax, rax
0x180042981  jz      short loc_18004298B
0x180042983  mov     rcx, rbx
0x180042986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004298b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180042992  test    rax, rax
0x180042995  jz      short loc_1800429AD
0x180042997  mov     rdx, [rsp+78h+arg_60]
0x18004299f  mov     r8d, 400h
0x1800429a5  mov     rcx, rbx
0x1800429a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429ad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800429b4  test    rax, rax
0x1800429b7  jz      short loc_1800429C1
0x1800429b9  mov     rcx, rbx
0x1800429bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429c1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800429c8  test    rax, rax
0x1800429cb  jz      short loc_1800429DB
0x1800429cd  test    byte ptr [rbx+4], 2
0x1800429d1  jnz     short loc_1800429DB
0x1800429d3  mov     rcx, rbx
0x1800429d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429db  cmp     [rbx+8], edi
0x1800429de  jl      short loc_1800429FA
0x1800429e0  cmp     r15d, 3
0x1800429e4  jnz     loc_180042AD5
0x1800429ea  mov     ecx, 8000FFFFh; this
0x1800429ef  mov     [rbx+8], ecx
0x1800429f2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800429f7  mov     [rbx+0Ch], eax
0x1800429fa  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180042a01  jnz     short loc_180042A28
0x180042a03  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180042a0a  test    rax, rax
0x180042a0d  jz      short loc_180042A18
0x180042a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a14  test    al, al
0x180042a16  jmp     short loc_180042A26
0x180042a18  call    cs:__imp_IsDebuggerPresent
0x180042a1f  nop     dword ptr [rax+rax+00h]
0x180042a24  test    eax, eax
0x180042a26  jz      short loc_180042A2E
0x180042a28  test    byte ptr [rbx+4], 2
0x180042a2c  jz      short loc_180042A52
0x180042a2e  mov     rax, cs:g_pfnResultLoggingCallback
0x180042a35  test    rax, rax
0x180042a38  jz      short loc_180042A9C
0x180042a3a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180042a41  jnz     short loc_180042A9C
0x180042a43  xor     r8d, r8d
0x180042a46  xor     edx, edx
0x180042a48  mov     rcx, rbx
0x180042a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a50  jmp     short loc_180042A9C
0x180042a52  mov     rax, cs:g_pfnResultLoggingCallback
0x180042a59  mov     ebp, 800h
0x180042a5e  test    rax, rax
0x180042a61  jz      short loc_180042A7A
0x180042a63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180042a6a  jnz     short loc_180042A7A
0x180042a6c  mov     r8d, ebp
0x180042a6f  mov     rdx, rsi
0x180042a72  mov     rcx, rbx
0x180042a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a7a  cmp     [rsi], di
0x180042a7d  jnz     short loc_180042A8D
0x180042a7f  mov     r8, rbx; unsigned __int64
0x180042a82  mov     rdx, rbp; unsigned __int16 *
0x180042a85  mov     rcx, rsi; this
0x180042a88  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180042a8d  mov     rcx, rsi; lpOutputString
0x180042a90  call    cs:__imp_OutputDebugStringW
0x180042a97  nop     dword ptr [rax+rax+00h]
0x180042a9c  test    byte ptr [rbx+4], 4
0x180042aa0  jnz     short loc_180042AAB
0x180042aa2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180042aa9  jz      short loc_180042ABC
0x180042aab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180042ab2  test    rax, rax
0x180042ab5  jz      short loc_180042ABC
0x180042ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042abc  mov     rbx, [rsp+78h+arg_10]
0x180042ac4  add     rsp, 40h
0x180042ac8  pop     r15
0x180042aca  pop     r14
0x180042acc  pop     r13
0x180042ace  pop     r12
0x180042ad0  pop     rdi
0x180042ad1  pop     rsi
0x180042ad2  pop     rbp
0x180042ad3  retn
0x180042ad5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
