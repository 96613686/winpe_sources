# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800047bc`
- end: `0x180004ab5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180002eec`
- `0x180003248`
- `0x180026f6c`

## callees

- `0x180002e24`
- `0x180003e24`
- `0x1800045f8`
- `0x1800047bc`
- `0x180004e84`
- `0x180004ea0`
- `0x180004eb4`
- `0x180004ed0`
- `0x180005be0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048df`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004a70`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004a70`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800049fe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800049fe`

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
0x1800047bc  mov     [rsp+arg_10], rbx
0x1800047c1  mov     [rsp+arg_8], edx
0x1800047c5  mov     [rsp+arg_0], rcx
0x1800047ca  push    rbp
0x1800047cb  push    rsi
0x1800047cc  push    rdi
0x1800047cd  push    r12
0x1800047cf  push    r13
0x1800047d1  push    r14
0x1800047d3  push    r15
0x1800047d5  sub     rsp, 40h
0x1800047d9  mov     r12, r9
0x1800047dc  mov     r13, r8
0x1800047df  mov     r10, rcx
0x1800047e2  xor     eax, eax
0x1800047e4  mov     rsi, [rsp+78h+lpOutputString]
0x1800047ec  mov     [rsi], ax
0x1800047ef  mov     rax, [rsp+78h+arg_60]
0x1800047f7  mov     byte ptr [rax], 0
0x1800047fa  mov     r14, [rsp+78h+arg_38]
0x180004802  mov     edi, [r14]
0x180004805  mov     rbx, [rsp+78h+arg_78]
0x18000480d  mov     [rbx+8], edi
0x180004810  mov     eax, [r14+4]
0x180004814  mov     [rbx+0Ch], eax
0x180004817  xor     ebp, ebp
0x180004819  mov     r15d, [rsp+78h+arg_30]
0x180004821  mov     ecx, r15d
0x180004824  test    r15d, r15d
0x180004827  jz      short loc_18000488F
0x180004829  sub     ecx, 1
0x18000482c  jz      short loc_180004886
0x18000482e  sub     ecx, 1
0x180004831  jz      short loc_180004841
0x180004833  cmp     ecx, 1
0x180004836  jnz     short loc_180004898
0x180004838  mov     ecx, edi; this
0x18000483a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000483f  jmp     short loc_180004896
0x180004841  test    edi, edi
0x180004843  js      short loc_18000487D
0x180004845  mov     edi, 8007029Ch
0x18000484a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000484e  mov     rax, [rsp+78h+arg_28]
0x180004856  mov     [rsp+78h+var_50], rax; __int64
0x18000485b  mov     rax, [rsp+78h+arg_20]
0x180004863  mov     [rsp+78h+var_58], rax; __int64
0x180004868  mov     rcx, r10; int
0x18000486b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004870  mov     [rbx+8], edi
0x180004873  mov     ecx, edi; this
0x180004875  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000487a  mov     [rbx+0Ch], eax
0x18000487d  mov     ecx, edi; this
0x18000487f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004884  jmp     short loc_180004896
0x180004886  mov     ecx, edi; this
0x180004888  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000488d  jmp     short loc_180004896
0x18000488f  mov     ecx, edi; this
0x180004891  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004896  mov     ebp, eax
0x180004898  mov     [rbx], r15d
0x18000489b  mov     eax, [rsp+78h+arg_70]
0x1800048a2  mov     [rbx+4], eax
0x1800048a5  cmp     dword ptr [r14+8], 1
0x1800048aa  jnz     short loc_1800048B2
0x1800048ac  or      eax, 8
0x1800048af  mov     [rbx+4], eax
0x1800048b2  mov     eax, 1
0x1800048b7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800048bf  inc     eax
0x1800048c1  mov     [rbx+10h], eax
0x1800048c4  mov     rax, [rsp+78h+arg_40]
0x1800048cc  xor     edi, edi
0x1800048ce  test    rax, rax
0x1800048d1  jz      short loc_1800048D8
0x1800048d3  cmp     [rax], di
0x1800048d6  jnz     short loc_1800048DB
0x1800048d8  mov     rax, rdi
0x1800048db  mov     [rbx+18h], rax
0x1800048df  call    cs:__imp_GetCurrentThreadId
0x1800048e5  mov     [rbx+20h], eax
0x1800048e8  mov     [rbx+38h], r13
0x1800048ec  mov     eax, [rsp+78h+arg_8]
0x1800048f3  mov     [rbx+40h], eax
0x1800048f6  mov     [rbx+44h], ebp
0x1800048f9  mov     rax, [rsp+78h+arg_20]
0x180004901  mov     [rbx+28h], rax
0x180004905  mov     [rbx+30h], r12
0x180004909  mov     rax, [rsp+78h+arg_28]
0x180004911  mov     [rbx+88h], rax
0x180004918  mov     rax, [rsp+78h+arg_0]
0x180004920  mov     [rbx+90h], rax
0x180004927  mov     [rbx+48h], rdi
0x18000492b  xorps   xmm0, xmm0
0x18000492e  xor     eax, eax
0x180004930  movups  xmmword ptr [rbx+68h], xmm0
0x180004934  mov     [rbx+78h], rax
0x180004938  movups  xmmword ptr [rbx+50h], xmm0
0x18000493c  mov     [rbx+60h], rax
0x180004940  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004947  test    rax, rax
0x18000494a  jz      short loc_180004953
0x18000494c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004951  jmp     short loc_180004956
0x180004953  mov     rax, rdi
0x180004956  mov     [rbx+80h], rax
0x18000495d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004964  test    rax, rax
0x180004967  jz      short loc_180004971
0x180004969  mov     rcx, rbx
0x18000496c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004971  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004978  test    rax, rax
0x18000497b  jz      short loc_180004993
0x18000497d  mov     r8d, 400h
0x180004983  mov     rdx, [rsp+78h+arg_60]
0x18000498b  mov     rcx, rbx
0x18000498e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004993  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000499a  test    rax, rax
0x18000499d  jz      short loc_1800049A7
0x18000499f  mov     rcx, rbx
0x1800049a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049a7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800049ae  test    rax, rax
0x1800049b1  jz      short loc_1800049C1
0x1800049b3  test    byte ptr [rbx+4], 2
0x1800049b7  jnz     short loc_1800049C1
0x1800049b9  mov     rcx, rbx
0x1800049bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049c1  cmp     [rbx+8], edi
0x1800049c4  jl      short loc_1800049E0
0x1800049c6  cmp     r15d, 3
0x1800049ca  jnz     loc_180004AAF
0x1800049d0  mov     ecx, 8000FFFFh; this
0x1800049d5  mov     [rbx+8], ecx
0x1800049d8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800049dd  mov     [rbx+0Ch], eax
0x1800049e0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800049e7  jnz     short loc_180004A08
0x1800049e9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800049f0  test    rax, rax
0x1800049f3  jz      short loc_1800049FE
0x1800049f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049fa  test    al, al
0x1800049fc  jmp     short loc_180004A06
0x1800049fe  call    cs:__imp_IsDebuggerPresent
0x180004a04  test    eax, eax
0x180004a06  jz      short loc_180004A0E
0x180004a08  test    byte ptr [rbx+4], 2
0x180004a0c  jz      short loc_180004A32
0x180004a0e  mov     rax, cs:g_pfnResultLoggingCallback
0x180004a15  test    rax, rax
0x180004a18  jz      short loc_180004A76
0x180004a1a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004a21  jnz     short loc_180004A76
0x180004a23  xor     r8d, r8d
0x180004a26  xor     edx, edx
0x180004a28  mov     rcx, rbx
0x180004a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a30  jmp     short loc_180004A76
0x180004a32  mov     ebp, 800h
0x180004a37  mov     rax, cs:g_pfnResultLoggingCallback
0x180004a3e  test    rax, rax
0x180004a41  jz      short loc_180004A5A
0x180004a43  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004a4a  jnz     short loc_180004A5A
0x180004a4c  mov     r8d, ebp
0x180004a4f  mov     rdx, rsi
0x180004a52  mov     rcx, rbx
0x180004a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a5a  cmp     [rsi], di
0x180004a5d  jnz     short loc_180004A6D
0x180004a5f  mov     r8, rbx; unsigned __int64
0x180004a62  mov     rdx, rbp; unsigned __int16 *
0x180004a65  mov     rcx, rsi; this
0x180004a68  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004a6d  mov     rcx, rsi; lpOutputString
0x180004a70  call    cs:__imp_OutputDebugStringW
0x180004a76  test    byte ptr [rbx+4], 4
0x180004a7a  jnz     short loc_180004A85
0x180004a7c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004a83  jz      short loc_180004A97
0x180004a85  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004a8c  test    rax, rax
0x180004a8f  jz      short loc_180004A97
0x180004a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a96  nop
0x180004a97  mov     rbx, [rsp+78h+arg_10]
0x180004a9f  add     rsp, 40h
0x180004aa3  pop     r15
0x180004aa5  pop     r14
0x180004aa7  pop     r13
0x180004aa9  pop     r12
0x180004aab  pop     rdi
0x180004aac  pop     rsi
0x180004aad  pop     rbp
0x180004aae  retn
0x180004aaf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
