# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180038f68`
- end: `0x180039261`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18002eb48`
- `0x18003828c`
- `0x1800405e8`

## callees

- `0x18002be10`
- `0x18002e114`
- `0x180037f94`
- `0x180038a48`
- `0x180038f68`
- `0x1800394a0`
- `0x1800394c0`
- `0x1800394d4`
- `0x180039908`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003908b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003908b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800391aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800391aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003921c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003921c`

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
0x180038f68  mov     [rsp+arg_10], rbx
0x180038f6d  mov     [rsp+arg_8], edx
0x180038f71  mov     [rsp+arg_0], rcx
0x180038f76  push    rbp
0x180038f77  push    rsi
0x180038f78  push    rdi
0x180038f79  push    r12
0x180038f7b  push    r13
0x180038f7d  push    r14
0x180038f7f  push    r15
0x180038f81  sub     rsp, 40h
0x180038f85  mov     r12, r9
0x180038f88  mov     r13, r8
0x180038f8b  mov     r10, rcx
0x180038f8e  xor     eax, eax
0x180038f90  mov     rsi, [rsp+78h+lpOutputString]
0x180038f98  mov     [rsi], ax
0x180038f9b  mov     rax, [rsp+78h+arg_60]
0x180038fa3  mov     byte ptr [rax], 0
0x180038fa6  mov     r14, [rsp+78h+arg_38]
0x180038fae  mov     edi, [r14]
0x180038fb1  mov     rbx, [rsp+78h+arg_78]
0x180038fb9  mov     [rbx+8], edi
0x180038fbc  mov     eax, [r14+4]
0x180038fc0  mov     [rbx+0Ch], eax
0x180038fc3  xor     ebp, ebp
0x180038fc5  mov     r15d, [rsp+78h+arg_30]
0x180038fcd  mov     ecx, r15d
0x180038fd0  test    r15d, r15d
0x180038fd3  jz      short loc_18003903B
0x180038fd5  sub     ecx, 1
0x180038fd8  jz      short loc_180039032
0x180038fda  sub     ecx, 1
0x180038fdd  jz      short loc_180038FED
0x180038fdf  cmp     ecx, 1
0x180038fe2  jnz     short loc_180039044
0x180038fe4  mov     ecx, edi; this
0x180038fe6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180038feb  jmp     short loc_180039042
0x180038fed  test    edi, edi
0x180038fef  js      short loc_180039029
0x180038ff1  mov     edi, 8007029Ch
0x180038ff6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180038ffa  mov     rax, [rsp+78h+arg_28]
0x180039002  mov     [rsp+78h+var_50], rax; __int64
0x180039007  mov     rax, [rsp+78h+arg_20]
0x18003900f  mov     [rsp+78h+var_58], rax; __int64
0x180039014  mov     rcx, r10; int
0x180039017  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003901c  mov     [rbx+8], edi
0x18003901f  mov     ecx, edi; this
0x180039021  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180039026  mov     [rbx+0Ch], eax
0x180039029  mov     ecx, edi; this
0x18003902b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180039030  jmp     short loc_180039042
0x180039032  mov     ecx, edi; this
0x180039034  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180039039  jmp     short loc_180039042
0x18003903b  mov     ecx, edi; this
0x18003903d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180039042  mov     ebp, eax
0x180039044  mov     [rbx], r15d
0x180039047  mov     eax, [rsp+78h+arg_70]
0x18003904e  mov     [rbx+4], eax
0x180039051  cmp     dword ptr [r14+8], 1
0x180039056  jnz     short loc_18003905E
0x180039058  or      eax, 8
0x18003905b  mov     [rbx+4], eax
0x18003905e  mov     eax, 1
0x180039063  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003906b  inc     eax
0x18003906d  mov     [rbx+10h], eax
0x180039070  mov     rax, [rsp+78h+arg_40]
0x180039078  xor     edi, edi
0x18003907a  test    rax, rax
0x18003907d  jz      short loc_180039084
0x18003907f  cmp     [rax], di
0x180039082  jnz     short loc_180039087
0x180039084  mov     rax, rdi
0x180039087  mov     [rbx+18h], rax
0x18003908b  call    cs:__imp_GetCurrentThreadId
0x180039091  mov     [rbx+20h], eax
0x180039094  mov     [rbx+38h], r13
0x180039098  mov     eax, [rsp+78h+arg_8]
0x18003909f  mov     [rbx+40h], eax
0x1800390a2  mov     [rbx+44h], ebp
0x1800390a5  mov     rax, [rsp+78h+arg_20]
0x1800390ad  mov     [rbx+28h], rax
0x1800390b1  mov     [rbx+30h], r12
0x1800390b5  mov     rax, [rsp+78h+arg_28]
0x1800390bd  mov     [rbx+88h], rax
0x1800390c4  mov     rax, [rsp+78h+arg_0]
0x1800390cc  mov     [rbx+90h], rax
0x1800390d3  mov     [rbx+48h], rdi
0x1800390d7  xorps   xmm0, xmm0
0x1800390da  xor     eax, eax
0x1800390dc  movups  xmmword ptr [rbx+68h], xmm0
0x1800390e0  mov     [rbx+78h], rax
0x1800390e4  movups  xmmword ptr [rbx+50h], xmm0
0x1800390e8  mov     [rbx+60h], rax
0x1800390ec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800390f3  test    rax, rax
0x1800390f6  jz      short loc_1800390FF
0x1800390f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390fd  jmp     short loc_180039102
0x1800390ff  mov     rax, rdi
0x180039102  mov     [rbx+80h], rax
0x180039109  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180039110  test    rax, rax
0x180039113  jz      short loc_18003911D
0x180039115  mov     rcx, rbx
0x180039118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003911d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180039124  test    rax, rax
0x180039127  jz      short loc_18003913F
0x180039129  mov     r8d, 400h
0x18003912f  mov     rdx, [rsp+78h+arg_60]
0x180039137  mov     rcx, rbx
0x18003913a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003913f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180039146  test    rax, rax
0x180039149  jz      short loc_180039153
0x18003914b  mov     rcx, rbx
0x18003914e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039153  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003915a  test    rax, rax
0x18003915d  jz      short loc_18003916D
0x18003915f  test    byte ptr [rbx+4], 2
0x180039163  jnz     short loc_18003916D
0x180039165  mov     rcx, rbx
0x180039168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003916d  cmp     [rbx+8], edi
0x180039170  jl      short loc_18003918C
0x180039172  cmp     r15d, 3
0x180039176  jnz     loc_18003925B
0x18003917c  mov     ecx, 8000FFFFh; this
0x180039181  mov     [rbx+8], ecx
0x180039184  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180039189  mov     [rbx+0Ch], eax
0x18003918c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180039193  jnz     short loc_1800391B4
0x180039195  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003919c  test    rax, rax
0x18003919f  jz      short loc_1800391AA
0x1800391a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391a6  test    al, al
0x1800391a8  jmp     short loc_1800391B2
0x1800391aa  call    cs:__imp_IsDebuggerPresent
0x1800391b0  test    eax, eax
0x1800391b2  jz      short loc_1800391BA
0x1800391b4  test    byte ptr [rbx+4], 2
0x1800391b8  jz      short loc_1800391DE
0x1800391ba  mov     rax, cs:g_pfnResultLoggingCallback
0x1800391c1  test    rax, rax
0x1800391c4  jz      short loc_180039222
0x1800391c6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800391cd  jnz     short loc_180039222
0x1800391cf  xor     r8d, r8d
0x1800391d2  xor     edx, edx
0x1800391d4  mov     rcx, rbx
0x1800391d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391dc  jmp     short loc_180039222
0x1800391de  mov     ebp, 800h
0x1800391e3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800391ea  test    rax, rax
0x1800391ed  jz      short loc_180039206
0x1800391ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800391f6  jnz     short loc_180039206
0x1800391f8  mov     r8d, ebp
0x1800391fb  mov     rdx, rsi
0x1800391fe  mov     rcx, rbx
0x180039201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039206  cmp     [rsi], di
0x180039209  jnz     short loc_180039219
0x18003920b  mov     r8, rbx; unsigned __int64
0x18003920e  mov     rdx, rbp; unsigned __int16 *
0x180039211  mov     rcx, rsi; this
0x180039214  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180039219  mov     rcx, rsi; lpOutputString
0x18003921c  call    cs:__imp_OutputDebugStringW
0x180039222  test    byte ptr [rbx+4], 4
0x180039226  jnz     short loc_180039231
0x180039228  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003922f  jz      short loc_180039243
0x180039231  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180039238  test    rax, rax
0x18003923b  jz      short loc_180039243
0x18003923d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039242  nop
0x180039243  mov     rbx, [rsp+78h+arg_10]
0x18003924b  add     rsp, 40h
0x18003924f  pop     r15
0x180039251  pop     r14
0x180039253  pop     r13
0x180039255  pop     r12
0x180039257  pop     rdi
0x180039258  pop     rsi
0x180039259  pop     rbp
0x18003925a  retn
0x18003925b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
