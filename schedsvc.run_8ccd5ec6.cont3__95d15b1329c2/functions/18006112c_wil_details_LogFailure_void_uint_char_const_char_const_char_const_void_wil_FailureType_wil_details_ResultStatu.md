# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18006112c`
- end: `0x180061438`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18005e774`
- `0x18005ead4`

## callees

- `0x180059278`
- `0x18005e6b4`
- `0x180060294`
- `0x18006112c`
- `0x180061c7c`
- `0x180061ca0`
- `0x180061d64`
- `0x180061d84`
- `0x180064648`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006124f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006124f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800613ec`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800613ec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180061374`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180061374`

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
0x18006112c  mov     [rsp+arg_10], rbx
0x180061131  mov     [rsp+arg_8], edx
0x180061135  mov     [rsp+arg_0], rcx
0x18006113a  push    rbp
0x18006113b  push    rsi
0x18006113c  push    rdi
0x18006113d  push    r12
0x18006113f  push    r13
0x180061141  push    r14
0x180061143  push    r15
0x180061145  sub     rsp, 40h
0x180061149  mov     r12, r9
0x18006114c  mov     r13, r8
0x18006114f  mov     r10, rcx
0x180061152  xor     eax, eax
0x180061154  mov     rsi, [rsp+78h+lpOutputString]
0x18006115c  mov     [rsi], ax
0x18006115f  mov     rax, [rsp+78h+arg_60]
0x180061167  mov     byte ptr [rax], 0
0x18006116a  mov     r14, [rsp+78h+arg_38]
0x180061172  mov     edi, [r14]
0x180061175  mov     rbx, [rsp+78h+arg_78]
0x18006117d  mov     [rbx+8], edi
0x180061180  mov     eax, [r14+4]
0x180061184  mov     [rbx+0Ch], eax
0x180061187  xor     ebp, ebp
0x180061189  mov     r15d, [rsp+78h+arg_30]
0x180061191  mov     ecx, r15d
0x180061194  test    r15d, r15d
0x180061197  jz      short loc_1800611FF
0x180061199  sub     ecx, 1
0x18006119c  jz      short loc_1800611F6
0x18006119e  sub     ecx, 1
0x1800611a1  jz      short loc_1800611B1
0x1800611a3  cmp     ecx, 1
0x1800611a6  jnz     short loc_180061208
0x1800611a8  mov     ecx, edi; this
0x1800611aa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800611af  jmp     short loc_180061206
0x1800611b1  test    edi, edi
0x1800611b3  js      short loc_1800611ED
0x1800611b5  mov     edi, 8007029Ch
0x1800611ba  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800611be  mov     rax, [rsp+78h+arg_28]
0x1800611c6  mov     [rsp+78h+var_50], rax; __int64
0x1800611cb  mov     rax, [rsp+78h+arg_20]
0x1800611d3  mov     [rsp+78h+var_58], rax; __int64
0x1800611d8  mov     rcx, r10; int
0x1800611db  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800611e0  mov     [rbx+8], edi
0x1800611e3  mov     ecx, edi; this
0x1800611e5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800611ea  mov     [rbx+0Ch], eax
0x1800611ed  mov     ecx, edi; this
0x1800611ef  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800611f4  jmp     short loc_180061206
0x1800611f6  mov     ecx, edi; this
0x1800611f8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800611fd  jmp     short loc_180061206
0x1800611ff  mov     ecx, edi; this
0x180061201  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180061206  mov     ebp, eax
0x180061208  mov     [rbx], r15d
0x18006120b  mov     eax, [rsp+78h+arg_70]
0x180061212  mov     [rbx+4], eax
0x180061215  cmp     dword ptr [r14+8], 1
0x18006121a  jnz     short loc_180061222
0x18006121c  or      eax, 8
0x18006121f  mov     [rbx+4], eax
0x180061222  mov     eax, 1
0x180061227  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18006122f  inc     eax
0x180061231  mov     [rbx+10h], eax
0x180061234  mov     rax, [rsp+78h+arg_40]
0x18006123c  xor     edi, edi
0x18006123e  test    rax, rax
0x180061241  jz      short loc_180061248
0x180061243  cmp     [rax], di
0x180061246  jnz     short loc_18006124B
0x180061248  mov     rax, rdi
0x18006124b  mov     [rbx+18h], rax
0x18006124f  call    cs:__imp_GetCurrentThreadId
0x180061256  nop     dword ptr [rax+rax+00h]
0x18006125b  mov     [rbx+20h], eax
0x18006125e  mov     [rbx+38h], r13
0x180061262  mov     eax, [rsp+78h+arg_8]
0x180061269  mov     [rbx+40h], eax
0x18006126c  mov     [rbx+44h], ebp
0x18006126f  mov     rax, [rsp+78h+arg_20]
0x180061277  mov     [rbx+28h], rax
0x18006127b  mov     [rbx+30h], r12
0x18006127f  mov     rax, [rsp+78h+arg_28]
0x180061287  mov     [rbx+88h], rax
0x18006128e  mov     rax, [rsp+78h+arg_0]
0x180061296  mov     [rbx+90h], rax
0x18006129d  mov     [rbx+48h], rdi
0x1800612a1  xorps   xmm0, xmm0
0x1800612a4  xor     eax, eax
0x1800612a6  movups  xmmword ptr [rbx+68h], xmm0
0x1800612aa  mov     [rbx+78h], rax
0x1800612ae  movups  xmmword ptr [rbx+50h], xmm0
0x1800612b2  mov     [rbx+60h], rax
0x1800612b6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800612bd  test    rax, rax
0x1800612c0  jz      short loc_1800612C9
0x1800612c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800612c7  jmp     short loc_1800612CC
0x1800612c9  mov     rax, rdi
0x1800612cc  mov     [rbx+80h], rax
0x1800612d3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800612da  test    rax, rax
0x1800612dd  jz      short loc_1800612E7
0x1800612df  mov     rcx, rbx
0x1800612e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800612e7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800612ee  test    rax, rax
0x1800612f1  jz      short loc_180061309
0x1800612f3  mov     r8d, 400h
0x1800612f9  mov     rdx, [rsp+78h+arg_60]
0x180061301  mov     rcx, rbx
0x180061304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061309  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180061310  test    rax, rax
0x180061313  jz      short loc_18006131D
0x180061315  mov     rcx, rbx
0x180061318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006131d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180061324  test    rax, rax
0x180061327  jz      short loc_180061337
0x180061329  test    byte ptr [rbx+4], 2
0x18006132d  jnz     short loc_180061337
0x18006132f  mov     rcx, rbx
0x180061332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061337  cmp     [rbx+8], edi
0x18006133a  jl      short loc_180061356
0x18006133c  cmp     r15d, 3
0x180061340  jnz     loc_180061432
0x180061346  mov     ecx, 8000FFFFh; this
0x18006134b  mov     [rbx+8], ecx
0x18006134e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180061353  mov     [rbx+0Ch], eax
0x180061356  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18006135d  jnz     short loc_180061384
0x18006135f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180061366  test    rax, rax
0x180061369  jz      short loc_180061374
0x18006136b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061370  test    al, al
0x180061372  jmp     short loc_180061382
0x180061374  call    cs:__imp_IsDebuggerPresent
0x18006137b  nop     dword ptr [rax+rax+00h]
0x180061380  test    eax, eax
0x180061382  jz      short loc_18006138A
0x180061384  test    byte ptr [rbx+4], 2
0x180061388  jz      short loc_1800613AE
0x18006138a  mov     rax, cs:g_pfnResultLoggingCallback
0x180061391  test    rax, rax
0x180061394  jz      short loc_1800613F8
0x180061396  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18006139d  jnz     short loc_1800613F8
0x18006139f  xor     r8d, r8d
0x1800613a2  xor     edx, edx
0x1800613a4  mov     rcx, rbx
0x1800613a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800613ac  jmp     short loc_1800613F8
0x1800613ae  mov     ebp, 800h
0x1800613b3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800613ba  test    rax, rax
0x1800613bd  jz      short loc_1800613D6
0x1800613bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800613c6  jnz     short loc_1800613D6
0x1800613c8  mov     r8d, ebp
0x1800613cb  mov     rdx, rsi
0x1800613ce  mov     rcx, rbx
0x1800613d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800613d6  cmp     [rsi], di
0x1800613d9  jnz     short loc_1800613E9
0x1800613db  mov     r8, rbx; unsigned __int64
0x1800613de  mov     rdx, rbp; unsigned __int16 *
0x1800613e1  mov     rcx, rsi; this
0x1800613e4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800613e9  mov     rcx, rsi; lpOutputString
0x1800613ec  call    cs:__imp_OutputDebugStringW
0x1800613f3  nop     dword ptr [rax+rax+00h]
0x1800613f8  test    byte ptr [rbx+4], 4
0x1800613fc  jnz     short loc_180061407
0x1800613fe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180061405  jz      short loc_180061419
0x180061407  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18006140e  test    rax, rax
0x180061411  jz      short loc_180061419
0x180061413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061418  nop
0x180061419  mov     rbx, [rsp+78h+arg_10]
0x180061421  add     rsp, 40h
0x180061425  pop     r15
0x180061427  pop     r14
0x180061429  pop     r13
0x18006142b  pop     r12
0x18006142d  pop     rdi
0x18006142e  pop     rsi
0x18006142f  pop     rbp
0x180061430  retn
0x180061432  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
