# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180023570`
- end: `0x180023869`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180021a78`
- `0x180021dc4`

## callees

- `0x1800219b8`
- `0x1800229c4`
- `0x1800233ac`
- `0x180023570`
- `0x180023bd0`
- `0x180023bf0`
- `0x180023c04`
- `0x180023c20`
- `0x180024a94`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023693`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023693`
- `KERNEL32!OutputDebugStringW` at `0x180023824`
- `KERNEL32!OutputDebugStringW` at `0x180023824`
- `KERNEL32!IsDebuggerPresent` at `0x1800237b2`
- `KERNEL32!IsDebuggerPresent` at `0x1800237b2`

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
0x180023570  mov     [rsp+arg_10], rbx
0x180023575  mov     [rsp+arg_8], edx
0x180023579  mov     [rsp+arg_0], rcx
0x18002357e  push    rbp
0x18002357f  push    rsi
0x180023580  push    rdi
0x180023581  push    r12
0x180023583  push    r13
0x180023585  push    r14
0x180023587  push    r15
0x180023589  sub     rsp, 40h
0x18002358d  mov     r12, r9
0x180023590  mov     r13, r8
0x180023593  mov     r10, rcx
0x180023596  xor     eax, eax
0x180023598  mov     rsi, [rsp+78h+lpOutputString]
0x1800235a0  mov     [rsi], ax
0x1800235a3  mov     rax, [rsp+78h+arg_60]
0x1800235ab  mov     byte ptr [rax], 0
0x1800235ae  mov     r14, [rsp+78h+arg_38]
0x1800235b6  mov     edi, [r14]
0x1800235b9  mov     rbx, [rsp+78h+arg_78]
0x1800235c1  mov     [rbx+8], edi
0x1800235c4  mov     eax, [r14+4]
0x1800235c8  mov     [rbx+0Ch], eax
0x1800235cb  xor     ebp, ebp
0x1800235cd  mov     r15d, [rsp+78h+arg_30]
0x1800235d5  mov     ecx, r15d
0x1800235d8  test    r15d, r15d
0x1800235db  jz      short loc_180023643
0x1800235dd  sub     ecx, 1
0x1800235e0  jz      short loc_18002363A
0x1800235e2  sub     ecx, 1
0x1800235e5  jz      short loc_1800235F5
0x1800235e7  cmp     ecx, 1
0x1800235ea  jnz     short loc_18002364C
0x1800235ec  mov     ecx, edi; this
0x1800235ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800235f3  jmp     short loc_18002364A
0x1800235f5  test    edi, edi
0x1800235f7  js      short loc_180023631
0x1800235f9  mov     edi, 8007029Ch
0x1800235fe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180023602  mov     rax, [rsp+78h+arg_28]
0x18002360a  mov     [rsp+78h+var_50], rax; __int64
0x18002360f  mov     rax, [rsp+78h+arg_20]
0x180023617  mov     [rsp+78h+var_58], rax; __int64
0x18002361c  mov     rcx, r10; int
0x18002361f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180023624  mov     [rbx+8], edi
0x180023627  mov     ecx, edi; this
0x180023629  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002362e  mov     [rbx+0Ch], eax
0x180023631  mov     ecx, edi; this
0x180023633  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180023638  jmp     short loc_18002364A
0x18002363a  mov     ecx, edi; this
0x18002363c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180023641  jmp     short loc_18002364A
0x180023643  mov     ecx, edi; this
0x180023645  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002364a  mov     ebp, eax
0x18002364c  mov     [rbx], r15d
0x18002364f  mov     eax, [rsp+78h+arg_70]
0x180023656  mov     [rbx+4], eax
0x180023659  cmp     dword ptr [r14+8], 1
0x18002365e  jnz     short loc_180023666
0x180023660  or      eax, 8
0x180023663  mov     [rbx+4], eax
0x180023666  mov     eax, 1
0x18002366b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180023673  inc     eax
0x180023675  mov     [rbx+10h], eax
0x180023678  mov     rax, [rsp+78h+arg_40]
0x180023680  xor     edi, edi
0x180023682  test    rax, rax
0x180023685  jz      short loc_18002368C
0x180023687  cmp     [rax], di
0x18002368a  jnz     short loc_18002368F
0x18002368c  mov     rax, rdi
0x18002368f  mov     [rbx+18h], rax
0x180023693  call    cs:__imp_GetCurrentThreadId
0x180023699  mov     [rbx+20h], eax
0x18002369c  mov     [rbx+38h], r13
0x1800236a0  mov     eax, [rsp+78h+arg_8]
0x1800236a7  mov     [rbx+40h], eax
0x1800236aa  mov     [rbx+44h], ebp
0x1800236ad  mov     rax, [rsp+78h+arg_20]
0x1800236b5  mov     [rbx+28h], rax
0x1800236b9  mov     [rbx+30h], r12
0x1800236bd  mov     rax, [rsp+78h+arg_28]
0x1800236c5  mov     [rbx+88h], rax
0x1800236cc  mov     rax, [rsp+78h+arg_0]
0x1800236d4  mov     [rbx+90h], rax
0x1800236db  mov     [rbx+48h], rdi
0x1800236df  xorps   xmm0, xmm0
0x1800236e2  xor     eax, eax
0x1800236e4  movups  xmmword ptr [rbx+68h], xmm0
0x1800236e8  mov     [rbx+78h], rax
0x1800236ec  movups  xmmword ptr [rbx+50h], xmm0
0x1800236f0  mov     [rbx+60h], rax
0x1800236f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800236fb  test    rax, rax
0x1800236fe  jz      short loc_180023707
0x180023700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023705  jmp     short loc_18002370A
0x180023707  mov     rax, rdi
0x18002370a  mov     [rbx+80h], rax
0x180023711  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180023718  test    rax, rax
0x18002371b  jz      short loc_180023725
0x18002371d  mov     rcx, rbx
0x180023720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023725  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002372c  test    rax, rax
0x18002372f  jz      short loc_180023747
0x180023731  mov     r8d, 400h
0x180023737  mov     rdx, [rsp+78h+arg_60]
0x18002373f  mov     rcx, rbx
0x180023742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023747  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002374e  test    rax, rax
0x180023751  jz      short loc_18002375B
0x180023753  mov     rcx, rbx
0x180023756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002375b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023762  test    rax, rax
0x180023765  jz      short loc_180023775
0x180023767  test    byte ptr [rbx+4], 2
0x18002376b  jnz     short loc_180023775
0x18002376d  mov     rcx, rbx
0x180023770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023775  cmp     [rbx+8], edi
0x180023778  jl      short loc_180023794
0x18002377a  cmp     r15d, 3
0x18002377e  jnz     loc_180023863
0x180023784  mov     ecx, 8000FFFFh; this
0x180023789  mov     [rbx+8], ecx
0x18002378c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180023791  mov     [rbx+0Ch], eax
0x180023794  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002379b  jnz     short loc_1800237BC
0x18002379d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800237a4  test    rax, rax
0x1800237a7  jz      short loc_1800237B2
0x1800237a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237ae  test    al, al
0x1800237b0  jmp     short loc_1800237BA
0x1800237b2  call    cs:__imp_IsDebuggerPresent
0x1800237b8  test    eax, eax
0x1800237ba  jz      short loc_1800237C2
0x1800237bc  test    byte ptr [rbx+4], 2
0x1800237c0  jz      short loc_1800237E6
0x1800237c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800237c9  test    rax, rax
0x1800237cc  jz      short loc_18002382A
0x1800237ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800237d5  jnz     short loc_18002382A
0x1800237d7  xor     r8d, r8d
0x1800237da  xor     edx, edx
0x1800237dc  mov     rcx, rbx
0x1800237df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237e4  jmp     short loc_18002382A
0x1800237e6  mov     ebp, 800h
0x1800237eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800237f2  test    rax, rax
0x1800237f5  jz      short loc_18002380E
0x1800237f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800237fe  jnz     short loc_18002380E
0x180023800  mov     r8d, ebp
0x180023803  mov     rdx, rsi
0x180023806  mov     rcx, rbx
0x180023809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002380e  cmp     [rsi], di
0x180023811  jnz     short loc_180023821
0x180023813  mov     r8, rbx; unsigned __int64
0x180023816  mov     rdx, rbp; unsigned __int16 *
0x180023819  mov     rcx, rsi; this
0x18002381c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180023821  mov     rcx, rsi; lpOutputString
0x180023824  call    cs:__imp_OutputDebugStringW
0x18002382a  test    byte ptr [rbx+4], 4
0x18002382e  jnz     short loc_180023839
0x180023830  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180023837  jz      short loc_18002384B
0x180023839  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180023840  test    rax, rax
0x180023843  jz      short loc_18002384B
0x180023845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002384a  nop
0x18002384b  mov     rbx, [rsp+78h+arg_10]
0x180023853  add     rsp, 40h
0x180023857  pop     r15
0x180023859  pop     r14
0x18002385b  pop     r13
0x18002385d  pop     r12
0x18002385f  pop     rdi
0x180023860  pop     rsi
0x180023861  pop     rbp
0x180023862  retn
0x180023863  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
