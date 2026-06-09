# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001d01c`
- end: `0x18001d315`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18001cc64`
- `0x180021fb4`
- `0x18004ae14`

## callees

- `0x180014bd8`
- `0x18001bba4`
- `0x18001c180`
- `0x18001c954`
- `0x18001d01c`
- `0x18001d31c`
- `0x18001d338`
- `0x18001d354`
- `0x18001de18`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d13f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d13f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d2d0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d2d0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d25e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d25e`

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
0x18001d01c  mov     [rsp+arg_10], rbx
0x18001d021  mov     [rsp+arg_8], edx
0x18001d025  mov     [rsp+arg_0], rcx
0x18001d02a  push    rbp
0x18001d02b  push    rsi
0x18001d02c  push    rdi
0x18001d02d  push    r12
0x18001d02f  push    r13
0x18001d031  push    r14
0x18001d033  push    r15
0x18001d035  sub     rsp, 40h
0x18001d039  mov     r12, r9
0x18001d03c  mov     r13, r8
0x18001d03f  mov     r10, rcx
0x18001d042  xor     eax, eax
0x18001d044  mov     rsi, [rsp+78h+lpOutputString]
0x18001d04c  mov     [rsi], ax
0x18001d04f  mov     rax, [rsp+78h+arg_60]
0x18001d057  mov     byte ptr [rax], 0
0x18001d05a  mov     r14, [rsp+78h+arg_38]
0x18001d062  mov     edi, [r14]
0x18001d065  mov     rbx, [rsp+78h+arg_78]
0x18001d06d  mov     [rbx+8], edi
0x18001d070  mov     eax, [r14+4]
0x18001d074  mov     [rbx+0Ch], eax
0x18001d077  xor     ebp, ebp
0x18001d079  mov     r15d, [rsp+78h+arg_30]
0x18001d081  mov     ecx, r15d
0x18001d084  test    r15d, r15d
0x18001d087  jz      short loc_18001D0EF
0x18001d089  sub     ecx, 1
0x18001d08c  jz      short loc_18001D0E6
0x18001d08e  sub     ecx, 1
0x18001d091  jz      short loc_18001D0A1
0x18001d093  cmp     ecx, 1
0x18001d096  jnz     short loc_18001D0F8
0x18001d098  mov     ecx, edi; this
0x18001d09a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001d09f  jmp     short loc_18001D0F6
0x18001d0a1  test    edi, edi
0x18001d0a3  js      short loc_18001D0DD
0x18001d0a5  mov     edi, 8007029Ch
0x18001d0aa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001d0ae  mov     rax, [rsp+78h+arg_28]
0x18001d0b6  mov     [rsp+78h+var_50], rax; __int64
0x18001d0bb  mov     rax, [rsp+78h+arg_20]
0x18001d0c3  mov     [rsp+78h+var_58], rax; __int64
0x18001d0c8  mov     rcx, r10; int
0x18001d0cb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001d0d0  mov     [rbx+8], edi
0x18001d0d3  mov     ecx, edi; this
0x18001d0d5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001d0da  mov     [rbx+0Ch], eax
0x18001d0dd  mov     ecx, edi; this
0x18001d0df  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001d0e4  jmp     short loc_18001D0F6
0x18001d0e6  mov     ecx, edi; this
0x18001d0e8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001d0ed  jmp     short loc_18001D0F6
0x18001d0ef  mov     ecx, edi; this
0x18001d0f1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001d0f6  mov     ebp, eax
0x18001d0f8  mov     [rbx], r15d
0x18001d0fb  mov     eax, [rsp+78h+arg_70]
0x18001d102  mov     [rbx+4], eax
0x18001d105  cmp     dword ptr [r14+8], 1
0x18001d10a  jnz     short loc_18001D112
0x18001d10c  or      eax, 8
0x18001d10f  mov     [rbx+4], eax
0x18001d112  mov     eax, 1
0x18001d117  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001d11f  inc     eax
0x18001d121  mov     [rbx+10h], eax
0x18001d124  mov     rax, [rsp+78h+arg_40]
0x18001d12c  xor     edi, edi
0x18001d12e  test    rax, rax
0x18001d131  jz      short loc_18001D138
0x18001d133  cmp     [rax], di
0x18001d136  jnz     short loc_18001D13B
0x18001d138  mov     rax, rdi
0x18001d13b  mov     [rbx+18h], rax
0x18001d13f  call    cs:__imp_GetCurrentThreadId
0x18001d145  mov     [rbx+20h], eax
0x18001d148  mov     [rbx+38h], r13
0x18001d14c  mov     eax, [rsp+78h+arg_8]
0x18001d153  mov     [rbx+40h], eax
0x18001d156  mov     [rbx+44h], ebp
0x18001d159  mov     rax, [rsp+78h+arg_20]
0x18001d161  mov     [rbx+28h], rax
0x18001d165  mov     [rbx+30h], r12
0x18001d169  mov     rax, [rsp+78h+arg_28]
0x18001d171  mov     [rbx+88h], rax
0x18001d178  mov     rax, [rsp+78h+arg_0]
0x18001d180  mov     [rbx+90h], rax
0x18001d187  mov     [rbx+48h], rdi
0x18001d18b  xorps   xmm0, xmm0
0x18001d18e  xor     eax, eax
0x18001d190  movups  xmmword ptr [rbx+68h], xmm0
0x18001d194  mov     [rbx+78h], rax
0x18001d198  movups  xmmword ptr [rbx+50h], xmm0
0x18001d19c  mov     [rbx+60h], rax
0x18001d1a0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001d1a7  test    rax, rax
0x18001d1aa  jz      short loc_18001D1B3
0x18001d1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1b1  jmp     short loc_18001D1B6
0x18001d1b3  mov     rax, rdi
0x18001d1b6  mov     [rbx+80h], rax
0x18001d1bd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001d1c4  test    rax, rax
0x18001d1c7  jz      short loc_18001D1D1
0x18001d1c9  mov     rcx, rbx
0x18001d1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1d1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001d1d8  test    rax, rax
0x18001d1db  jz      short loc_18001D1F3
0x18001d1dd  mov     r8d, 400h
0x18001d1e3  mov     rdx, [rsp+78h+arg_60]
0x18001d1eb  mov     rcx, rbx
0x18001d1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1f3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d1fa  test    rax, rax
0x18001d1fd  jz      short loc_18001D207
0x18001d1ff  mov     rcx, rbx
0x18001d202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d207  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d20e  test    rax, rax
0x18001d211  jz      short loc_18001D221
0x18001d213  test    byte ptr [rbx+4], 2
0x18001d217  jnz     short loc_18001D221
0x18001d219  mov     rcx, rbx
0x18001d21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d221  cmp     [rbx+8], edi
0x18001d224  jl      short loc_18001D240
0x18001d226  cmp     r15d, 3
0x18001d22a  jnz     loc_18001D30F
0x18001d230  mov     ecx, 8000FFFFh; this
0x18001d235  mov     [rbx+8], ecx
0x18001d238  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001d23d  mov     [rbx+0Ch], eax
0x18001d240  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001d247  jnz     short loc_18001D268
0x18001d249  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001d250  test    rax, rax
0x18001d253  jz      short loc_18001D25E
0x18001d255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d25a  test    al, al
0x18001d25c  jmp     short loc_18001D266
0x18001d25e  call    cs:__imp_IsDebuggerPresent
0x18001d264  test    eax, eax
0x18001d266  jz      short loc_18001D26E
0x18001d268  test    byte ptr [rbx+4], 2
0x18001d26c  jz      short loc_18001D292
0x18001d26e  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d275  test    rax, rax
0x18001d278  jz      short loc_18001D2D6
0x18001d27a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001d281  jnz     short loc_18001D2D6
0x18001d283  xor     r8d, r8d
0x18001d286  xor     edx, edx
0x18001d288  mov     rcx, rbx
0x18001d28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d290  jmp     short loc_18001D2D6
0x18001d292  mov     ebp, 800h
0x18001d297  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d29e  test    rax, rax
0x18001d2a1  jz      short loc_18001D2BA
0x18001d2a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001d2aa  jnz     short loc_18001D2BA
0x18001d2ac  mov     r8d, ebp
0x18001d2af  mov     rdx, rsi
0x18001d2b2  mov     rcx, rbx
0x18001d2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2ba  cmp     [rsi], di
0x18001d2bd  jnz     short loc_18001D2CD
0x18001d2bf  mov     r8, rbx; unsigned __int64
0x18001d2c2  mov     rdx, rbp; unsigned __int16 *
0x18001d2c5  mov     rcx, rsi; this
0x18001d2c8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001d2cd  mov     rcx, rsi; lpOutputString
0x18001d2d0  call    cs:__imp_OutputDebugStringW
0x18001d2d6  test    byte ptr [rbx+4], 4
0x18001d2da  jnz     short loc_18001D2E5
0x18001d2dc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001d2e3  jz      short loc_18001D2F7
0x18001d2e5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001d2ec  test    rax, rax
0x18001d2ef  jz      short loc_18001D2F7
0x18001d2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2f6  nop
0x18001d2f7  mov     rbx, [rsp+78h+arg_10]
0x18001d2ff  add     rsp, 40h
0x18001d303  pop     r15
0x18001d305  pop     r14
0x18001d307  pop     r13
0x18001d309  pop     r12
0x18001d30b  pop     rdi
0x18001d30c  pop     rsi
0x18001d30d  pop     rbp
0x18001d30e  retn
0x18001d30f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
