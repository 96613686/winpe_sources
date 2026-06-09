# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000dee8`
- end: `0x18000e1e1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180008c54`

## callees

- `0x180008690`
- `0x18000b984`
- `0x18000cb7c`
- `0x18000dee8`
- `0x18000eadc`
- `0x18000eb00`
- `0x18000ec2c`
- `0x18000eddc`
- `0x1800125a4`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000e00b`
- `KERNEL32!GetCurrentThreadId` at `0x18000e00b`
- `KERNEL32!IsDebuggerPresent` at `0x18000e12a`
- `KERNEL32!IsDebuggerPresent` at `0x18000e12a`
- `KERNEL32!OutputDebugStringW` at `0x18000e19c`
- `KERNEL32!OutputDebugStringW` at `0x18000e19c`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x18000dee8  mov     [rsp+arg_10], rbx
0x18000deed  mov     [rsp+arg_8], edx
0x18000def1  mov     [rsp+arg_0], rcx
0x18000def6  push    rbp
0x18000def7  push    rsi
0x18000def8  push    rdi
0x18000def9  push    r12
0x18000defb  push    r13
0x18000defd  push    r14
0x18000deff  push    r15
0x18000df01  sub     rsp, 40h
0x18000df05  mov     r12, r9
0x18000df08  mov     r13, r8
0x18000df0b  mov     r10, rcx
0x18000df0e  xor     eax, eax
0x18000df10  mov     rsi, [rsp+78h+lpOutputString]
0x18000df18  mov     [rsi], ax
0x18000df1b  mov     rax, [rsp+78h+arg_60]
0x18000df23  mov     byte ptr [rax], 0
0x18000df26  mov     r14, [rsp+78h+arg_38]
0x18000df2e  mov     edi, [r14]
0x18000df31  mov     rbx, [rsp+78h+arg_78]
0x18000df39  mov     [rbx+8], edi
0x18000df3c  mov     eax, [r14+4]
0x18000df40  mov     [rbx+0Ch], eax
0x18000df43  xor     ebp, ebp
0x18000df45  mov     r15d, [rsp+78h+arg_30]
0x18000df4d  mov     ecx, r15d
0x18000df50  test    r15d, r15d
0x18000df53  jz      short loc_18000DFBB
0x18000df55  sub     ecx, 1
0x18000df58  jz      short loc_18000DFB2
0x18000df5a  sub     ecx, 1
0x18000df5d  jz      short loc_18000DF6D
0x18000df5f  cmp     ecx, 1
0x18000df62  jnz     short loc_18000DFC4
0x18000df64  mov     ecx, edi; this
0x18000df66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000df6b  jmp     short loc_18000DFC2
0x18000df6d  test    edi, edi
0x18000df6f  js      short loc_18000DFA9
0x18000df71  mov     edi, 8007029Ch
0x18000df76  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000df7a  mov     rax, [rsp+78h+arg_28]
0x18000df82  mov     [rsp+78h+var_50], rax; __int64
0x18000df87  mov     rax, [rsp+78h+arg_20]
0x18000df8f  mov     [rsp+78h+var_58], rax; __int64
0x18000df94  mov     rcx, r10; int
0x18000df97  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000df9c  mov     [rbx+8], edi
0x18000df9f  mov     ecx, edi; this
0x18000dfa1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000dfa6  mov     [rbx+0Ch], eax
0x18000dfa9  mov     ecx, edi; this
0x18000dfab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000dfb0  jmp     short loc_18000DFC2
0x18000dfb2  mov     ecx, edi; this
0x18000dfb4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000dfb9  jmp     short loc_18000DFC2
0x18000dfbb  mov     ecx, edi; this
0x18000dfbd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000dfc2  mov     ebp, eax
0x18000dfc4  mov     [rbx], r15d
0x18000dfc7  mov     eax, [rsp+78h+arg_70]
0x18000dfce  mov     [rbx+4], eax
0x18000dfd1  cmp     dword ptr [r14+8], 1
0x18000dfd6  jnz     short loc_18000DFDE
0x18000dfd8  or      eax, 8
0x18000dfdb  mov     [rbx+4], eax
0x18000dfde  mov     eax, 1
0x18000dfe3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000dfeb  inc     eax
0x18000dfed  mov     [rbx+10h], eax
0x18000dff0  mov     rax, [rsp+78h+arg_40]
0x18000dff8  xor     edi, edi
0x18000dffa  test    rax, rax
0x18000dffd  jz      short loc_18000E004
0x18000dfff  cmp     [rax], di
0x18000e002  jnz     short loc_18000E007
0x18000e004  mov     rax, rdi
0x18000e007  mov     [rbx+18h], rax
0x18000e00b  call    cs:__imp_GetCurrentThreadId
0x18000e011  mov     [rbx+20h], eax
0x18000e014  mov     [rbx+38h], r13
0x18000e018  mov     eax, [rsp+78h+arg_8]
0x18000e01f  mov     [rbx+40h], eax
0x18000e022  mov     [rbx+44h], ebp
0x18000e025  mov     rax, [rsp+78h+arg_20]
0x18000e02d  mov     [rbx+28h], rax
0x18000e031  mov     [rbx+30h], r12
0x18000e035  mov     rax, [rsp+78h+arg_28]
0x18000e03d  mov     [rbx+88h], rax
0x18000e044  mov     rax, [rsp+78h+arg_0]
0x18000e04c  mov     [rbx+90h], rax
0x18000e053  mov     [rbx+48h], rdi
0x18000e057  xorps   xmm0, xmm0
0x18000e05a  xor     eax, eax
0x18000e05c  movups  xmmword ptr [rbx+68h], xmm0
0x18000e060  mov     [rbx+78h], rax
0x18000e064  movups  xmmword ptr [rbx+50h], xmm0
0x18000e068  mov     [rbx+60h], rax
0x18000e06c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e073  test    rax, rax
0x18000e076  jz      short loc_18000E07F
0x18000e078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e07d  jmp     short loc_18000E082
0x18000e07f  mov     rax, rdi
0x18000e082  mov     [rbx+80h], rax
0x18000e089  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e090  test    rax, rax
0x18000e093  jz      short loc_18000E09D
0x18000e095  mov     rcx, rbx
0x18000e098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e09d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e0a4  test    rax, rax
0x18000e0a7  jz      short loc_18000E0BF
0x18000e0a9  mov     r8d, 400h
0x18000e0af  mov     rdx, [rsp+78h+arg_60]
0x18000e0b7  mov     rcx, rbx
0x18000e0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0bf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e0c6  test    rax, rax
0x18000e0c9  jz      short loc_18000E0D3
0x18000e0cb  mov     rcx, rbx
0x18000e0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e0da  test    rax, rax
0x18000e0dd  jz      short loc_18000E0ED
0x18000e0df  test    byte ptr [rbx+4], 2
0x18000e0e3  jnz     short loc_18000E0ED
0x18000e0e5  mov     rcx, rbx
0x18000e0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0ed  cmp     [rbx+8], edi
0x18000e0f0  jl      short loc_18000E10C
0x18000e0f2  cmp     r15d, 3
0x18000e0f6  jnz     loc_18000E1DB
0x18000e0fc  mov     ecx, 8000FFFFh; this
0x18000e101  mov     [rbx+8], ecx
0x18000e104  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e109  mov     [rbx+0Ch], eax
0x18000e10c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000e113  jnz     short loc_18000E134
0x18000e115  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e11c  test    rax, rax
0x18000e11f  jz      short loc_18000E12A
0x18000e121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e126  test    al, al
0x18000e128  jmp     short loc_18000E132
0x18000e12a  call    cs:__imp_IsDebuggerPresent
0x18000e130  test    eax, eax
0x18000e132  jz      short loc_18000E13A
0x18000e134  test    byte ptr [rbx+4], 2
0x18000e138  jz      short loc_18000E15E
0x18000e13a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e141  test    rax, rax
0x18000e144  jz      short loc_18000E1A2
0x18000e146  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e14d  jnz     short loc_18000E1A2
0x18000e14f  xor     r8d, r8d
0x18000e152  xor     edx, edx
0x18000e154  mov     rcx, rbx
0x18000e157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e15c  jmp     short loc_18000E1A2
0x18000e15e  mov     ebp, 800h
0x18000e163  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e16a  test    rax, rax
0x18000e16d  jz      short loc_18000E186
0x18000e16f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e176  jnz     short loc_18000E186
0x18000e178  mov     r8d, ebp
0x18000e17b  mov     rdx, rsi
0x18000e17e  mov     rcx, rbx
0x18000e181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e186  cmp     [rsi], di
0x18000e189  jnz     short loc_18000E199
0x18000e18b  mov     r8, rbx; unsigned __int64
0x18000e18e  mov     rdx, rbp; unsigned __int16 *
0x18000e191  mov     rcx, rsi; this
0x18000e194  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e199  mov     rcx, rsi; lpOutputString
0x18000e19c  call    cs:__imp_OutputDebugStringW
0x18000e1a2  test    byte ptr [rbx+4], 4
0x18000e1a6  jnz     short loc_18000E1B1
0x18000e1a8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000e1af  jz      short loc_18000E1C3
0x18000e1b1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e1b8  test    rax, rax
0x18000e1bb  jz      short loc_18000E1C3
0x18000e1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1c2  nop
0x18000e1c3  mov     rbx, [rsp+78h+arg_10]
0x18000e1cb  add     rsp, 40h
0x18000e1cf  pop     r15
0x18000e1d1  pop     r14
0x18000e1d3  pop     r13
0x18000e1d5  pop     r12
0x18000e1d7  pop     rdi
0x18000e1d8  pop     rsi
0x18000e1d9  pop     rbp
0x18000e1da  retn
0x18000e1db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
