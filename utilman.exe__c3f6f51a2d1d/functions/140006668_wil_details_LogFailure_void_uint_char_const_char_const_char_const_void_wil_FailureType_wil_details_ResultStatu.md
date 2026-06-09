# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140006668`
- end: `0x140006974`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x140003c38`
- `0x140003fb8`
- `0x14001e124`

## callees

- `0x140003b70`
- `0x140005964`
- `0x140006280`
- `0x140006668`
- `0x1400075fc`
- `0x140007620`
- `0x140007784`
- `0x1400077a4`
- `0x140009694`
- `0x140029010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000678b`
- `KERNEL32!GetCurrentThreadId` at `0x14000678b`
- `KERNEL32!OutputDebugStringW` at `0x140006928`
- `KERNEL32!OutputDebugStringW` at `0x140006928`
- `KERNEL32!IsDebuggerPresent` at `0x1400068b0`
- `KERNEL32!IsDebuggerPresent` at `0x1400068b0`

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
0x140006668  mov     [rsp+arg_10], rbx
0x14000666d  mov     [rsp+arg_8], edx
0x140006671  mov     [rsp+arg_0], rcx
0x140006676  push    rbp
0x140006677  push    rsi
0x140006678  push    rdi
0x140006679  push    r12
0x14000667b  push    r13
0x14000667d  push    r14
0x14000667f  push    r15
0x140006681  sub     rsp, 40h
0x140006685  mov     r12, r9
0x140006688  mov     r13, r8
0x14000668b  mov     r10, rcx
0x14000668e  xor     eax, eax
0x140006690  mov     rsi, [rsp+78h+lpOutputString]
0x140006698  mov     [rsi], ax
0x14000669b  mov     rax, [rsp+78h+arg_60]
0x1400066a3  mov     byte ptr [rax], 0
0x1400066a6  mov     r14, [rsp+78h+arg_38]
0x1400066ae  mov     edi, [r14]
0x1400066b1  mov     rbx, [rsp+78h+arg_78]
0x1400066b9  mov     [rbx+8], edi
0x1400066bc  mov     eax, [r14+4]
0x1400066c0  mov     [rbx+0Ch], eax
0x1400066c3  xor     ebp, ebp
0x1400066c5  mov     r15d, [rsp+78h+arg_30]
0x1400066cd  mov     ecx, r15d
0x1400066d0  test    r15d, r15d
0x1400066d3  jz      short loc_14000673B
0x1400066d5  sub     ecx, 1
0x1400066d8  jz      short loc_140006732
0x1400066da  sub     ecx, 1
0x1400066dd  jz      short loc_1400066ED
0x1400066df  cmp     ecx, 1
0x1400066e2  jnz     short loc_140006744
0x1400066e4  mov     ecx, edi; this
0x1400066e6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400066eb  jmp     short loc_140006742
0x1400066ed  test    edi, edi
0x1400066ef  js      short loc_140006729
0x1400066f1  mov     edi, 8007029Ch
0x1400066f6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400066fa  mov     rax, [rsp+78h+arg_28]
0x140006702  mov     [rsp+78h+var_50], rax; __int64
0x140006707  mov     rax, [rsp+78h+arg_20]
0x14000670f  mov     [rsp+78h+var_58], rax; __int64
0x140006714  mov     rcx, r10; int
0x140006717  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000671c  mov     [rbx+8], edi
0x14000671f  mov     ecx, edi; this
0x140006721  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006726  mov     [rbx+0Ch], eax
0x140006729  mov     ecx, edi; this
0x14000672b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140006730  jmp     short loc_140006742
0x140006732  mov     ecx, edi; this
0x140006734  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006739  jmp     short loc_140006742
0x14000673b  mov     ecx, edi; this
0x14000673d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140006742  mov     ebp, eax
0x140006744  mov     [rbx], r15d
0x140006747  mov     eax, [rsp+78h+arg_70]
0x14000674e  mov     [rbx+4], eax
0x140006751  cmp     dword ptr [r14+8], 1
0x140006756  jnz     short loc_14000675E
0x140006758  or      eax, 8
0x14000675b  mov     [rbx+4], eax
0x14000675e  mov     eax, 1
0x140006763  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000676b  inc     eax
0x14000676d  mov     [rbx+10h], eax
0x140006770  mov     rax, [rsp+78h+arg_40]
0x140006778  xor     edi, edi
0x14000677a  test    rax, rax
0x14000677d  jz      short loc_140006784
0x14000677f  cmp     [rax], di
0x140006782  jnz     short loc_140006787
0x140006784  mov     rax, rdi
0x140006787  mov     [rbx+18h], rax
0x14000678b  call    cs:__imp_GetCurrentThreadId
0x140006792  nop     dword ptr [rax+rax+00h]
0x140006797  mov     [rbx+20h], eax
0x14000679a  mov     [rbx+38h], r13
0x14000679e  mov     eax, [rsp+78h+arg_8]
0x1400067a5  mov     [rbx+40h], eax
0x1400067a8  mov     [rbx+44h], ebp
0x1400067ab  mov     rax, [rsp+78h+arg_20]
0x1400067b3  mov     [rbx+28h], rax
0x1400067b7  mov     [rbx+30h], r12
0x1400067bb  mov     rax, [rsp+78h+arg_28]
0x1400067c3  mov     [rbx+88h], rax
0x1400067ca  mov     rax, [rsp+78h+arg_0]
0x1400067d2  mov     [rbx+90h], rax
0x1400067d9  mov     [rbx+48h], rdi
0x1400067dd  xorps   xmm0, xmm0
0x1400067e0  xor     eax, eax
0x1400067e2  movups  xmmword ptr [rbx+68h], xmm0
0x1400067e6  mov     [rbx+78h], rax
0x1400067ea  movups  xmmword ptr [rbx+50h], xmm0
0x1400067ee  mov     [rbx+60h], rax
0x1400067f2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400067f9  test    rax, rax
0x1400067fc  jz      short loc_140006805
0x1400067fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006803  jmp     short loc_140006808
0x140006805  mov     rax, rdi
0x140006808  mov     [rbx+80h], rax
0x14000680f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006816  test    rax, rax
0x140006819  jz      short loc_140006823
0x14000681b  mov     rcx, rbx
0x14000681e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006823  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000682a  test    rax, rax
0x14000682d  jz      short loc_140006845
0x14000682f  mov     r8d, 400h
0x140006835  mov     rdx, [rsp+78h+arg_60]
0x14000683d  mov     rcx, rbx
0x140006840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006845  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000684c  test    rax, rax
0x14000684f  jz      short loc_140006859
0x140006851  mov     rcx, rbx
0x140006854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006859  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006860  test    rax, rax
0x140006863  jz      short loc_140006873
0x140006865  test    byte ptr [rbx+4], 2
0x140006869  jnz     short loc_140006873
0x14000686b  mov     rcx, rbx
0x14000686e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006873  cmp     [rbx+8], edi
0x140006876  jl      short loc_140006892
0x140006878  cmp     r15d, 3
0x14000687c  jnz     loc_14000696E
0x140006882  mov     ecx, 8000FFFFh; this
0x140006887  mov     [rbx+8], ecx
0x14000688a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000688f  mov     [rbx+0Ch], eax
0x140006892  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140006899  jnz     short loc_1400068C0
0x14000689b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400068a2  test    rax, rax
0x1400068a5  jz      short loc_1400068B0
0x1400068a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068ac  test    al, al
0x1400068ae  jmp     short loc_1400068BE
0x1400068b0  call    cs:__imp_IsDebuggerPresent
0x1400068b7  nop     dword ptr [rax+rax+00h]
0x1400068bc  test    eax, eax
0x1400068be  jz      short loc_1400068C6
0x1400068c0  test    byte ptr [rbx+4], 2
0x1400068c4  jz      short loc_1400068EA
0x1400068c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400068cd  test    rax, rax
0x1400068d0  jz      short loc_140006934
0x1400068d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400068d9  jnz     short loc_140006934
0x1400068db  xor     r8d, r8d
0x1400068de  xor     edx, edx
0x1400068e0  mov     rcx, rbx
0x1400068e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068e8  jmp     short loc_140006934
0x1400068ea  mov     ebp, 800h
0x1400068ef  mov     rax, cs:g_pfnResultLoggingCallback
0x1400068f6  test    rax, rax
0x1400068f9  jz      short loc_140006912
0x1400068fb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006902  jnz     short loc_140006912
0x140006904  mov     r8d, ebp
0x140006907  mov     rdx, rsi
0x14000690a  mov     rcx, rbx
0x14000690d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006912  cmp     [rsi], di
0x140006915  jnz     short loc_140006925
0x140006917  mov     r8, rbx; unsigned __int64
0x14000691a  mov     rdx, rbp; unsigned __int16 *
0x14000691d  mov     rcx, rsi; this
0x140006920  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006925  mov     rcx, rsi; lpOutputString
0x140006928  call    cs:__imp_OutputDebugStringW
0x14000692f  nop     dword ptr [rax+rax+00h]
0x140006934  test    byte ptr [rbx+4], 4
0x140006938  jnz     short loc_140006943
0x14000693a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140006941  jz      short loc_140006955
0x140006943  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000694a  test    rax, rax
0x14000694d  jz      short loc_140006955
0x14000694f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006954  nop
0x140006955  mov     rbx, [rsp+78h+arg_10]
0x14000695d  add     rsp, 40h
0x140006961  pop     r15
0x140006963  pop     r14
0x140006965  pop     r13
0x140006967  pop     r12
0x140006969  pop     rdi
0x14000696a  pop     rsi
0x14000696b  pop     rbp
0x14000696c  retn
0x14000696e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
