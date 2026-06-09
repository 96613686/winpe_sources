# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004664`
- end: `0x14000495c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140003700`

## callees

- `0x14000313c`
- `0x140003fdc`
- `0x1400044a0`
- `0x140004664`
- `0x140004b4c`
- `0x140004b68`
- `0x140004b7c`
- `0x140004b98`
- `0x140005464`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004787`
- `KERNEL32!GetCurrentThreadId` at `0x140004787`
- `KERNEL32!OutputDebugStringW` at `0x140004918`
- `KERNEL32!OutputDebugStringW` at `0x140004918`
- `KERNEL32!IsDebuggerPresent` at `0x1400048a6`
- `KERNEL32!IsDebuggerPresent` at `0x1400048a6`

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
0x140004664  mov     [rsp+arg_10], rbx
0x140004669  mov     [rsp+arg_8], edx
0x14000466d  mov     [rsp+arg_0], rcx
0x140004672  push    rbp
0x140004673  push    rsi
0x140004674  push    rdi
0x140004675  push    r12
0x140004677  push    r13
0x140004679  push    r14
0x14000467b  push    r15
0x14000467d  sub     rsp, 40h
0x140004681  mov     r14, [rsp+78h+arg_38]
0x140004689  xor     eax, eax
0x14000468b  mov     rbx, [rsp+78h+arg_78]
0x140004693  xor     ebp, ebp
0x140004695  mov     r15d, [rsp+78h+arg_30]
0x14000469d  mov     r10, rcx
0x1400046a0  mov     rsi, [rsp+78h+lpOutputString]
0x1400046a8  mov     r12, r9
0x1400046ab  mov     r13, r8
0x1400046ae  mov     ecx, r15d
0x1400046b1  mov     [rsi], ax
0x1400046b4  mov     rax, [rsp+78h+arg_60]
0x1400046bc  mov     byte ptr [rax], 0
0x1400046bf  mov     edi, [r14]
0x1400046c2  mov     [rbx+8], edi
0x1400046c5  mov     eax, [r14+4]
0x1400046c9  mov     [rbx+0Ch], eax
0x1400046cc  test    r15d, r15d
0x1400046cf  jz      short loc_140004737
0x1400046d1  sub     ecx, 1
0x1400046d4  jz      short loc_14000472E
0x1400046d6  sub     ecx, 1
0x1400046d9  jz      short loc_1400046E9
0x1400046db  cmp     ecx, 1
0x1400046de  jnz     short loc_140004740
0x1400046e0  mov     ecx, edi; this
0x1400046e2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400046e7  jmp     short loc_14000473E
0x1400046e9  test    edi, edi
0x1400046eb  js      short loc_140004725
0x1400046ed  mov     rax, [rsp+78h+arg_28]
0x1400046f5  mov     edi, 8007029Ch
0x1400046fa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400046fe  mov     rcx, r10; int
0x140004701  mov     [rsp+78h+var_50], rax; __int64
0x140004706  mov     rax, [rsp+78h+arg_20]
0x14000470e  mov     [rsp+78h+var_58], rax; __int64
0x140004713  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004718  mov     ecx, edi; this
0x14000471a  mov     [rbx+8], edi
0x14000471d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004722  mov     [rbx+0Ch], eax
0x140004725  mov     ecx, edi; this
0x140004727  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000472c  jmp     short loc_14000473E
0x14000472e  mov     ecx, edi; this
0x140004730  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004735  jmp     short loc_14000473E
0x140004737  mov     ecx, edi; this
0x140004739  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000473e  mov     ebp, eax
0x140004740  mov     eax, [rsp+78h+arg_70]
0x140004747  mov     [rbx+4], eax
0x14000474a  mov     [rbx], r15d
0x14000474d  cmp     dword ptr [r14+8], 1
0x140004752  jnz     short loc_14000475A
0x140004754  or      eax, 8
0x140004757  mov     [rbx+4], eax
0x14000475a  mov     eax, 1
0x14000475f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004767  inc     eax
0x140004769  xor     edi, edi
0x14000476b  mov     [rbx+10h], eax
0x14000476e  mov     rax, [rsp+78h+arg_40]
0x140004776  test    rax, rax
0x140004779  jz      short loc_140004780
0x14000477b  cmp     [rax], di
0x14000477e  jnz     short loc_140004783
0x140004780  mov     rax, rdi
0x140004783  mov     [rbx+18h], rax
0x140004787  call    cs:__imp_GetCurrentThreadId
0x14000478d  mov     [rbx+38h], r13
0x140004791  xorps   xmm0, xmm0
0x140004794  mov     [rbx+20h], eax
0x140004797  mov     eax, [rsp+78h+arg_8]
0x14000479e  mov     [rbx+40h], eax
0x1400047a1  mov     rax, [rsp+78h+arg_20]
0x1400047a9  mov     [rbx+28h], rax
0x1400047ad  mov     rax, [rsp+78h+arg_28]
0x1400047b5  mov     [rbx+88h], rax
0x1400047bc  mov     rax, [rsp+78h+arg_0]
0x1400047c4  mov     [rbx+90h], rax
0x1400047cb  xor     eax, eax
0x1400047cd  mov     [rbx+44h], ebp
0x1400047d0  mov     [rbx+30h], r12
0x1400047d4  mov     [rbx+48h], rdi
0x1400047d8  movups  xmmword ptr [rbx+68h], xmm0
0x1400047dc  mov     [rbx+78h], rax
0x1400047e0  movups  xmmword ptr [rbx+50h], xmm0
0x1400047e4  mov     [rbx+60h], rax
0x1400047e8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400047ef  test    rax, rax
0x1400047f2  jz      short loc_1400047FB
0x1400047f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047f9  jmp     short loc_1400047FE
0x1400047fb  mov     rax, rdi
0x1400047fe  mov     [rbx+80h], rax
0x140004805  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000480c  test    rax, rax
0x14000480f  jz      short loc_140004819
0x140004811  mov     rcx, rbx
0x140004814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004819  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004820  test    rax, rax
0x140004823  jz      short loc_14000483B
0x140004825  mov     rdx, [rsp+78h+arg_60]
0x14000482d  mov     r8d, 400h
0x140004833  mov     rcx, rbx
0x140004836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000483b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004842  test    rax, rax
0x140004845  jz      short loc_14000484F
0x140004847  mov     rcx, rbx
0x14000484a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000484f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004856  test    rax, rax
0x140004859  jz      short loc_140004869
0x14000485b  test    byte ptr [rbx+4], 2
0x14000485f  jnz     short loc_140004869
0x140004861  mov     rcx, rbx
0x140004864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004869  cmp     [rbx+8], edi
0x14000486c  jl      short loc_140004888
0x14000486e  cmp     r15d, 3
0x140004872  jnz     loc_140004956
0x140004878  mov     ecx, 8000FFFFh; this
0x14000487d  mov     [rbx+8], ecx
0x140004880  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004885  mov     [rbx+0Ch], eax
0x140004888  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000488f  jnz     short loc_1400048B0
0x140004891  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004898  test    rax, rax
0x14000489b  jz      short loc_1400048A6
0x14000489d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048a2  test    al, al
0x1400048a4  jmp     short loc_1400048AE
0x1400048a6  call    cs:__imp_IsDebuggerPresent
0x1400048ac  test    eax, eax
0x1400048ae  jz      short loc_1400048B6
0x1400048b0  test    byte ptr [rbx+4], 2
0x1400048b4  jz      short loc_1400048DA
0x1400048b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400048bd  test    rax, rax
0x1400048c0  jz      short loc_14000491E
0x1400048c2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400048c9  jnz     short loc_14000491E
0x1400048cb  xor     r8d, r8d
0x1400048ce  xor     edx, edx
0x1400048d0  mov     rcx, rbx
0x1400048d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048d8  jmp     short loc_14000491E
0x1400048da  mov     rax, cs:g_pfnResultLoggingCallback
0x1400048e1  mov     ebp, 800h
0x1400048e6  test    rax, rax
0x1400048e9  jz      short loc_140004902
0x1400048eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400048f2  jnz     short loc_140004902
0x1400048f4  mov     r8d, ebp
0x1400048f7  mov     rdx, rsi
0x1400048fa  mov     rcx, rbx
0x1400048fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004902  cmp     [rsi], di
0x140004905  jnz     short loc_140004915
0x140004907  mov     r8, rbx; unsigned __int64
0x14000490a  mov     rdx, rbp; unsigned __int16 *
0x14000490d  mov     rcx, rsi; this
0x140004910  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004915  mov     rcx, rsi; lpOutputString
0x140004918  call    cs:__imp_OutputDebugStringW
0x14000491e  test    byte ptr [rbx+4], 4
0x140004922  jnz     short loc_14000492D
0x140004924  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000492b  jz      short loc_14000493E
0x14000492d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004934  test    rax, rax
0x140004937  jz      short loc_14000493E
0x140004939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000493e  mov     rbx, [rsp+78h+arg_10]
0x140004946  add     rsp, 40h
0x14000494a  pop     r15
0x14000494c  pop     r14
0x14000494e  pop     r13
0x140004950  pop     r12
0x140004952  pop     rdi
0x140004953  pop     rsi
0x140004954  pop     rbp
0x140004955  retn
0x140004956  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
