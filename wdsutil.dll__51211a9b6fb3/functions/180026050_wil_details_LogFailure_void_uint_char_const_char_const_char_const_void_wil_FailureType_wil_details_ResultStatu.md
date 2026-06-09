# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180026050`
- end: `0x180026364`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800221b8`

## callees

- `0x180021bb4`
- `0x180025564`
- `0x180025d94`
- `0x180026050`
- `0x180027028`
- `0x180027050`
- `0x180027064`
- `0x180027084`
- `0x180028814`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002617b`
- `KERNEL32!GetCurrentThreadId` at `0x18002617b`
- `KERNEL32!OutputDebugStringW` at `0x180026318`
- `KERNEL32!OutputDebugStringW` at `0x180026318`
- `KERNEL32!IsDebuggerPresent` at `0x1800262a0`
- `KERNEL32!IsDebuggerPresent` at `0x1800262a0`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180026050  mov     rax, rsp
0x180026053  mov     [rax+10h], edx
0x180026056  mov     [rax+8], rcx
0x18002605a  push    rbp
0x18002605b  push    rsi
0x18002605c  push    rdi
0x18002605d  push    r12
0x18002605f  push    r13
0x180026061  push    r14
0x180026063  push    r15
0x180026065  sub     rsp, 50h
0x180026069  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180026071  mov     [rax+18h], rbx
0x180026075  mov     r12, r9
0x180026078  mov     r13, r8
0x18002607b  mov     r10, rcx
0x18002607e  xor     eax, eax
0x180026080  mov     rsi, [rsp+88h+lpOutputString]
0x180026088  mov     [rsi], ax
0x18002608b  mov     rax, [rsp+88h+arg_60]
0x180026093  mov     byte ptr [rax], 0
0x180026096  mov     r14, [rsp+88h+arg_38]
0x18002609e  mov     edi, [r14]
0x1800260a1  mov     rbx, [rsp+88h+arg_78]
0x1800260a9  mov     [rbx+8], edi
0x1800260ac  mov     eax, [r14+4]
0x1800260b0  mov     [rbx+0Ch], eax
0x1800260b3  xor     ebp, ebp
0x1800260b5  mov     r15d, [rsp+88h+arg_30]
0x1800260bd  mov     ecx, r15d
0x1800260c0  test    r15d, r15d
0x1800260c3  jz      short loc_18002612B
0x1800260c5  sub     ecx, 1
0x1800260c8  jz      short loc_180026122
0x1800260ca  sub     ecx, 1
0x1800260cd  jz      short loc_1800260DD
0x1800260cf  cmp     ecx, 1
0x1800260d2  jnz     short loc_180026134
0x1800260d4  mov     ecx, edi; this
0x1800260d6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800260db  jmp     short loc_180026132
0x1800260dd  test    edi, edi
0x1800260df  js      short loc_180026119
0x1800260e1  mov     edi, 8007029Ch
0x1800260e6  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x1800260ea  mov     rax, [rsp+88h+arg_28]
0x1800260f2  mov     [rsp+88h+var_60], rax; __int64
0x1800260f7  mov     rax, [rsp+88h+arg_20]
0x1800260ff  mov     [rsp+88h+var_68], rax; __int64
0x180026104  mov     rcx, r10; int
0x180026107  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002610c  mov     [rbx+8], edi
0x18002610f  mov     ecx, edi; this
0x180026111  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180026116  mov     [rbx+0Ch], eax
0x180026119  mov     ecx, edi; this
0x18002611b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180026120  jmp     short loc_180026132
0x180026122  mov     ecx, edi; this
0x180026124  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180026129  jmp     short loc_180026132
0x18002612b  mov     ecx, edi; this
0x18002612d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180026132  mov     ebp, eax
0x180026134  mov     [rbx], r15d
0x180026137  mov     eax, [rsp+88h+arg_70]
0x18002613e  mov     [rbx+4], eax
0x180026141  cmp     dword ptr [r14+8], 1
0x180026146  jnz     short loc_18002614E
0x180026148  or      eax, 8
0x18002614b  mov     [rbx+4], eax
0x18002614e  mov     eax, 1
0x180026153  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002615b  inc     eax
0x18002615d  mov     [rbx+10h], eax
0x180026160  mov     rax, [rsp+88h+arg_40]
0x180026168  xor     edi, edi
0x18002616a  test    rax, rax
0x18002616d  jz      short loc_180026174
0x18002616f  cmp     [rax], di
0x180026172  jnz     short loc_180026177
0x180026174  mov     rax, rdi
0x180026177  mov     [rbx+18h], rax
0x18002617b  call    cs:__imp_GetCurrentThreadId
0x180026182  nop     dword ptr [rax+rax+00h]
0x180026187  mov     [rbx+20h], eax
0x18002618a  mov     [rbx+38h], r13
0x18002618e  mov     eax, [rsp+88h+arg_8]
0x180026195  mov     [rbx+40h], eax
0x180026198  mov     [rbx+44h], ebp
0x18002619b  mov     rax, [rsp+88h+arg_20]
0x1800261a3  mov     [rbx+28h], rax
0x1800261a7  mov     [rbx+30h], r12
0x1800261ab  mov     rax, [rsp+88h+arg_28]
0x1800261b3  mov     [rbx+88h], rax
0x1800261ba  mov     rax, [rsp+88h+arg_0]
0x1800261c2  mov     [rbx+90h], rax
0x1800261c9  mov     [rbx+48h], rdi
0x1800261cd  xorps   xmm0, xmm0
0x1800261d0  xor     eax, eax
0x1800261d2  movups  xmmword ptr [rbx+68h], xmm0
0x1800261d6  mov     [rbx+78h], rax
0x1800261da  movups  xmmword ptr [rbx+50h], xmm0
0x1800261de  mov     [rbx+60h], rax
0x1800261e2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800261e9  test    rax, rax
0x1800261ec  jz      short loc_1800261F5
0x1800261ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261f3  jmp     short loc_1800261F8
0x1800261f5  mov     rax, rdi
0x1800261f8  mov     [rbx+80h], rax
0x1800261ff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180026206  test    rax, rax
0x180026209  jz      short loc_180026213
0x18002620b  mov     rcx, rbx
0x18002620e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026213  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002621a  test    rax, rax
0x18002621d  jz      short loc_180026235
0x18002621f  mov     r8d, 400h
0x180026225  mov     rdx, [rsp+88h+arg_60]
0x18002622d  mov     rcx, rbx
0x180026230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026235  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002623c  test    rax, rax
0x18002623f  jz      short loc_180026249
0x180026241  mov     rcx, rbx
0x180026244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026249  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026250  test    rax, rax
0x180026253  jz      short loc_180026263
0x180026255  test    byte ptr [rbx+4], 2
0x180026259  jnz     short loc_180026263
0x18002625b  mov     rcx, rbx
0x18002625e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026263  cmp     [rbx+8], edi
0x180026266  jl      short loc_180026282
0x180026268  cmp     r15d, 3
0x18002626c  jnz     loc_18002635E
0x180026272  mov     ecx, 8000FFFFh; this
0x180026277  mov     [rbx+8], ecx
0x18002627a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002627f  mov     [rbx+0Ch], eax
0x180026282  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180026289  jnz     short loc_1800262B0
0x18002628b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180026292  test    rax, rax
0x180026295  jz      short loc_1800262A0
0x180026297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002629c  test    al, al
0x18002629e  jmp     short loc_1800262AE
0x1800262a0  call    cs:__imp_IsDebuggerPresent
0x1800262a7  nop     dword ptr [rax+rax+00h]
0x1800262ac  test    eax, eax
0x1800262ae  jz      short loc_1800262B6
0x1800262b0  test    byte ptr [rbx+4], 2
0x1800262b4  jz      short loc_1800262DA
0x1800262b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800262bd  test    rax, rax
0x1800262c0  jz      short loc_180026324
0x1800262c2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800262c9  jnz     short loc_180026324
0x1800262cb  xor     r8d, r8d
0x1800262ce  xor     edx, edx
0x1800262d0  mov     rcx, rbx
0x1800262d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262d8  jmp     short loc_180026324
0x1800262da  mov     ebp, 800h
0x1800262df  mov     rax, cs:g_pfnResultLoggingCallback
0x1800262e6  test    rax, rax
0x1800262e9  jz      short loc_180026302
0x1800262eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800262f2  jnz     short loc_180026302
0x1800262f4  mov     r8d, ebp
0x1800262f7  mov     rdx, rsi
0x1800262fa  mov     rcx, rbx
0x1800262fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026302  cmp     [rsi], di
0x180026305  jnz     short loc_180026315
0x180026307  mov     r8, rbx; unsigned __int64
0x18002630a  mov     rdx, rbp; unsigned __int16 *
0x18002630d  mov     rcx, rsi; this
0x180026310  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180026315  mov     rcx, rsi; lpOutputString
0x180026318  call    cs:__imp_OutputDebugStringW
0x18002631f  nop     dword ptr [rax+rax+00h]
0x180026324  test    byte ptr [rbx+4], 4
0x180026328  jnz     short loc_180026333
0x18002632a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180026331  jz      short loc_180026345
0x180026333  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002633a  test    rax, rax
0x18002633d  jz      short loc_180026345
0x18002633f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026344  nop
0x180026345  mov     rbx, [rsp+88h+arg_10]
0x18002634d  add     rsp, 50h
0x180026351  pop     r15
0x180026353  pop     r14
0x180026355  pop     r13
0x180026357  pop     r12
0x180026359  pop     rdi
0x18002635a  pop     rsi
0x18002635b  pop     rbp
0x18002635c  retn
0x18002635e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
