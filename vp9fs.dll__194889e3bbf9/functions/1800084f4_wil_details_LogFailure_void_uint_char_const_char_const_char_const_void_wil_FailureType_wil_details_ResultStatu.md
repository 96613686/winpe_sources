# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800084f4`
- end: `0x1800087ed`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005988`

## callees

- `0x1800050c8`
- `0x180007af4`
- `0x1800082dc`
- `0x1800084f4`
- `0x180008f90`
- `0x180008fb0`
- `0x1800090e0`
- `0x1800090fc`
- `0x18000b75c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008617`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008617`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800087a8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800087a8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008736`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008736`

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
0x1800084f4  mov     [rsp+arg_10], rbx
0x1800084f9  mov     [rsp+arg_8], edx
0x1800084fd  mov     [rsp+arg_0], rcx
0x180008502  push    rbp
0x180008503  push    rsi
0x180008504  push    rdi
0x180008505  push    r12
0x180008507  push    r13
0x180008509  push    r14
0x18000850b  push    r15
0x18000850d  sub     rsp, 40h
0x180008511  mov     r12, r9
0x180008514  mov     r13, r8
0x180008517  mov     r10, rcx
0x18000851a  xor     eax, eax
0x18000851c  mov     rsi, [rsp+78h+lpOutputString]
0x180008524  mov     [rsi], ax
0x180008527  mov     rax, [rsp+78h+arg_60]
0x18000852f  mov     byte ptr [rax], 0
0x180008532  mov     r14, [rsp+78h+arg_38]
0x18000853a  mov     edi, [r14]
0x18000853d  mov     rbx, [rsp+78h+arg_78]
0x180008545  mov     [rbx+8], edi
0x180008548  mov     eax, [r14+4]
0x18000854c  mov     [rbx+0Ch], eax
0x18000854f  xor     ebp, ebp
0x180008551  mov     r15d, [rsp+78h+arg_30]
0x180008559  mov     ecx, r15d
0x18000855c  test    r15d, r15d
0x18000855f  jz      short loc_1800085C7
0x180008561  sub     ecx, 1
0x180008564  jz      short loc_1800085BE
0x180008566  sub     ecx, 1
0x180008569  jz      short loc_180008579
0x18000856b  cmp     ecx, 1
0x18000856e  jnz     short loc_1800085D0
0x180008570  mov     ecx, edi; this
0x180008572  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008577  jmp     short loc_1800085CE
0x180008579  test    edi, edi
0x18000857b  js      short loc_1800085B5
0x18000857d  mov     edi, 8007029Ch
0x180008582  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008586  mov     rax, [rsp+78h+arg_28]
0x18000858e  mov     [rsp+78h+var_50], rax; __int64
0x180008593  mov     rax, [rsp+78h+arg_20]
0x18000859b  mov     [rsp+78h+var_58], rax; __int64
0x1800085a0  mov     rcx, r10; int
0x1800085a3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800085a8  mov     [rbx+8], edi
0x1800085ab  mov     ecx, edi; this
0x1800085ad  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800085b2  mov     [rbx+0Ch], eax
0x1800085b5  mov     ecx, edi; this
0x1800085b7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800085bc  jmp     short loc_1800085CE
0x1800085be  mov     ecx, edi; this
0x1800085c0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800085c5  jmp     short loc_1800085CE
0x1800085c7  mov     ecx, edi; this
0x1800085c9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800085ce  mov     ebp, eax
0x1800085d0  mov     [rbx], r15d
0x1800085d3  mov     eax, [rsp+78h+arg_70]
0x1800085da  mov     [rbx+4], eax
0x1800085dd  cmp     dword ptr [r14+8], 1
0x1800085e2  jnz     short loc_1800085EA
0x1800085e4  or      eax, 8
0x1800085e7  mov     [rbx+4], eax
0x1800085ea  mov     eax, 1
0x1800085ef  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800085f7  inc     eax
0x1800085f9  mov     [rbx+10h], eax
0x1800085fc  mov     rax, [rsp+78h+arg_40]
0x180008604  xor     edi, edi
0x180008606  test    rax, rax
0x180008609  jz      short loc_180008610
0x18000860b  cmp     [rax], di
0x18000860e  jnz     short loc_180008613
0x180008610  mov     rax, rdi
0x180008613  mov     [rbx+18h], rax
0x180008617  call    cs:__imp_GetCurrentThreadId
0x18000861d  mov     [rbx+20h], eax
0x180008620  mov     [rbx+38h], r13
0x180008624  mov     eax, [rsp+78h+arg_8]
0x18000862b  mov     [rbx+40h], eax
0x18000862e  mov     [rbx+44h], ebp
0x180008631  mov     rax, [rsp+78h+arg_20]
0x180008639  mov     [rbx+28h], rax
0x18000863d  mov     [rbx+30h], r12
0x180008641  mov     rax, [rsp+78h+arg_28]
0x180008649  mov     [rbx+88h], rax
0x180008650  mov     rax, [rsp+78h+arg_0]
0x180008658  mov     [rbx+90h], rax
0x18000865f  mov     [rbx+48h], rdi
0x180008663  xorps   xmm0, xmm0
0x180008666  xor     eax, eax
0x180008668  movups  xmmword ptr [rbx+68h], xmm0
0x18000866c  mov     [rbx+78h], rax
0x180008670  movups  xmmword ptr [rbx+50h], xmm0
0x180008674  mov     [rbx+60h], rax
0x180008678  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000867f  test    rax, rax
0x180008682  jz      short loc_18000868B
0x180008684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008689  jmp     short loc_18000868E
0x18000868b  mov     rax, rdi
0x18000868e  mov     [rbx+80h], rax
0x180008695  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000869c  test    rax, rax
0x18000869f  jz      short loc_1800086A9
0x1800086a1  mov     rcx, rbx
0x1800086a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800086b0  test    rax, rax
0x1800086b3  jz      short loc_1800086CB
0x1800086b5  mov     r8d, 400h
0x1800086bb  mov     rdx, [rsp+78h+arg_60]
0x1800086c3  mov     rcx, rbx
0x1800086c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086cb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800086d2  test    rax, rax
0x1800086d5  jz      short loc_1800086DF
0x1800086d7  mov     rcx, rbx
0x1800086da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086df  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800086e6  test    rax, rax
0x1800086e9  jz      short loc_1800086F9
0x1800086eb  test    byte ptr [rbx+4], 2
0x1800086ef  jnz     short loc_1800086F9
0x1800086f1  mov     rcx, rbx
0x1800086f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086f9  cmp     [rbx+8], edi
0x1800086fc  jl      short loc_180008718
0x1800086fe  cmp     r15d, 3
0x180008702  jnz     loc_1800087E7
0x180008708  mov     ecx, 8000FFFFh; this
0x18000870d  mov     [rbx+8], ecx
0x180008710  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008715  mov     [rbx+0Ch], eax
0x180008718  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000871f  jnz     short loc_180008740
0x180008721  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008728  test    rax, rax
0x18000872b  jz      short loc_180008736
0x18000872d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008732  test    al, al
0x180008734  jmp     short loc_18000873E
0x180008736  call    cs:__imp_IsDebuggerPresent
0x18000873c  test    eax, eax
0x18000873e  jz      short loc_180008746
0x180008740  test    byte ptr [rbx+4], 2
0x180008744  jz      short loc_18000876A
0x180008746  mov     rax, cs:g_pfnResultLoggingCallback
0x18000874d  test    rax, rax
0x180008750  jz      short loc_1800087AE
0x180008752  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008759  jnz     short loc_1800087AE
0x18000875b  xor     r8d, r8d
0x18000875e  xor     edx, edx
0x180008760  mov     rcx, rbx
0x180008763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008768  jmp     short loc_1800087AE
0x18000876a  mov     ebp, 800h
0x18000876f  mov     rax, cs:g_pfnResultLoggingCallback
0x180008776  test    rax, rax
0x180008779  jz      short loc_180008792
0x18000877b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008782  jnz     short loc_180008792
0x180008784  mov     r8d, ebp
0x180008787  mov     rdx, rsi
0x18000878a  mov     rcx, rbx
0x18000878d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008792  cmp     [rsi], di
0x180008795  jnz     short loc_1800087A5
0x180008797  mov     r8, rbx; unsigned __int64
0x18000879a  mov     rdx, rbp; unsigned __int16 *
0x18000879d  mov     rcx, rsi; this
0x1800087a0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800087a5  mov     rcx, rsi; lpOutputString
0x1800087a8  call    cs:__imp_OutputDebugStringW
0x1800087ae  test    byte ptr [rbx+4], 4
0x1800087b2  jnz     short loc_1800087BD
0x1800087b4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800087bb  jz      short loc_1800087CF
0x1800087bd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800087c4  test    rax, rax
0x1800087c7  jz      short loc_1800087CF
0x1800087c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087ce  nop
0x1800087cf  mov     rbx, [rsp+78h+arg_10]
0x1800087d7  add     rsp, 40h
0x1800087db  pop     r15
0x1800087dd  pop     r14
0x1800087df  pop     r13
0x1800087e1  pop     r12
0x1800087e3  pop     rdi
0x1800087e4  pop     rsi
0x1800087e5  pop     rbp
0x1800087e6  retn
0x1800087e7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
